## Overview

This page will provide steps to get Docker installed on a Debian Linux OS. This will be a base installation,
so all other steps to configure and manage Docker can be found in different instructions. 

## Docker Repository Setup

The easiest and most efficient method for installing Docker is by using the official Docker repository. This will also
allow easier upgrade methods.

1. Update the apt-get package:

  ```
  sudo apt-get update
  ```

2. Install the packages that will allow ```apt``` to use a repository:

  ```
  sude apt-get install apt-transport-https curl gnupg2 software-properties-common
  ```
3. 
