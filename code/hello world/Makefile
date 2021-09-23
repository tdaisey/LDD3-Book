# Linux device driver makefile

# This Makefile has two parts because it will be read twice.
# First, when we call 'make' on the command line and KERNELRELEASE is not defined.  
# Second, by the kernel build system. 

# If KERNELRELEASE is not defined then we've been called directly from 
# the command line (make) and we need to invoke the kernel build system. 
# The kernel build system will then look for the Makefile in the module's 
# directory to know what to build and KERNELRELEASE will be set. 

# If KERNELRELEASE not empty
ifneq ($(KERNELRELEASE),)  

    obj-m := hello.o

# Else KERNELRELEASE is empty
else    

    KERN_DIR ?= /usr/src/linux-headers-$(shell uname -r)/
    PWD := $(shell pwd)
    
default: 

	$(MAKE) -C $(KERN_DIR) M=$(PWD) modules

endif

clean:
	rm -rf *.o *~ core .depend .*.cmd *.ko *.mod.c .tmp_versions