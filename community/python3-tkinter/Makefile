SHELL := /bin/bash
ABUILD ?= $(shell which abuild $(PWD)/../../../abuild/abuild false | head -n 1)
all:
	$(ABUILD) fetch verify
