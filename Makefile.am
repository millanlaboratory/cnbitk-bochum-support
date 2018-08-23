ACLOCAL_AMFLAGS=-I m4
#SUBDIRS = src/ \
#		  extra/ \
#	  	  gui/ \
#	  	  python/Feedback/

# Removed src/ for the time being (using python feedback)
		  
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
