CMPE283 : Virtualization
Assignment 1: Communicating with the hypervisor
Due: Oct 14 2019 Before Midnight

Notes From Sergio Aguilar
Sep 29   task completed
    1- Create a partition in a windows 10
    2- Install Ubuntu 18.04
    Issues: Unable to install Ubuntu alongside... (windows 10) 
    Solution: The computer use to have windows 7 when I migrated to windows 10, 
             I forgot to change the partition from MBR to GUID; so, I ending 
             with windows 10 in a legacy BIOS and during the installation 
             Ubuntu does not recognize the windows 10 Operating Sysytem and 
             it does not give me the option of "install Ubuntu alongside…". 
             Therefore, I have migrate partition to GUID, change the BIOS to UEFI
             and now Install a Ubuntu. Finally in same latop I have windows 10 
             and Ubuntu 18.04.

Oct 04  
    1- Installation of KVM

Oct 06
    1- Install git
    2- Clone repository
    3- install pakages required to compile
    4- compile the kernel
    5- install  virt-manager 

Oct 08
    1) Ensure the the KVM can support virtualization
		grep -c '(vmx|svm)' /proc/cpuinfo
		0
	Issues:   If the output is greater than 0 then 
                  it means your system supports Virtualization 
                  else reboot your system, then go to BIOS settings and enable VT technology.
 	Solution: Increase the CPU of the KVM to 8 CPU
		  modify file:  vi /etc/modprobe.d/qemu-system-x86.conf
		  to include the line  options kvm-intel nested=y enable_apicv=n
		  and reboot
	    After fixed
	            grep -c '(vmx|svm)' /proc/cpuinfo
		    8
	    Also  Install “kvm-ok”utility and run command  sudo kvm-ok
		    INFO: /dev/kvm exists
		    KVM acceleration can be used
	    So the VM instance can be installed faster
    2) Create a VM  using ubuntu but 15GB


Oct 12
    1) Fork and Clone reporsitory from Achalaesh  (Work as a team from one reporsitory)
    2) Compile Linux again
    3) Get access as colaborator 	

Oct 13 & 14
    1) Add installation notes in this readme file
    2) Read/research about files  x86.c and vmx.c

