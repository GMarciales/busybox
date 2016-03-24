# Build environment for GNS3 Docker Init

The build script, the config file and the patches
are copied from the alpine busybox package,
see http://git.alpinelinux.org/cgit/aports/tree/main/busybox

Changes:
- Created build script make_busybox from APKBUILD file
- Changed busyboxconfig to static build
- In busyboxconfig changed default udhcpc script to
  `CONFIG_UDHCPC_DEFAULT_SCRIPT="/gns3/etc/udhcpc/default.script"`

## Building

Install docker (https://www.docker.com) and run:  
``docker run -t -v <git repository base dir>:/source alpine sh /source/gns3_build/build_busybox``

e.g, when you install this git repository in /home/xyz/busybox then run  
``docker run -t -v /home/xyz/busybox:/source alpine sh /source/gns3_build/build_busybox``

The directory must be given as an absolute path.

From root directory of busybox:  
``docker run -t -v `pwd`:/source alpine sh /source/gns3_build/build_busybox``

After the build the binary (busybox) is copied to the base directory.
