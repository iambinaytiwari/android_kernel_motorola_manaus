# SPDX-License-Identifier: GPL-2.0

ifeq ($(CONFIG_MTK_GCOV_KERNEL),y)
GCOV_PROFILE := y
endif

ccflags-y += -I$(srctree)/drivers/misc/mediatek/include/
subdir-ccflags-$(CONFIG_MTK_ENG_BUILD) += -DDBG_ENABLE

obj-$(CONFIG_DEVAPC_ARCH_COMMON) += device-apc-common-legacy.o
device-apc-common-legacy-$(CONFIG_DEVAPC_ARCH_COMMON) += devapc-mtk-common.o

obj-$(CONFIG_DEVAPC_ARCH_MULTI) += device-apc-common.o
device-apc-common-$(CONFIG_DEVAPC_ARCH_MULTI) += devapc-mtk-multi-ao.o

ifneq ($(wildcard $(srctree)/$(src)/devapc-mt6879.c),)
obj-$(CONFIG_DEVAPC_MT6879) += device-apc-mt6879.o
device-apc-mt6879-$(CONFIG_DEVAPC_MT6879) += devapc-mt6879.o
endif
