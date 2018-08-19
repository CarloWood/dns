noinst_LTLIBRARIES = libdns.la

bin_PROGRAMS = dns

libdns_la_SOURCES = dns.c
libdns_la_CFLAGS = -std=gnu99 -DDNS_DEBUG=2 -fstack-protector -Wall -Wextra

dns_SOURCES = dns.c
dns_CFLAGS = -std=gnu99 -DDNS_DEBUG=2 -DDNS_MAIN -fstack-protector -Wall -Wextra

# --------------- Maintainer's Section

if MAINTAINER_MODE
distclean-local:
	-rm -f dns

clean-local:
endif

MAINTAINERCLEANFILES = $(srcdir)/Makefile.in
