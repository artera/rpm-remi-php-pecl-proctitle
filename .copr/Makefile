rpmbuild_src = $(shell rpmbuild --eval '%{_sourcedir}')

.PHONY: prepare
prepare:
	dnf -y install rpmdevtools rpm-build
	cp *.* $(rpmbuild_src)
	sed '1 s;^;%define scl php74\n;' -i $(spec)
	spectool -g -R $(spec)

.PHONY: srpm
srpm: prepare
	rpmbuild -bs -D "_srcrpmdir $(outdir)" $(spec)

.PHONY: rpm
rpm: prepare
	rpmbuild -bb -D "_rpmdir $(outdir)" $(spec)
