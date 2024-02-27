CONFIG_MODULE_SIG=n
ifeq ($(KERNELRELEASE),) 
#ifeq后面一定要加空格
#非命令行前面不能以tab开头，必须以空格开头
 KERNELDIR ?= /lib/modules/$(shell uname -r)/build  
 KERNEL ?= /usr/src/linux-hwe-6.5-headers-6.5.0-21/include
 USR ?= /usr/src/linux-headers-6.5.0-21-generic/arch/x86/include/generated
 M=$(PWD) modules
 PWD := $(shell pwd)
modules:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules #必须以tab开头
modules_install:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules_install #必须以tab开头
clean:
	rm -rf *.o *~ core .depend .*.cmd *.ko *.mod *.mod.c .tmp_versions Module* modules* #必须以tab开头
.PHONY: modules modules_install clean
else
 obj-m :=pango_pci_driver.o #空格开头
endif

edit : $(objects)
        cc -o edit $(objects)