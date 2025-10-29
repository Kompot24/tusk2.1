```
              
#    #  ####  
##  ## #    # 
# ## # #      
#    # #      
#    # #    # 
#    #  ####  
              
```
**Package**: mc  
**Version**: 3:4.8.26-1.1  
**Priority**: optional  
**Section**: utils  
**Maintainer**: Dmitry Smirnov <onlyjob@debian.org>  
**Installed-Size**: 1 528 kB  
**Provides**: mcedit  
**Depends**: libc6 (>= 2.15), libext2fs2 (>= 1.37), libglib2.0-0 (>= 2.59.2), libgpm2 (>= 1.20.7), libslang2 (>= 2.2.4), libssh2-1 (>= 1.2.8), mc-data (= 3:4.8.26-1.1)  
**Recommends**: mime-support, perl, unzip, sensible-utils  
**Suggests**: arj, bzip2, catdvi | texlive-binaries, dbview, djvulibre-bin, epub-utils, file, genisoimage, gv, imagemagick, libaspell-dev, links | w3m | lynx, odt2txt, poppler-utils, python, python-boto, python-tz, unar, wimtools, xpdf | pdf-viewer, zip  
**Homepage**: https://www.midnight-commander.org  
**Tag**: admin::filesystem, devel::lang:perl, devel::library, implemented-in::c,  
** implemented-in**::perl, interface::commandline, interface::text-mode,  
** role**::devel-lib, role::program, scope::application, suite::gnu,  
** uitoolkit**::ncurses, use::browsing, use::editing, use::organizing,  
** works-with**::archive, works-with::file  
**Download-Size**: 534 kB  
**APT-Manual-Installed**: yes  
**APT-Sources**: http://deb.debian.org/debian bullseye/main amd64 Packages  
**Description**: Midnight Commander - многофункциональный диспетчер файлов  
 GNU Midnight Commander – полноэкранный текстовый файловый менеджер.  
 В нём используется двухпанельный интерфейс и встроенная командная оболочка.  
 Также имеется встроенный редактор с подсветкой синтаксиса и просмотрщик,  
 поддерживающий двоичные файлы. Программа поддерживает виртуальную файловую  
 систему (VFS), что позволяет работать с файлами на удалённых машинах  
 (например, на серверах FTP, SSH) и с файлами внутри архивов,  
 как с обычными файлами.  
  
tree_mc
├── etc
│   └── mc
│       ├── edit.indent.rc
│       ├── filehighlight.ini
│       ├── mc.default.keymap
│       ├── mcedit.menu
│       ├── mc.emacs.keymap
│       ├── mc.ext
│       ├── mc.keymap -> mc.default.keymap
│       ├── mc.menu
│       └── sfs.ini
└── usr
    ├── bin
    │   ├── mc
    │   ├── mcdiff -> mc
    │   ├── mcedit -> mc
    │   └── mcview -> mc
    ├── lib
    │   └── mc
    └── share
        ├── applications
        ├── doc
        ├── lintian
        ├── mc
        └── pixmaps

12 directories, 13 files
#Файл preinst
#!/bin/sh
set -e
# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper rm_conffile /etc/mc/edit.spell.rc 3:4.8.5-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.charsets 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.lib 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/Syntax 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.menu.sr 3:4.8.17-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/cedit.menu /etc/mc/mcedit.menu 3:4.8-1 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.emacs /etc/mc/mc.emacs.keymap 3:4.8.8-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.default /etc/mc/mc.default.keymap 3:4.8.8-0 -- "$@"
# End automatically added section
#Файл postinst
#!/bin/sh
set -e

case "$1" in
	configure|abort-upgrade)
		update-alternatives --install /usr/bin/view view /usr/bin/mcview 25 \
			--slave /usr/share/man/man1/view.1.gz view.1.gz /usr/share/man/man1/mcview.1.gz
		update-alternatives --install /usr/bin/editor editor /usr/bin/mcedit 25 \
			--slave /usr/share/man/man1/editor.1.gz editor.1.gz /usr/share/man/man1/mcedit.1.gz
	;;
esac

# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper rm_conffile /etc/mc/edit.spell.rc 3:4.8.5-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.charsets 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.lib 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/Syntax 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.menu.sr 3:4.8.17-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/cedit.menu /etc/mc/mcedit.menu 3:4.8-1 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.emacs /etc/mc/mc.emacs.keymap 3:4.8.8-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.default /etc/mc/mc.default.keymap 3:4.8.8-0 -- "$@"
# End automatically added section

#Файл prerm
#!/bin/sh
set -e

case "$1" in
	remove)
		update-alternatives --remove editor /usr/bin/mcedit
		update-alternatives --remove view /usr/bin/mcview
	;;
esac

# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper rm_conffile /etc/mc/edit.spell.rc 3:4.8.5-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.charsets 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.lib 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/Syntax 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.menu.sr 3:4.8.17-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/cedit.menu /etc/mc/mcedit.menu 3:4.8-1 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.emacs /etc/mc/mc.emacs.keymap 3:4.8.8-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.default /etc/mc/mc.default.keymap 3:4.8.8-0 -- "$@"
# End automatically added section

#Файл postrm
#!/bin/sh
set -e

case "$1" in
	purge)

		rm -f \
			/etc/mc/cedit.menu \
			/etc/mc/*.ini \
			/etc/mc/mc.* \
			/etc/mc/*.rc \
			/etc/mc/Syntax

		rmdir /etc/mc 2>/dev/null || true

	;;
esac

# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper rm_conffile /etc/mc/edit.spell.rc 3:4.8.5-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.charsets 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.lib 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/Syntax 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.menu.sr 3:4.8.17-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/cedit.menu /etc/mc/mcedit.menu 3:4.8-1 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.emacs /etc/mc/mc.emacs.keymap 3:4.8.8-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.default /etc/mc/mc.default.keymap 3:4.8.8-0 -- "$@"
# End automatically added section

