dtb-$(CONFIG_ARCH_QCOM) += starqlte/sdm845-sec-starqlte-chn-r14.dtb \
	starqlte/sdm845-sec-starqlte-chn-r14_v2.1.dtb

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../%.dtb: $(src)/%.dts FORCE
        $(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(dtb-y))
endif
clean-files := *.dtb *.reverse.dts
