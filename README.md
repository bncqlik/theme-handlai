# theme-handlai
The master/main thene that is used  by handlai.com

## Prerequisites
Set Up a Second GitHub Account in VSCode:
    Generate SSH Key for Second Account
    $ ssh-keygen -t rsa -b 4096 -C "your_second_email@example.com"
and save the key with a distinct name, such as id_rsa_second

eval "$(ssh-agent -s)"
Add the new SSH key to the agent:
    $ ssh-add ~/.ssh/id_rsa_second

Configure Git with Second Account:
    Set the global Git configurations for your second account:
        $ git config --global user.name "Your Second Name"
        $ git config --global user.email "your_second_email@example.com"

Use Different SSH Configurations for Each Account:
    Create or Edit SSH Config File:
        If you don't have an SSH config file, create one:
        $ touch ~/.ssh/config

Edit the SSH config file:
        eg. $ nano ~/.ssh/config

Configure SSH Hosts for Each GitHub Account:
    Add entries for both GitHub accounts:
    plaintext
        # Personal GitHub account
        Host github.com
          HostName github.com
          User git
          IdentityFile ~/.ssh/id_rsa

        # Second GitHub account
        Host github-second
          HostName github.com
          User git
          IdentityFile ~/.ssh/id_rsa_second

        Save the file.

Use Different Configurations in VSCode:

    Open VSCode:
        Open the project associated with your second GitHub account or clone a repository using the second account.

    Set Repository-Specific Configurations:
        Inside the repository, set the repository-specific Git configurations for your second account:

        bash
    git config user.name "Your Second Name"
    git config user.email "your_second_email@example.com"

Use SSH URLs with VSCode:

    When cloning or working with repositories associated with your second account, use the SSH URL with the configured SSH host alias:

    bash

        git clone git@github-second:username/repo.git

        Replace username and repo with the appropriate GitHub username and repository name.

By following these steps, you can have separate SSH keys and configurations for each GitHub account, allowing you to work seamlessly with multiple GitHub accounts in Visual Studio Code. Remember to adjust the SSH host alias in the SSH URL according to your configuration.