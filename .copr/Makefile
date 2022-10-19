rpmbuild_src = $(shell rpmbuild --eval '%{_sourcedir}')
dnf -y install https://repo.almalinux.org/almalinux/9/AppStream/x86_64/os/Packages/scl-utils-build-2.0.3-2.el9.x86_64.rpm

.PHONY: prepare
prepare:
	dnf -y install rpmdevtools rpm-build scl-utils-build
	cp *.* $(rpmbuild_src)
	sed -r '1 s;global scl [^}]+;global scl php80;' -i $(spec)
	spectool -g -R $(spec)

.PHONY: srpm
srpm: prepare
	rpmbuild -bs -D "_srcrpmdir $(outdir)" $(spec)

.PHONY: rpm
rpm: prepare
	rpmbuild -bb -D "_rpmdir $(outdir)" $(spec)
