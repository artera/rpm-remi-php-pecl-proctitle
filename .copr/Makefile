rpmbuild_src = $(shell rpmbuild --eval '%{_sourcedir}')
php_version = php74

.PHONY: prepare
prepare:
	dnf -y install rpmdevtools rpm-build scl-utils-build
	cp *.* $(rpmbuild_src)
	spectool -g -R $(spec)

.PHONY: srpm
srpm: prepare
	sed -r '1 s/%define scl [^}]+/%define scl $(php_version)/' -i $(spec)
	rpmbuild -bs -D "_srcrpmdir $(outdir)" -D "scl_vendor remi" -D "_scl_prefix /opt/remi" -D "scl $(php_version)" $(spec)

.PHONY: rpm
rpm: prepare
	rpmbuild -bb -D "_rpmdir $(outdir)" -D "scl_vendor remi" -D "_scl_prefix /opt/remi" -D "scl $(php_version)" $(spec)
