.PHONY: help clean prepare html web pickle htmlhelp latex changes linkcheck check-env

clean:
	-rm -rf build

build: check-env clean
	mkdir -p $(DESTDIR)/usr
	mkdir -p dist
	UV_THREADPOOL_SIZE=1 yarn install
	UV_THREADPOOL_SIZE=1 npm run build

install: build
	install -d $(DESTDIR)$(PACKAGE_DEST)
	cp -rT dist/ $(DESTDIR)$(PACKAGE_DEST)

check-env:
ifndef TARGET
    $(error TARGET is undefined)
endif
ifndef PACKAGE_DEST
    PACKAGE_DEST=/usr/lib/ui/webapp
endif
