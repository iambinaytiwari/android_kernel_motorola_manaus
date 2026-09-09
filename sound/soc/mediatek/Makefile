# SPDX-License-Identifier: GPL-2.0
obj-$(CONFIG_SND_SOC_MEDIATEK) += common/
ifneq ($(wildcard $(srctree)/sound/soc/mediatek/mt6879),)
obj-$(CONFIG_SND_SOC_MT6879) += mt6879/
endif

# vow related code
obj-$(CONFIG_MTK_VOW_SUPPORT) += vow/

# audio sound dsp related code
obj-$(CONFIG_SND_SOC_MTK_AUDIO_DSP) += audio_dsp/

#scp ultra sound related code
obj-$(CONFIG_MTK_ULTRASND_PROXIMITY) += ultrasound/

obj-$(CONFIG_MTK_SCP_AUDIO) += audio_scp/

# include path
subdir-ccflags-y += -Werror -I$(srctree)/drivers/misc/mediatek/include/mt-plat
subdir-ccflags-y += -Werror -I$(srctree)/drivers/misc/mediatek/include

# New architecture
ifeq ($(CONFIG_MTK_SND_SOC_NEW_ARCH),y)
obj-$(CONFIG_SND_SOC_MTK_BTCVSD) += common/
# flags for not ready feature, uncomment after ready
subdir-ccflags-y += -DAUDIO_USING_WRAP_DRIVER
subdir-ccflags-y += -D_MT_IDLE_HEADER
subdir-ccflags-y += -D_REG_SYNC_WRITE
# PMIC include path
ifeq ($(CONFIG_MTK_SND_SOC_NEW_ARCH),y)
subdir-ccflags-y += -I$(srctree)/sound/soc/mediatek/codec
# AP include path
subdir-ccflags-y += -I$(srctree)/sound/soc/mediatek/common_int

ifeq ($(CONFIG_SND_SOC_MT6739),m)
subdir-ccflags-y += -I$(srctree)/sound/soc/mediatek/mt6739
else
subdir-ccflags-y += -I$(srctree)/sound/soc/mediatek/mt6765
endif

subdir-ccflags-y += -Wno-incompatible-pointer-types
endif
# Update pmic built flow to avoid codec init later than codec probe
obj-$(CONFIG_MTK_SND_SOC_NEW_ARCH_COMMON) += codec/
obj-$(CONFIG_MTK_SND_SOC_NEW_ARCH_COMMON) += common_int/
obj-$(CONFIG_SND_SOC_MT6765) += mt6765/
endif