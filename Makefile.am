cfgdir 			= $(datadir)/vyatta-cfg/templates
opdir 			= $(datadir)/vyatta-op/templates
curverdir 		= $(sysconfdir)/config-migrate/current
bin_sudo_usersdir 	= $(bindir)/sudo-users
initddir		= /etc/init.d

initd_SCRIPTS		= etc/init.d/opennhrp.init

vprefix = /opt/vyatta
vsbindir = $(vprefix)/sbin

sbin_SCRIPTS = scripts/vyos-update-nhrp.pl

bin_sudo_users_SCRIPTS =

curver_DATA = 

cpiop = find  . ! -regex '\(.*~\|.*\.bak\|.*\.swp\|.*\#.*\#\)' -print0 | \
  cpio -0pd

install-exec-hook:
	mkdir -p $(DESTDIR)$(cfgdir)
	cd templates-cfg; $(cpiop) $(DESTDIR)$(cfgdir)
	mkdir -p $(DESTDIR)$(opdir)
	cd templates-op; $(cpiop) $(DESTDIR)$(opdir)
	mkdir -p $(DESTDIR)/etc/
