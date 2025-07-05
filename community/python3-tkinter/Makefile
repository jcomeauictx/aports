SHELL := /bin/bash
ABUILD ?= $(shell which $(PWD)/../../../abuild/abuild abuild false | head -n 1)
ASH ?= $(shell which ash false | head -n 1) -ex
all:
	$(ASH) $(ABUILD) fetch verify
clean:
	rm -rf src
	rm -f Python-*.tar.xz
