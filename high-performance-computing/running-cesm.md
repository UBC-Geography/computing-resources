---
title: Running the Community Earth Sytem Model (CESM)
date: last-modified
---

::: {.callout-warning}

## Warning

This page is still a draft and requires further review.

:::

> The Community Earth System Model is a fully coupled global climate model
> developed in collaboration with colleagues in the research community. CESM
> provides state of the art computer simulations of Earth's past, present, and
> future climate states.

This page provides a tutorial on how to port
[CESM](https://github.com/ESCOMP/CESM) on an HTC/HPC environment using either
UBC ARC's Sockeye cluster or one of the Alliance clusters. This guide is
relatively technical and has the following requirements:

- Status as faculty or a librarian with an institution that holds eligibility
  for CFI grants
- An account on either UBC ARC Sockeye or the Alliance
- Working knowledge of UNIX/Linux

While this guide may be helpful to some, we strongly recommend reaching out to
support before attempting to setup CESM on your own as some configurations may
need to be modified, especially as systems are upgraded with new infrastructure.

If you are looking for any easier approach to run CESM, CESM 2.1.3 is available
as a module on the Alliance software stack, which can also be easily loaded on
the Sockeye cluster.

```bash
$ module load cesm
```

- [Alliance Documentation - CESM](https://docs.alliancecan.ca/wiki/CESM)

- [CESM 2.2 Documentation](https://escomp.github.io/CESM/versions/cesm2.2/html/introduction.html)

- [CIME Documentation - Porting Guide](https://esmci.github.io/cime/versions/master/html/users_guide/porting-cime.html)

## Porting CESM

1. Start by downloading CESM's source code from GitHub. This guide uses the
   latest stable release of CESM as of writing, but you can easily switch
   between minor versions using these
   [instructions](https://escomp.github.io/CESM/versions/cesm2.2/html/downloading_cesm.html)
   from the CESM documentation.

   ::: {.panel-tabset}

   ## Sockeye

   ```bash
   $ module load CVMFS_CC
   $ module load python/3.12
   $ git clone -b release-cesm2.2.2 https://github.com/ESCOMP/CESM.git
   $ python CESM/manage_externals/checkout_externals
   ```

   ## Alliance

   ```bash
   $ module load python/3.12
   $ git clone -b release-cesm2.2.2 https://github.com/ESCOMP/CESM.git
   $ python CESM/manage_externals/checkout_externals
   ```

   :::

2. To properly port CESM to a new system, a few configurations files need to be
   created that include details about the machine that CESM will be running on,
   how CESM should submit jobs to the machine/cluster's job scheduler, and what
   tweaks might need to be made for the compilation step.

   The first config file to create should be the `config_machines.xml` file.
   Examples for Sockeye and the Alliance's Cedar cluster are provided below.

   ```bash
   $ nano ~/.cime/config_machines.xml
   ```

   ::: {.panel-tabset}

   ## Sockeye

   On Sockeye, you can load the Alliance's software stack to access larger and
   often more up-to-date collection of software modules, which would be used by
   CESM for compilation.

   ```{.xml filename="~/.cime/config_machines.xml"}
   <?xml version="1.0"?>

   <config_machines version="2.0">
      <machine MACH="sockeye">
        <DESC>UBC ARC cluster, os is Linux, 40 pes/node, batch system is SLURM</DESC>
        <OS>LINUX</OS>
        <COMPILERS>intel,gnu</COMPILERS>
        <MPILIBS>openmpi</MPILIBS>
        <PROJECT><alloc-code></PROJECT>
        <CIME_OUTPUT_ROOT>/scratch/<alloc-code>/cesm/output</CIME_OUTPUT_ROOT>
        <DIN_LOC_ROOT>/scratch/<alloc-code>/cesm/inputdata</DIN_LOC_ROOT>
        <DIN_LOC_ROOT_CLMFORC>${DIN_LOC_ROOT}/atm/datm7</DIN_LOC_ROOT_CLMFORC>
        <DOUT_S_ROOT>$CIME_OUTPUT_ROOT/archive/$CASE</DOUT_S_ROOT>
        <GMAKE>make</GMAKE>
        <GMAKE_J>8</GMAKE_J>
        <BATCH_SYSTEM>slurm</BATCH_SYSTEM>
        <SUPPORTED_BY><your-email></SUPPORTED_BY>
        <MAX_TASKS_PER_NODE>40</MAX_TASKS_PER_NODE>
        <MAX_MPITASKS_PER_NODE>40</MAX_MPITASKS_PER_NODE>
        <PROJECT_REQUIRED>TRUE</PROJECT_REQUIRED>
        <mpirun mpilib="openmpi">
          <executable>mpirun</executable>
          <arguments>
            <arg name="anum_tasks"> -np {{ total_tasks }}</arg>
          </arguments>
        </mpirun>
        <module_system type="module" allow_error="true">
          <init_path lang="perl">$ENV{MODULESHOME}/init/perl</init_path>
          <init_path lang="python">$ENV{MODULESHOME}/init/env_modules_python.py</init_path>
          <init_path lang="csh">$ENV{MODULESHOME}/init/csh</init_path>
          <init_path lang="sh">$ENV{MODULESHOME}/init/sh</init_path>
          <cmd_path lang="perl">$ENV{MODULESHOME}/libexec/lmod perl</cmd_path>
          <cmd_path lang="python">$ENV{MODULESHOME}/libexec/lmod python</cmd_path>
          <cmd_path lang="csh">module</cmd_path>
          <cmd_path lang="sh">module</cmd_path>
          <modules>
      	    <command name="purge"/>
            <command name="load">CVMFS_CC</command>
            <command name="load">StdEnv/2023</command>
            <command name="load">python/3.11.5</command>
            <command name="load">cmake/3.31.0</command>
          </modules>
          <modules compiler="intel">
            <command name="load">intel/2023.2.1</command>
            <command name="load">imkl/2024.2.0</command>
          </modules>
          <modules compiler="gnu">
            <command name="load">gcc/12.3</command>
            <command name="load">openblas/0.3.24</command>
          </modules>
          <modules mpilib="openmpi">
            <command name="load">openmpi/4.1.5</command>
            <command name="load">hdf5-mpi/1.14.5</command>
            <command name="load">netcdf-mpi/4.9.2</command>
            <command name="load">netcdf-c++4-mpi/4.3.1</command>
            <command name="load">netcdf-fortran-mpi/4.6.1</command>
            <command name="load">pnetcdf/1.12.3</command>
            <command name="load">parallelio/2.6.3</command>
            <command name="load">esmf/8.7.0</command>
          </modules>
        </module_system>
        <environment_variables>
          <env name="OMP_STACKSIZE">256M</env>
        </environment_variables>
        <environment_variables comp_interface="nuopc">
          <env name="ESMF_RUNTIME_PROFILE">ON</env>
          <env name="ESMF_RUNTIME_PROFILE_OUTPUT">SUMMARY</env>
        </environment_variables>
        <resource_limits>
          <resource name="RLIMIT_STACK">300000000</resource>
        </resource_limits>
      </machine>
    </config_machines>
   ```

   ## Alliance - Cedar

   While the following example is focused on the Cedar cluster, with a few
   modifications, it could also work on other Alliance clusters. One item to
   note is that many Alliance clusters run both Intel and AMD CPUs in their
   nodes, and according to the
   [Alliance's documentation](https://docs.alliancecan.ca/wiki/BLAS_and_LAPACK)
   loading Flexiblas for BLAS and LAPACK can be a safe method to ensure you are
   using the best library for whichever nodes you might be running on.

   ```{.xml filename="~/.cime/config_machines.xml"}
   <?xml version="1.0"?>

   <config_machines version="2.0">
      <machine MACH="cedar">
        <DESC>Alliance cluster hosted at SFU, os is Linux, 48 pes/node, batch system is SLURM>/DESC>
        <NODENAME_REGEX>c[de].*.computecanada.ca</NODENAME_REGEX>
        <OS>LINUX</OS>
        <COMPILERS>intel,gnu</COMPILERS>
        <MPILIBS>openmpi</MPILIBS>
        <PROJECT><group_name></PROJECT>
        <CIME_OUTPUT_ROOT>$ENV{SCRATCH}/cesm/output</CIME_OUTPUT_ROOT>
        <DIN_LOC_ROOT>$ENV{SCRATCH}/cesm/inputdata</DIN_LOC_ROOT>
        <DIN_LOC_ROOT_CLMFORC>$DIN_LOC_ROOT/atm/datm7</DIN_LOC_ROOT_CLMFORC>
        <DOUT_S_ROOT>$CIME_OUTPUT_ROOT/archive/$CASE</DOUT_S_ROOT>
        <GMAKE>make</GMAKE>
        <GMAKE_J>8</GMAKE_J>
        <BATCH_SYSTEM>slurm</BATCH_SYSTEM>
        <SUPPORTED_BY>support@tech.alliancecan.ca</SUPPORTED_BY>
        <MAX_TASKS_PER_NODE>48</MAX_TASKS_PER_NODE>
        <MAX_MPITASKS_PER_NODE>48</MAX_MPITASKS_PER_NODE>
        <PROJECT_REQUIRED>TRUE</PROJECT_REQUIRED>
        <mpirun mpilib="openmpi">
          <executable>mpirun</executable>
            <arguments>
                <arg name="anum_tasks"> -np {{ total_tasks }}</arg>
            </arguments>
        </mpirun>
        <module_system type="module" allow_error="true">
          <init_path lang="perl">$ENV{MODULESHOME}/init/perl</init_path>
          <init_path lang="python">$ENV{MODULESHOME}/init/env_modules_python.py</init_path>
          <init_path lang="csh">$ENV{MODULESHOME}/init/csh</init_path>
          <init_path lang="sh">$ENV{MODULESHOME}/init/sh</init_path>
          <cmd_path lang="perl">$ENV{MODULESHOME}/libexec/lmod perl</cmd_path>
          <cmd_path lang="python">$ENV{MODULESHOME}/libexec/lmod python</cmd_path>
          <cmd_path lang="csh">module</cmd_path>
          <cmd_path lang="sh">module</cmd_path>
        <modules>
      	    <command name="purge"/>
            <command name="load">StdEnv/2023</command>
            <command name="load">python/3.11.5</command>
            <command name="load">cmake/3.31.0</command>
        </modules>
        <modules compiler="intel">
            <command name="load">intel/2023.2.1</command>
        </modules>
        <modules compiler="gnu">
            <command name="load">gcc/12.3</command>
        </modules>
        <modules>
            <command name="load">flexiblas/3.3.1</command>
        </modules>
        <modules mpilib="openmpi">
            <command name="load">openmpi/4.1.5</command>
            <command name="load">hdf5-mpi/1.14.5</command>
            <command name="load">netcdf-mpi/4.9.2</command>
            <command name="load">netcdf-c++4-mpi/4.3.1</command>
            <command name="load">netcdf-fortran-mpi/4.6.1</command>
            <command name="load">pnetcdf/1.12.3</command>
            <command name="load">parallelio/2.6.3</command>
            <command name="load">esmf/8.7.0</command>
        </modules>
    </module_system>
    <environment_variables>
      <env name="OMP_STACKSIZE">256M</env>
    </environment_variables>
    <environment_variables comp_interface="nuopc">
      <env name="ESMF_RUNTIME_PROFILE">ON</env>
      <env name="ESMF_RUNTIME_PROFILE_OUTPUT">SUMMARY</env>
    </environment_variables>
    <resource_limits>
      <resource name="RLIMIT_STACK">300000000</resource>
    </resource_limits>
   ```

   :::

   Once you've finished creating `config_machines.xml`, run the file through
   `xmllint` to verify that it complies with the XML schema.

   ```bash
   $ xmllint --noout --schema $CIME/config/xml_schemas/config_machines.xsd $HOME/.cime/config_machines.xml
   ```

3. The next config file to create is `config_batch.xml`. Since both Sockeye and
   the Alliance clusters use the SLURM job scheduler, this file should be pretty
   easy to adapt between any of the clusters. Just remember to replace
   `<machine_name>`.

   ```bash
   $ nano ~/.cime/config_batch.xml
   ```

   ```{.xml filename="~/.cime/config_batch.xml"}
   <batch_system MACH="<machine_name>" type="slurm" >
     <batch_submit>sbatch</batch_submit>
     <batch_cancel>scancel</batch_cancel>
     <batch_directive>#SBATCH</batch_directive>
     <jobid_pattern>(\d+)$</jobid_pattern>
     <depend_string> --dependency=afterok:jobid</depend_string>
     <depend_allow_string> --dependency=afterany:jobid</depend_allow_string>
     <depend_separator>,</depend_separator>
     <submit_args>
       <arg flag="--time" name="$JOB_WALLCLOCK_TIME"/>
       <arg flag="--account" name="$PROJECT"/>
     </submit_args>
     <directives>
       <directive>--job-name={{ job_id }}</directive>
       <directive>--nodes={{ num_nodes }}</directive>
       <directive>--ntasks-per-node={{ tasks_per_node }}</directive>
       <directive>--output={{ job_id }}</directive>
       <directive>--exclusive</directive>
       <directive>--mem=0</directive>
     </directives>
     <unknown_queue_directives>regular</unknown_queue_directives>
     <queues>
       <queue walltimemax="12:00:00" nodemin="1" nodemax="4032"><machine_name></queue>
     </queues>
   </batch_system>
   ```

   Again validate this file using `xmllint`.

   ```bash
   $ xmllint --noout --schema $CIME/config/xml_schemas/config_batch.xsd $HOME/.cime/config_batch.xml
   ```

4. The last config file is used to provide information for the compilation step.
   For versrions of CESM <= 2.2.2, a `config_compilers.xml` file should be
   created, while newer versions of CESM will deperecate that config file and
   switch to using cmake macros file.

   ::: {.panel-tabset}

   ## Sockeye

   ```{.xml filename="~/.cime/config_compilers.xml"}
   <compiler MACH="sockeye">
     <CPPDEFS>
        <append MODEL="gptl"> -DHAVE_NANOTIME -DBIT64 -DHAVE_VPRINTF -DHAVE_BACKTRACE -DHAVE_SLASHPROC -DHAVE_COMM_F2C -DHAVE_TIMES -DHAVE_GETTIMEOFDAY </append>
      </CPPDEFS>
     <ESMF_LIBDIR>$ENV{EBROOTESMF}/lib</ESMF_LIBDIR>
     <HDF5_PATH>$ENV{HDF5_DIR}</HDF5_PATH>
     <MPI_LIB_NAME>openmpi</MPI_LIB_NAME>
     <MPI_PATH>$ENV{EBROOTOPENMPI}</MPI_PATH>
      <NETCDF_C_PATH>$ENV{EBROOTNETCDF}</NETCDF_C_PATH>
     <NETCDF_FORTRAN_PATH>$ENV{EBROOTNETCDFMINFORTRAN}</NETCDF_FORTRAN_PATH>
      <PIO_FILESYSTEM_HINTS>lustre</PIO_FILESYSTEM_HINTS>
      <PNETCDF_PATH>$ENV{PNETCDF}</PNETCDF_PATH>
   </compiler>
   ```

   ## Allianec - Cedar

   ```{.xml filename="~/.cime/config_compilers.xml"}
   <compiler MACH="cedar">
     <CPPDEFS>
        <append MODEL="gptl"> -DHAVE_NANOTIME -DBIT64 -DHAVE_VPRINTF -DHAVE_BACKTRACE -DHAVE_SLASHPROC -DHAVE_COMM_F2C -DHAVE_TIMES -DHAVE_GETTIMEOFDAY </append>
      </CPPDEFS>
     <ESMF_LIBDIR>$ENV{EBROOTESMF}/lib</ESMF_LIBDIR>
     <HDF5_PATH>$ENV{HDF5_DIR}</HDF5_PATH>
     <MPI_LIB_NAME>openmpi</MPI_LIB_NAME>
     <MPI_PATH>$ENV{EBROOTOPENMPI}</MPI_PATH>
      <NETCDF_C_PATH>$ENV{EBROOTNETCDF}</NETCDF_C_PATH>
     <NETCDF_FORTRAN_PATH>$ENV{EBROOTNETCDFMINFORTRAN}</NETCDF_FORTRAN_PATH>
      <PIO_FILESYSTEM_HINTS>lustre</PIO_FILESYSTEM_HINTS>
      <PNETCDF_PATH>$ENV{PNETCDF}</PNETCDF_PATH>
      <SLIBS>
        <append>-L$ENV{FLEXIBLAS_LIBRARY_PATH} -lflexiblas</append>
      </SLIBS>
   </compiler>
   ```

   :::

   Again, use `xmllint` for validation.

   ```bash
   $ xmllint --noout --schema $CIME/config/xml_schemas/config_compilers_v2.xsd $HOME/.cime/config_compilers.xml
   ```

   Newer version of CESM will switch to using Cmake Macros

   ::: {.panel-tabset}

   ## Sockeye

   ```{.sh filename="~/.cime/sockeye.cmake"}
   if (COMP_NAME STREQUAL gptl)
     string(APPEND CPPDEFS " -DHAVE_NANOTIME -DBIT64 -DHAVE_VPRINTF -DHAVE_BACKTRACE -DHAVE_SLASHPROC -DHAVE_COMM_F2C -DHAVE_TIMES -DHAVE_GETTIMEOFDAY")
   endif()
   set(ESMF_LIBDIR "$ENV{EBROOTESMF}/lib")
   set(MPI_LIB_NAME "openmpi")
   set(MPI_PATH "$ENV{EBROOTOPENMPI}")
   set(HDF5_PATH "$ENV{HDF5_DIR}")
   set(NETCDF_C_PATH "$ENV{EBROOTNETCDF}")
   set(NETCDF_FORTRAN_PATH "$ENV{EBROOTNETCDFMINFORTRAN}")
   set(PNETCDF_PATH "$ENV{PNETCDF}")
   set(PIO_FILESYSTEM_HINTS "lustre")
   set(PIO_LIBDIR "$ENV{PIO}/lib")
   set(PIO_INCDIR "$ENV{PIO}/include")
   ```

   ## Alliance - Cedar

   ```{.sh filename="~/.cime/cedar.cmake"}
   if (COMP_NAME STREQUAL gptl)
     string(APPEND CPPDEFS " -DHAVE_NANOTIME -DBIT64 -DHAVE_VPRINTF -DHAVE_BACKTRACE -DHAVE_SLASHPROC -DHAVE_COMM_F2C -DHAVE_TIMES -DHAVE_GETTIMEOFDAY")
   endif()
   set(ESMF_LIBDIR "$ENV{EBROOTESMF}/lib")
   set(MPI_LIB_NAME "openmpi")
   set(MPI_PATH "$ENV{EBROOTOPENMPI}")
   set(HDF5_PATH "$ENV{HDF5_DIR}")
   set(NETCDF_C_PATH "$ENV{EBROOTNETCDF}")
   set(NETCDF_FORTRAN_PATH "$ENV{EBROOTNETCDFMINFORTRAN}")
   set(PNETCDF_PATH "$ENV{PNETCDF}")
   set(PIO_FILESYSTEM_HINTS "lustre")
   set(PIO_LIBDIR "$ENV{PIO}/lib")
   set(PIO_INCDIR "$ENV{PIO}/include")
   string(REPLACE "-mkl=cluster" "" SLIBS "${SLIBS}")
   string(APPEND SLIBS "-lflexiblas")
   ```

   :::

5. To further validate the config files, run the `scripts_regression_test.py`
   that's included with CESM.

   ```bash
   $ python ./CESM/cime/scripts/tests/scripts_regression_test.py
   ```

6. run cheyenne prealpha tests

   ```bash
   $ ./CESM/cime/scripts/create_test --xml-category prealpha --xml-machine cheyenne --xml-compiler intel --machine <your_machine_name> --compiler <your_compiler_name>
   ```
