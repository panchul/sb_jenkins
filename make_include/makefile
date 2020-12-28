SHELL :=/bin/bash
APP_ROOT := $(PWD)
TMP_PATH := $(APP_ROOT)/.tmp
VENV_PATH := $(APP_ROOT)/.venv

export ENVIRONMENT_OVERRIDE_PATH ?= $(APP_ROOT)/env/makefile.override

.DEFAULT_GOAL := help 
help: # Show this help
	echo $(MAKEFILE_LIST)
	@egrep -h '\s#\s' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?# "}; {printf "\033[36m%-20s\033[0m %s\n", $$1, $$2}'

# will ignore if there is no such file to include
-include $(ENVIRONMENT_OVERRIDE_PATH)

include $(APP_ROOT)/targets/makefile.docker
include $(APP_ROOT)/targets/makefile.k8s

