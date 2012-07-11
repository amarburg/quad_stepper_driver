GIT = git

PHONY: externs submodules pull push

submodules:
	@$(GIT) submodule init
	@$(GIT) submodule update

pull:
	@$(GIT) pull
	@$(GIT) submodule update

push:
	@$(GIT) push origin
	@cd libmaple && $(GIT) push origin

path:
	export PATH=$(LIB_MAPLE_HOME)/../arm/bin:$(PATH)


# Used to include chan-fat here but found it required some work, so simply 
# included in the code...
externs: arm ubuntu

CODE_SOURCERY_URL = http://static.leaflabs.com/pub/codesourcery/gcc-arm-none-eabi-latest-linux32.tar.gz

arm:
	mkdir -p packages
	cd packages && wget -N ${CODE_SOURCERY_URL}
	tar -xzvf packages/${notdir ${CODE_SOURCERY_URL}}

ubuntu: debian

debian:
	sudo apt-get install build-essential git-core wget screen dfu-util \
	                          openocd python python-serial


