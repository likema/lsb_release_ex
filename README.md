=====================
lsb_release_ex
=====================

LSB release detection module for Debian/Ubuntu and Red Hat.

Ehanced Linux Standard Base version reporting module for Debian/Ubuntu and
Red Hat series. It is inspired by Debian implementaion in lsb-release.

Installation
===============

Download the latest version from github:

	git clone git://github.com/likema/lsb_release_ex.git
	cd lsb_release_ex
	python setup.py install

Usage
===============

The sample runs just like

	lsb_release -a

in Debian/Ubuntu.

```python
import lsb_release_ex

distinfo = lsb_release_ex.get_distro_information()
verinfo = lsb_release_ex.check_modules_installed()

print '''LSB Version:    %s
Distributor ID: %s
Description:    %s
Release:        %s
Codename:       %s''' % (":".join(verinfo) if verinfo else None,
                         distinfo.get("ID"),
                         distinfo.get("DESCRIPTION"),
                         distinfo.get("RELEASE"),
                         distinfo.get("CODENAME"))
```
