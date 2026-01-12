# Chapter 2
I will be documenting this chapter chronologically, and according to the documentation. So if I write 2.1 for instance, this is a reference to 2.1 in the documentation. The section that follows, should be a log of my experience with that section in the documentation.

---

## Overview of the chapter (2.1)
This chapter goes over and checks the host tools necessary for the build, and if they are not present will require to be installed. We then prepare the disk partition, create it and its filesystem, before finally mounting it.

## Host system requirements (2.2)

### Hardware (2.2.1)
Four cores and 8GB memory is reccomended. The virtual machine has been allocated 8GB memory and 5 cores, if the build time becomes an issue then this will be reallocated.

### Software (2.2.2)

My host system must have the following installed with their respective minimum versions:
  - Bash (3.2)
  - Binutils (2.13.1)
  - Coreutils (8.1)
  - Diffutils (2.8.1)
  - Findutils (4.2.31)
  - Gawk (4.0.1) 
  - GCC (5.4) 
  - Grep (2.5.1)
  - Gzip (1.3.12)
  - Linux Kernel (5.4)
  - M4 (1.4.10)
  - Make (4.0)
  - Patch (2.5.4)
  - Perl (5.8.8)
  - Python (3.4)
  - Sed (4.1.5)
  - Tar (1.22)
  - Texinfo (5.0)
  - Xz (5.0.0)

In order to check if my host system has all of the appropriate software and versions I used the official version-check script provided in the LFS documentation

The script was executed using:
```sh
bash version-check.sh

Several required host tools were missing or below the minimum version. These were installed using the Debian package manager (`apt`). After installation, the version-check script was re-run and all requirements were satisfied.

### 2.3.1 + 2.3.2

LFS requires the certain steps to be excecuted as the root user (unrestricted access, privileged user), whereas other must be run as an unprivileged user (LFS). This seperation prevents accidental modification of the host system. The following commands must therefore be run inside of the terminal.

  - sudo-i -> gives me root user access, I am essentially in "root mode" here. This causes the terminal to go       from name@hostname: ~$ to root@hostname: ~#, indicating that we are in root user mode.
  - export LFS=/mnt/lfs -> This takes "LFS" from a shell variable and makes it an environment variable. Many        commands in the documentation contain $LFS, if the variable is not exported then commands may act on /,         instead of /mnt/lfs. This command is a safety mechanism to stop the commands acting on the root user.
  - echo $LFS -> just prints what is stored inside of the variable LFS, and should print /mnt/lfs, which it         does 

I have to then mount the mnt/lfs partition, I can check if this is done by using the bash command:  lsblk, this command must be done as the root user. Since I have not mounted it, there is no sign of mnt/lfs being mounted. Therefore I must mount it to a disk partition which I will do by creating a loopback file. I will make this 30gb.
I must use the following commands to do this:

  - mkdir -pv /mnt/lfs -> Creates a directory to hold the virtual disk
  - dd if=/dev/zero of=/lfs.img bs=1M count=30720 status=progress -> Creates a 30gb loopback file. 
  - mkfs.ext4 /lfs.img -> Format the file as ext4
  - mount -v /lfs.img /mnt/lfs -> Mount the file at /mnt/lfs

Finally I just verify it with the same2 lsblk command as before. It has been correctly mounted, as the file now shows when the command runs. Therefore the dedicated ext4 filesystem mounted at /mnt/lfs has been created, satisfying the documentations requirement for an isolated build environment before proceeding to user and toolchain preperation.


