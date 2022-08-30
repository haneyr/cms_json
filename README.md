This notebook has been tested with a Vertex AI workbench running on a m1-ultramem-40 (40 vCPUs, 961 GB RAM) - additional testing is underway for performance on smaller instance types.

2022-08-30 Update:

This notebook has been tested on machines as small as n1-standard4 (4 vCPU, 15GB of RAM), using 1TB of SSD swap space.  Relying on swap slows the JSON parsing significantly - one example JSON that was approximately 120GB in total size took roughly three days to fully process; however, the machine cost is significantly lower using swap versus memory.

To create a 1TB swap file, first create a GCP VM or Vertex Workspace notebook server with at least a 1150GB root volume.

Next:

1. sudo fallocate -l 1024G /swapfile
2. sudo chmod 600 /swapfile
3. sudo mkswap /swapfile
4. sudo swapon /swapfile

To persist the changes, add the following line to /etc/fstab.  

1. /swapfile swap swap defaults 0 0

Verify the swap space is active:

1. sudo swapon --show


Copyright 2022 Google LLC. This software is provided as-is, without warranty or representation for any use or purpose. Your use of it is subject to your agreements with Google.
