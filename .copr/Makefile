rpmbuild_src = $(shell rpmbuild --eval '%{_sourcedir}')

.PHONY: prepare
prepare:
	dnf -y install rpmdevtools rpm-build scl-utils-build
	cp *.* $(rpmbuild_src)
	spectool -g -R $(spec)

.PHONY: srpm
srpm: prepare
	rpmbuild -bs --define "_srcrpmdir $(outdir)" $(spec)
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php74" $(spec)
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php73" $(spec)
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php72" $(spec)
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php71" $(spec)
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php70" $(spec)
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php56" $(spec)
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php55" $(spec)
	rpmbuild -bs --define "_srcrpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php54" $(spec)

.PHONY: rpm
rpm: prepare
	rpmbuild -bb --define "_rpmdir $(outdir)" $(spec)
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php74" $(spec)
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php73" $(spec)
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php72" $(spec)
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php71" $(spec)
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php70" $(spec)
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php56" $(spec)
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php55" $(spec)
	rpmbuild -bb --define "_rpmdir $(outdir)" --define "scl_vendor remi" --define "_scl_prefix /opt/remi" --define "scl php54" $(spec)
