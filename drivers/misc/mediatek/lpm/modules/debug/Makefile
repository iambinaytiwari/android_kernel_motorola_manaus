# common KOs
obj-$(CONFIG_MTK_LOW_POWER_MODULE) += v1/

# platform dependent  KOs

ifeq ($(CONFIG_MTK_LPM_MT6879),m)
ifneq ($(wildcard $(srctree)/$(src)/mt6879),)
obj-$(CONFIG_MTK_LPM_MT6879) += mt6879/
endif
endif