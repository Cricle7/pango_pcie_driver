CONFIG_MODULE_SIG=n
ifeq ($(KERNELRELEASE),) 
#ifeq后面一定要加空格
#非命令行前面不能以tab开头，必须以空格开头
 KERNELDIR ?= /lib/modules/$(shell uname -r)/build  
 #KERNELDIR ?= /usr/src/linux-headers-6.5.0-21-generic/include/linux
 KERNEL ?= /usr/src/linux-hwe-6.5-headers-6.5.0-21/include
 USR ?= /usr/src/linux-headers-6.5.0-21-generic/arch/x86/include/generated
 M=$(PWD) modules
 PWD := $(shell pwd)
modules:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules #必须以tab开头
# //-C 表示进入到某一个目录下去编译
# //`pwd`：表示把两个`号中间的内容当成命令执行
# //M=`pwd`则表示把pwd打印的内容保存起来，目的是为了编译好了之后能够返回原来的目录
# //modules就是真正用来编译模块的命令，在内核的其他地方定义过了
modules_install:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules_install #必须以tab开头
clean:
	rm -rf *.o *~ core .depend .*.cmd *.ko *.mod *.mod.c .tmp_versions Module* modules* #必须以tab开头
.PHONY: modules modules_install clean
else
 obj-m :=pango_pci_driver.o #空格开头
 # //-m 表示我们要将module_test.c编译成一个模块
 # //-y表示我们要将module_test.c编译链接进zImage
endif

