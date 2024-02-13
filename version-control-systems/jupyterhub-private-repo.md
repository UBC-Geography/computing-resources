---
title: Working with Private GitHub Repositories from JupyterHub
---

## Using Fine-Grained Personal Access Tokens

This is the recommended method for cloning and pushing commits to a private
GitHub repository while working within a JupyterHub server. A fine-grained
personal access token, acts as a password for your account and provides a
limited set of functionality when working with your GitHub repositories.

You can have multiple personal access tokens associated with your GitHub account
with various levels of access to your account and specific repositories
associated with it. You can generate tokens from within the
[developer settings](https://github.com/settings/tokens?type=beta) of your
personal account.

When creating a new token, ensure that you provided it with the minimum
privileges necessary to interact with your private repositories via JupyterHub.
This includes setting a short expiration date for the token and restricting the
token to only work with a specific repository.

![GitHub fine-grained personal access token - name, expiration, description, and repository access](/assets/images/github-personal-token-1.PNG)

Also set restrictive permissions for the token. If you only need to clone a
private repository from JupyterHub, set the 'Contents' permissions to
'Read-only'. Otherwise, if you plan to make changes to any files in the
repository and push those changes to GitHub, set the 'Contents' permissions to
'Read and write'.

![GitHub fine-grained personal access token - permissions](/assets/images/github-personal-token-2.PNG)

Once you click 'Generate token', GitHub will display your new personal access
token. Be sure to copy and store the token in a secure place. From JupyterLab's
Git extension, you can now provide your GitHub username and your token in place
of a password to clone and push changes to token's associated repository.

## Using SSH

::: {.callout-important}

This method is not recommended. While there are multiple precautions taken by
UBC LT and Syzygy to isolate and secure your JupyterHub environment, if for any
reason your environment were to be compromised, a bad actor could gain full
access to your GitHub account.

:::

If you must use this method, ensure you generate a new SSH key on JupyterHub
with a strong passphrase. Never reuse/store an SSH private key that you have
generated on your local machine within a JupyterHub environment.

From a Terminal in your JupyterHub server, run the following command to generate
a new SSH key.

```bash
jovyan@jupyter-<your_cwl>:~$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/jovyan/.ssh/id_rsa):
Created directory '/home/jovyan/.ssh'.
Enter passphrase (empty for no passphrase): <enter_a_strong_passphrase_here>
Enter same passphrase again:
Your identification has been saved in /home/jovyan/.ssh/id_rsa
Your public key has been saved in /home/jovyan/.ssh/id_rsa.pub
```

To use your new SSH key, add a public key to your GitHub personal account from
the [SSH Key Settings page](https://github.com/settings/ssh/new) by copying the
contents of /home/jovyan/.ssh/id_rsa.pub into the key field.

From JupyterHub, you'll then be able to clone and push changes to all of your
private repositories within GitHub using the SSH protocol.
