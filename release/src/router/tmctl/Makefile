
#GLOBAL_RELEASE_SCRIPT_NOTOUCH

ifneq ($(wildcard Makefile.fullsrc),)

include Makefile.fullsrc

else

EXE = tmctl
dynamic: generic_exe_install

clean:
	rm -f $(EXE)

ifneq ($(PREBUILT_BCMBIN),1)
tmctl:
	cp $(EXE)_$(PROFILE).save $(EXE)
else
$(EXE): 
	-cp -f $(TOP)/$(shell pwd | sed 's/\(.*router\/\)//')/$(PRBM_DIR)/$@ ./
endif

#
# Set our CommEngine directory (by splitting the pwd into two words
# at /userspace and taking the first word only).
# Then include the common defines under CommEngine.
#

CURR_DIR := $(shell pwd)
BUILD_DIR:=$(HND_SRC)

include $(BUILD_DIR)/make.common
endif
