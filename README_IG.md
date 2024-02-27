# Introduction <!-- omit in toc -->

This file contains notes about the changes I do in this repo. 

This repo is based on [this template](https://github.com/onedr0p/cluster-template). 

# Contents <!-- omit in toc -->

- [1. Setting up the hardware](#1-setting-up-the-hardware)
- [2. Keeping this repo upto date with the template repo](#2-keeping-this-repo-upto-date-with-the-template-repo)


# 1. Setting up the hardware

Use the `rpi-imager` tool to set-up the hardware.

My hardware: 
- Raspberry pi 5: 
  - Raspberry pi 5 8gb: `ssh pi5-8gb-1@pi5-8gb-1.local`

# 2. Keeping this repo upto date with the template repo

At some point you may want to update your Git repository with some commit from this repository. The following is one method to achieve this.

1. Add this repository as an additional remote

    ```sh
    git remote add tmpl git@github.com:onedr0p/cluster-template.git
    ```

2. Fetch all the branches

    ```sh
    git fetch tmpl
    ```

3. List the commits from this repository

    ```sh
    git log tmpl/main
    ```

4. There are two methods to bring changes from template in here: 
   
   4.1. Pick the commit you want to bring over to your repository

    ```sh
    git cherry-pick ce67a3c
    ```

   4.2. Use difftool to compare latest with the current repo and add changes manually

   ```bash
   git difftool tmpl/main
   ```

   If a new file that was not present in my local main was added to the template, Meld (difftool) wouldn't be able to save that file. If this is the case, you'll get an error when trying to save. for these files find the file location with `git diff tmpl/main` and do `git checkout tmpl/main path/to/new/file` to get the new file. 


5. Push the changes up to your Git remote

    ```sh
    git push origin main
    ```
