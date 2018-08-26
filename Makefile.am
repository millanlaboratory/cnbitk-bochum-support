ACLOCAL_AMFLAGS=-I m4
SUBDIRS = desktop/ 	 \
		  gui/ 		 \
	  	  icons/ 	 \
	  	  images/ 	 \
		  launchers/ \
		  utilities/ 


REMOVE_DISTDIR = \
   { test ! -d "$(distdir)" \
   || { find "$(distdir)" -type d ! -perm -200 -exec chmod u+w {} ';' \
   && rm -fr "$(distdir)"; }; }

dist-deb: distdir
	am__cwd=`pwd` \
	&& cd $(distdir) \
	&& CFLAGS="$(CFLAGS)" CXXFLAGS="$(CXXFLAGS)" FFLAGS="$(FFLAGS)" \
	CPPFLAGS="$(CPPFLAGS)" LDFLAGS="$(LD    FLAGS)" dpkg-buildpackage \
	&& cd "$$am__cwd" 
	$(REMOVE_DISTDIR)
