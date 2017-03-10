# Sharing Your IDE Settings

On this page:

- Introduction
- Prerequisites
- Configuring settings repository
- Authentication
- Configuring a read-only source

## Introduction

PhpStorm allows you to share your IDE settings between different instances of PhpStorm (or other IntelliJ platform-based) products installed on different computers.

This is useful if you are using several PhpStorm installations, or want to implement the same settings among your team members or company-wide.

## Prerequisites

Before you start working with Settings Repository, make sure that the Settings Repository plugin is enabled. The plugin is bundled with PhpStorm and is activated by default. If the plugin is not activated, enable it on the Plugins page of the Settings / Preferences Dialog as described in Enabling and Disabling Plugins.

## Configuring settings repository

If you want to share your IDE settings, perform the following steps:

If you select to use Bitbucket to host your repository, the use of App passwords is recommended for authentication. You need to set the read/write permissions for your repositories.
1. Create a Git repository on any hosting service, such as Bitbucket or GitHub.
2. On the computer where the PhpStorm instance whose settings you want to share is installed, navigate to File | Settings Repository. Specify the URL of the repository you've created and click Overwrite Remote.
3. On each computer where you want your settings to be applied, in the Settings/Preferences dialog , expand the Tools node and chooseSettings Repository, specify the URL of the repository you've created, and click Overwrite Local.

You can click **Merge** if you want the repository to keep a combination of the remote settings and your local settings. If any conflicts are detected, a dialog will be displayed where you can resolve these conflicts.

If you want to overwrite the remote settings with your local settings, click **Overwrite Remote**.

Your local settings will be automatically synchronized with the settings stored in the repository each time you perform an Update Project or a **Push** operation, or when you close your project or exit PhpStorm.

If you want to disable automatic settings synchronization, navigate to **File | Settings | Tools | Settings Repository** and disable the **Auto Sync** option. You will be able to update your settings manually by choosing **VCS | Sync Settings** from the main menu.

## Authentication

On the first sync, you will be prompted to specify a username and password.

It is recommended to use an access token for GitHub authentication. If, for some reason, you want to use a username and password instead of an access token, or your Git hosting provider doesn't support it, it is recommended to configure the Git credentials helper.

Note that the OS X Keychain is supported, which means you can share your credentials between all IntelliJ Platform-based products (you will be prompted to grant access if the original IDE is different from the requestor IDE).

## Configuring a read-only source

Apart from the **Settings Repository**, you can configure any number of additional repositories containing any types of settings you want to share, including live templates, file templates, schemes, deployment options, etc.

These repositories are referred to as **Read-only sources**, as they cannot be overwritten or merged, just used as a source of settings as is.

To configure such repositories, do the following:

In the Settings/Preferences dialog, expand the **Tools** node and choose Settings Repository.
Click **+** and add the URL of the GitHub repository that contains the settings you want to share.
Synchronization with the settings from **read-only sources** is performed in the same way as for the Settings Repository.
