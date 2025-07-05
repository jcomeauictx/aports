SHELL := /bin/bash
ABUILD_KEY ?= $(wildcard $HOME/.abuild/*.key)
ABUILD ?= $(shell which $(PWD)/../../../abuild/abuild abuild false | head -n 1)
BINDIR ?= $(dir $(ABUILD))
ASH ?= $(shell which ash false | head -n 1) -ex
all: signkey
	$(ASH) $(ABUILD) fetch verify checksum
	$(ASH) $(ABUILD) -r
signkey: 
	if [ "$(ABUILD_KEY)" = "" ]; then $(BINDIR)/abuild-keygen -a -i; fi
clean:
	rm -rf src
	rm -f Python-*.tar.xz
