`nvidia-dkms` is a version of the NVIDIA proprietary graphics driver that uses [[Dynamic Kernel Module Support]] 
* `dkms status`
	* Check if the NVIDIA module is successfully installed and for which kernels. |
* `dkms autoinstall`
	* Manually trigger a rebuild of all DKMS modules for the current kernel.      |
* `dkms remove nvidia/<version> --all`
	* Remove the DKMS registration for the driver.
