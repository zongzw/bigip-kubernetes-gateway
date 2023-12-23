release:
ifndef version
	$(error 'version' not defined, i.e, version=v0.3.0)
endif
	make -C controller upload
	make -C webhook upload