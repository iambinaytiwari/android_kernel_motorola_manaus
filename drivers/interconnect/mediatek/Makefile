# SPDX-License-Identifier: GPL-2.0

ccflags-y += -I$(srctree)/drivers/iommu
ccflags-y += -I$(srctree)/drivers/misc/mediatek/mtk-interconnect
ccflags-y += -I$(srctree)/drivers/misc/mediatek/qos
obj-$(CONFIG_INTERCONNECT_MTK_EMI) += mtk-emi.o
obj-$(CONFIG_INTERCONNECT_MTK_MMQOS_COMMON) += mmqos-common.o
ifneq ($(filter y m,$(CONFIG_MTK_ECCCI_DRIVER)),)
obj-$(CONFIG_INTERCONNECT_MTK_MMQOS_COMMON) += mmqos-md.o
endif
ccflags-y += -I$(srctree)/drivers/misc/mediatek/mmdvfs
ccflags-y += -I$(srctree)/drivers/misc/mediatek/include/mt-plat
mmqos-common-objs += mmqos-mtk.o mmqos-hrt.o
ifneq ($(wildcard $(srctree)/$(src)/mmqos-mt6879.c),)
obj-$(CONFIG_INTERCONNECT_MTK_MMQOS_MT6879) += mmqos-mt6879.o
endif
