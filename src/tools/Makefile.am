ceph_osdomap_tool_SOURCES = tools/ceph_osdomap_tool.cc
ceph_osdomap_tool_LDADD = $(LIBOS) $(CEPH_GLOBAL) $(BOOST_PROGRAM_OPTIONS_LIBS)
bin_DEBUGPROGRAMS += ceph-osdomap-tool

ceph_monstore_tool_SOURCES = tools/ceph_monstore_tool.cc
ceph_monstore_tool_LDADD = $(LIBOS) $(CEPH_GLOBAL) $(BOOST_PROGRAM_OPTIONS_LIBS)
bin_DEBUGPROGRAMS += ceph-monstore-tool

ceph_kvstore_tool_SOURCES = tools/ceph_kvstore_tool.cc
ceph_kvstore_tool_LDADD = $(LIBOS) $(CEPH_GLOBAL)
ceph_kvstore_tool_CXXFLAGS = $(UNITTEST_CXXFLAGS)
bin_DEBUGPROGRAMS += ceph-kvstore-tool


ceph_filestore_tool_SOURCES = tools/ceph_filestore_tool.cc
ceph_filestore_tool_LDADD = $(LIBOSD) $(LIBOS) $(CEPH_GLOBAL) -lboost_program_options
if LINUX
ceph_filestore_tool_LDADD += -ldl
endif # LINUX
bin_PROGRAMS += ceph_filestore_tool

ceph_filestore_dump_SOURCES = tools/ceph_filestore_dump.cc
ceph_filestore_dump_LDADD = $(LIBOSD) $(LIBOS) $(CEPH_GLOBAL) $(BOOST_PROGRAM_OPTIONS_LIBS)
if LINUX
ceph_filestore_dump_LDADD += -ldl
endif # LINUX
bin_PROGRAMS += ceph_filestore_dump

monmaptool_SOURCES = tools/monmaptool.cc
monmaptool_LDADD = $(CEPH_GLOBAL) $(LIBCOMMON)
bin_PROGRAMS += monmaptool

crushtool_SOURCES = tools/crushtool.cc
crushtool_LDADD = $(CEPH_GLOBAL)
bin_PROGRAMS += crushtool

osdmaptool_SOURCES = tools/osdmaptool.cc
osdmaptool_LDADD = $(CEPH_GLOBAL)
bin_PROGRAMS += osdmaptool

ceph_scratchtool_SOURCES = tools/scratchtool.c
ceph_scratchtool_LDADD = $(LIBRADOS) $(CEPH_GLOBAL)
bin_DEBUGPROGRAMS += ceph_scratchtool

ceph_scratchtoolpp_SOURCES = tools/scratchtoolpp.cc
ceph_scratchtoolpp_LDADD = $(LIBRADOS) $(CEPH_GLOBAL)
bin_DEBUGPROGRAMS += ceph_scratchtoolpp

ceph_psim_SOURCES = tools/psim.cc
ceph_psim_LDADD = $(CEPH_GLOBAL)
bin_DEBUGPROGRAMS += ceph_psim

ceph_dupstore_SOURCES = tools/dupstore.cc
ceph_dupstore_LDADD = $(LIBOS) $(CEPH_GLOBAL)
bin_DEBUGPROGRAMS += ceph_dupstore

ceph_radosacl_SOURCES = tools/radosacl.cc
ceph_radosacl_LDADD = $(LIBRADOS) $(CEPH_GLOBAL)
bin_DEBUGPROGRAMS += ceph_radosacl

rados_SOURCES = \
	tools/rados/rados.cc \
	tools/rados/rados_import.cc \
	tools/rados/rados_export.cc \
	tools/rados/rados_sync.cc
rados_SOURCES += common/obj_bencher.cc # needs cleanup so it can go in libcommon.la
rados_LDADD = libcls_lock_client.la $(LIBRADOS) $(CEPH_GLOBAL)
bin_PROGRAMS += rados

if WITH_REST_BENCH
rest_bench_SOURCES = tools/rest_bench.cc
rest_bench_SOURCES += common/obj_bencher.cc # needs cleanup so it can go in libcommon.la
rest_bench_LDADD = $(CEPH_GLOBAL)
bin_PROGRAMS += rest-bench

if WITH_SYSTEM_LIBS3
rest_bench_LDADD += -ls3
else
rest_bench_LDADD += libs3/build/lib/libs3.a -lcurl -lxml2
rest_bench_CXXFLAGS = ${AM_CXXFLAGS} -I$(top_srcdir)/src/libs3/inc
SUBDIRS += libs3
endif # WITH_SYSTEM_LIBS3
endif # WITH_REST_BENCH

ceph_conf_SOURCES = tools/ceph_conf.cc
ceph_conf_LDADD = $(CEPH_GLOBAL) $(LIBCOMMON)
bin_PROGRAMS += ceph-conf

ceph_authtool_SOURCES = tools/ceph_authtool.cc
ceph_authtool_LDADD = $(CEPH_GLOBAL) $(LIBCOMMON)
bin_PROGRAMS += ceph-authtool

ceph_mon_store_converter_SOURCES = tools/mon_store_converter.cc
ceph_mon_store_converter_LDADD = $(LIBMON) $(LIBOS) $(CEPH_GLOBAL)
bin_PROGRAMS += ceph_mon_store_converter

noinst_HEADERS += \
	tools/rados/rados_sync.h \
	tools/common.h

