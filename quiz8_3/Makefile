obj-m += dont_trace.o
TARGET_MODULE := dont_trace

KERNELDIR ?= /lib/modules/`uname -r`/build
PWD := $(shell pwd)

all:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules

load:
	sudo insmod $(TARGET_MODULE).ko

unload:
	sudo rmmod $(TARGET_MODULE) || true >/dev/null

clean:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) clean