rpmbuild_src = $(shell rpmbuild --eval '%{_sourcedir}')

.PHONY: prepare
prepare:
	dnf -y install rpmdevtools rpm-build scl-utils-build
	cp *.* $(rpmbuild_src)
	sed -r '1 s;global scl [^}]+;global scl php70;' -i $(spec)
	spectool -g -R $(spec)

.PHONY: srpm
srpm: prepare
	rpmbuild -bs -D "_srcrpmdir $(outdir)" $(spec)

.PHONY: rpm
rpm: prepare
	rpmbuild -bb -D "_rpmdir $(outdir)" $(spec)
