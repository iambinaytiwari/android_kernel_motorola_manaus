ccflags-y += -I$(srctree)/include/linux/soc/mediatek/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/dcm/include/

# Core
obj-$(CONFIG_MTK_DCM_COMMON)	+= mtk_dcm.o

# SoC Drivers
ifneq ($(wildcard $(srctree)/$(src)/mt6879_dcm_autogen.c),)
obj-$(CONFIG_MTK_DCM_MT6879) += mt6879_dcm.o
mt6879_dcm-objs := mt6879_dcm_internal.o mt6879_dcm_autogen.o
endif
