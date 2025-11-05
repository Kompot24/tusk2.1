```
               
 ####  # ##### 
#    # #   #   
#      #   #   
#  ### #   #   
#    # #   #   
 ####  #   #   
               
```
**Package**: git  
**Version**: 1:2.30.2-1+deb11u5  
**Priority**: optional  
**Section**: vcs  
**Maintainer**: Jonathan Nieder <jrnieder@gmail.com>  
**Installed-Size**: 36,1 MB  
**Provides**: git-completion, git-core  
**Depends**: libc6 (>= 2.28), libcurl3-gnutls (>= 7.56.1), libexpat1 (>= 2.0.1), libpcre2-8-0 (>= 10.22), zlib1g (>= 1:1.2.0), perl, liberror-perl, git-man (>> 1:2.30.2), git-man (<< 1:2.30.2-.)  
**Recommends**: ca-certificates, patch, less, ssh-client  
**Suggests**: gettext-base, git-daemon-run | git-daemon-sysvinit, git-doc, git-el, git-email, git-gui, gitk, gitweb, git-cvs, git-mediawiki, git-svn  
**Breaks**: bash-completion (<< 1:1.90-1), cogito (<= 0.18.2+), dgit (<< 5.1~), git-buildpackage (<< 0.6.5), git-core (<< 1:1.7.0.4-1.), gitosis (<< 0.2+20090917-7), gitpkg (<< 0.15), gitweb (<< 1:1.7.4~rc1), guilt (<< 0.33), openssh-client (<< 1:6.8), stgit (<< 0.15), stgit-contrib (<< 0.15)  
**Replaces**: git-core (<< 1:1.7.0.4-1.), gitweb (<< 1:1.7.4~rc1)  
**Homepage**: https://git-scm.com/  
**Download-Size**: 5 568 kB  
**APT-Sources**: http://deb.debian.org/debian-security bullseye-security/updates/main amd64 Packages  
**Description**: масштабируемая распределённая система контроля версий  
 Git — это популярная система контроля версий, предназначенная для быстрой и  
 эффективной работы над очень большими проектами; используется многими  
 проектами с открытым исходным кодом, самым заметным из которых является  
 ядро Linux.  
 .  
** Git является распределённой системой контроля версий**: для работы с ней не  
 нужен центральный сервер. Репозитории хранятся локально полностью, со всей  
 историей изменений, а соединение с центральным сервером (если такой  
 имеется) нужно только для публикации своих изменений и загрузки изменений  
 опубликованных другими (т.е. для синхронизации удалённого и локального  
 репозиториев).  
 .  
 Этот пакет устанавливает основные компоненты git. Дополнительные  
 компоненты, такие как графический интерфейс пользователя и утилита для  
 наглядного представления дерева версий, утилиты для организации  
 взаимодействия с другими системами контроля версий и веб-интерфейс,  
 доступны в отдельных пакетах git*.  
  
# Структура пакета
```
tree_git [error opening dir]

0 directories, 0 files
```
# Файл preinst
```
```
# Файл postinst
```
```
# Файл prerm
```
```
# Файл postrm
```
```
