if HAVE_MANPAGES
BUILT_SOURCES = \
    build_manpages \
    $(NULL)

man_MANS = \
    authselect.8 \
    authselect-profiles.5 \
    authselect-migration.7 \
    $(NULL)

build_manpages:
	./build.sh $(prefix) $(exec_prefix)

.PHONY: expand_files

MAN_FILES = $(shell find $(srcdir) -maxdepth 1 -type f -name '*.adoc' -printf '%d\t%p\n' | sort -nk1 | cut -f2-) 
MAN_PO = $(shell find $(srcdir)/po -maxdepth 1 -type f -name '*.po' -printf '%d\t%p\n' | sort -nk1 | cut -f2-)

EXTRA_DIST = \
    $(MAN_FILES) \
    $(MAN_PO) \
    $(NULL)

clean-local:
	for FILE in $(man_MANS) ; do \
		$(RM) $$FILE $$FILE.txt ; \
	done ; \
	$(RM) build.stamp

endif