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
3. Add Docker's official GPG key:

  ```
  curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
  ```
  
  *Be sure to verify that the key ID is:
  ```
  9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88
  ```
  ```
  sudo apt-key fingerprint 0EBFCD88

  pub   4096R/0EBFCD88 2017-02-22
      Key fingerprint = 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
  uid                  Docker Release (CE deb) <docker@docker.com>
  sub   4096R/F273FCD8 2017-02-22
  ```
  
  4. Next, we're going to tell Debian to check the "stable" repository when installing/updating. Please that that you will
  always need the stable repository, even if you're adding the "edge" or "test" repositories later. 
  
  ```
  sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
  ```
  
  5. Install Docker CE
  
  Update the ```apt``` package index:
  
  ```
  sudo apt-get update
  ```
  
  Install the latest version of Docker CE:
  
  ```
  sudo apt-get install docker-ce
  ```
