SHELL := /bin/bash
ABUILD ?= $(shell which abuild $(PWD)/../../../abuild/abuild false | head -n 1)
ASH ?= $(shell which ash false | head -n 1) -x
all:
	$(ASH) $(ABUILD) fetch verify
