rpmbuild_src = $(shell rpmbuild --eval '%{_sourcedir}')

.PHONY: prepare
prepare:
	dnf -y install rpmdevtools rpm-build scl-utils-build
	cp *.* $(rpmbuild_src)
	spectool -g -R $(spec)

.PHONY: srpm
srpm: prepare
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php74" $(spec)

.PHONY: rpm
rpm: prepare
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php74" $(spec)
