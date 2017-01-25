QVD basic desktop LXC image
===========================

It is a basic Xubuntu desktop with:

 * Libreoffice
 * Firefox
 * Thunderbird
 * Evince

Support for LXC images
======================

This is how to build a basic desktop LXC image for QVD using Docker.

To create the tar.gz file importable into QVD (for LXC backends) please use the following
commands:

  sudo docker build -t theqvd/qvdimage-basicdesktop-xubuntu-1604 .
  vmid=$(sudo docker run -d -t -i theqvd/qvdimage-basicdesktop-xubuntu-1604 /bin/bash -c "read a; echo $a")
  docker export $vmid  | gzip -c > qvd-image-basicdesktop-xubuntu-16.04.tgz
  sudo docker kill $vmid

And the importable image is qvd-image-basicdesktop-xubuntu-16.04.tgz

References
==========

More information about QVD can be found here: http://theqvd.com

Further docs are available here http://docs.theqvd.com
