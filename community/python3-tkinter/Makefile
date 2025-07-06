SHELL := /bin/bash
BUILDER := $(shell git config user.email)
ABUILD_KEYS := $(wildcard /etc/apk/keys/$(BUILDER)-*.rsa.pub)
ABUILD_KEYS += $(wildcard $(HOME)/.abuild/$(BUILDER)-*rsa.pub)
ABUILD ?= $(shell which $(PWD)/../../../abuild/abuild abuild false | head -n 1)
BINDIR ?= $(dir $(ABUILD))
ASH ?= $(shell which ash false | head -n 1) -ex
APK ?= $(wildcard ../../../apk-tools/src/apk)
LD_LIBRARY_PATH := $(dir $(APK))
ifneq ($(SHOWENV),)
	export
else
	export APK
endif
all: signkey
	$(ASH) $(ABUILD) fetch verify checksum
	$(ASH) $(ABUILD) -r
signkey: 
	if [ "$(ABUILD_KEYS)" = "" ]; then $(BINDIR)/abuild-keygen -a -i; fi
clean:
	rm -rf src
	rm -f Python-*.tar.xz
env:
ifneq ($(SHOWENV),)
	$@
else
	$(MAKE) SHOWENV=1 $@
endif
