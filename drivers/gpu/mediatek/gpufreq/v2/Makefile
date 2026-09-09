#
# Copyright (C) 2019 MediaTek Inc.
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License version 2 as
# published by the Free Software Foundation.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
# See http://www.gnu.org/licenses/gpl-2.0.html for more details.
#
ccflags-y += -I$(srctree)/include/
ccflags-y += -I$(srctree)/drivers/gpu/mediatek/gpufreq/v2/include/
ccflags-y += -I$(srctree)/drivers/gpu/mediatek/ged/include/
ccflags-y += -I$(srctree)/drivers/gpu/mediatek/gpueb/include/
ccflags-y += -I$(srctree)/drivers/gpu/mediatek/mt-plat/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/include/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/base/power/include/
ccflags-y += -I$(srctree)/drivers/clk/mediatek/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/power_throttling/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/pbm/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/aee/aed/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/include/mt-plat/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/include/leakage_table_v2/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/thermal/v2/inc/mach/
ccflags-y += -I$(srctree)/drivers/misc/mediatek/include/vcorefs_v3/

ccflags-y += \
	-Wno-unused-variable \
	-Wno-unused-function

ifeq ($(findstring aging,$(PROJECT_DTB_NAMES)),aging)
	ccflags-y += -DGPUFREQ_AGING_LOAD
endif

ifeq ($(CONFIG_MTK_GPU_MT6768_SUPPORT)$(CONFIG_MTK_GPU_MT6765_SUPPORT)$(CONFIG_MTK_GPU_MT6761_SUPPORT)$(CONFIG_MTK_GPU_MT6739_SUPPORT),)
ccflags-y += -DMTK_GPU_EB_SUPPORT
endif


mtk_gpufreq_wrapper-y := \
	gpufreq_v2.o \
	gpufreq_debug.o \
	gpu_misc.o

mtk_gpufreq_mt6879-y := \
	gpufreq_history_common.o \
	gpuppm.o \
	gpufreq_mt6879.o \
	gpudfd_mt6879.o

obj-$(CONFIG_MTK_GPU_SUPPORT) += mtk_gpufreq_wrapper.o
ifneq ($(wildcard $(srctree)/$(src)/gpufreq_mt6879.c),)
ifneq ($(wildcard $(srctree)/$(src)/gpudfd_mt6879.c),)
obj-$(CONFIG_MTK_GPU_MT6879_SUPPORT) += mtk_gpufreq_mt6879.o
endif
endif
