obj-m := GobiNet.o
GobiNet-objs := GobiUSBNet.o QMIDevice.o QMI.o
KDIR := /lib/modules/$(shell uname -r)/build
PWD := $(shell pwd)
OUTPUTDIR=/lib/modules/`uname -r`/kernel/drivers/net/usb/

all: 
	$(MAKE) -C $(KDIR) M=$(PWD) modules

install: all
	mkdir -p $(OUTPUTDIR)
	cp -f GobiNet.ko $(OUTPUTDIR)
	depmod

clean:
	$(MAKE) -C $(KDIR) M=$(PWD) clean


