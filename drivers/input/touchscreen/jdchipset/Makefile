ccflags-y += -DCONFIG_TOUCHSCREEN_JADARD_DEBUG=y
ccflags-y += -DCONFIG_TOUCHSCREEN_JADARD_SORTING=y

ifeq ($(TARGET_BUILD_VARIANT), user)
	ccflags-y += -D__JADARD_GKI__
endif

# Makefile for the Jadard touchscreen drivers.
ifeq ($(CONFIG_TOUCHSCREEN_JADARD_MODULE), y)
	obj-y += jadard_module.o
	obj-$(CONFIG_TOUCHSCREEN_JADARD_IC_JD9366T)     += jadard_ic_JD9366T.o
	obj-y += jadard_common.o jadard_platform.o
	obj-y += jadard_debug.o
	obj-y += jadard_sorting.o
	obj-$(CONFIG_JD_HID) += jadard_hid.o

else ifeq ($(CONFIG_TOUCHSCREEN_JADARD_MODULE), m)
	ccflags-y += -D__JADARD_KMODULE__

	jadard_touch-objs := jadard_module.o
	jadard_touch-objs += jadard_ic_JD9366T.o
	jadard_touch-objs += jadard_common.o jadard_platform.o
	jadard_touch-objs += jadard_debug.o
	jadard_touch-objs += jadard_sorting.o
	obj-m += jadard_touch.o

endif

CFLAGS_jadard_module.o := -Wno-comment
CFLAGS_jadard_ic_JD9366T.o := -Wno-comment
CFLAGS_jadard_common.o := -Wno-comment
CFLAGS_jadard_platform.o := -Wno-comment
CFLAGS_jadard_debug.o := -Wno-comment
CFLAGS_jadard_sorting.o := -Wno-comment
CFLAGS_jadard_touch.o := -Wno-comment
