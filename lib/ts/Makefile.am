# libts Makefile.am
#
#  Licensed to the Apache Software Foundation (ASF) under one
#  or more contributor license agreements.  See the NOTICE file
#  distributed with this work for additional information
#  regarding copyright ownership.  The ASF licenses this file
#  to you under the Apache License, Version 2.0 (the
#  "License"); you may not use this file except in compliance
#  with the License.  You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
#  Unless required by applicable law or agreed to in writing, software
#  distributed under the License is distributed on an "AS IS" BASIS,
#  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#  See the License for the specific language governing permissions and
#  limitations under the License.

library_includedir=$(includedir)/ts

library_include_HEADERS = apidefs.h

noinst_PROGRAMS = mkdfa CompileParseRules
check_PROGRAMS = test_arena test_atomic test_freelist test_geometry test_List test_Map test_Regex test_Vec
TESTS = $(check_PROGRAMS)

AM_CPPFLAGS = -I$(top_srcdir)/lib

lib_LTLIBRARIES = libtsutil.la

libtsutil_la_LDFLAGS = -no-undefined -version-info @TS_LIBTOOL_VERSION@
libtsutil_la_LIBADD = \
  @HWLOC_LIBS@ \
  @LIBOBJS@ \
  @LIBPCRE@ \
  @OPENSSL_LIBS@ \
  @LIBTCL@ \
  @LIBRESOLV@ \
  @LIBCAP@ \
  -lc

libtsutil_la_SOURCES = \
  Allocator.h \
  Arena.cc \
  Arena.h \
  Bitops.cc \
  Bitops.h \
  ConsistentHash.cc \
  ConsistentHash.h \
  Cryptohash.h \
  Diags.cc \
  Diags.h \
  DynArray.h \
  EventNotify.cc \
  EventNotify.h \
  Hash.cc \
  Hash.h \
  HashFNV.cc \
  HashFNV.h \
  HashMD5.cc \
  HashMD5.h \
  HashSip.cc \
  HashSip.h \
  HostLookup.cc \
  HostLookup.h \
  INK_MD5.h \
  I_Layout.h \
  I_Version.h \
  InkErrno.h \
  InkPool.h \
  IntrusiveDList.h \
  IpMap.cc \
  IpMap.h \
  IpMapConf.cc \
  IpMapConf.h \
  Layout.cc \
  List.h \
  MMH.cc \
  MMH.h \
  Map.h \
  MatcherUtils.cc \
  MatcherUtils.h \
  MimeTable.cc \
  MimeTable.h \
  ParseRules.cc \
  ParseRules.h \
  Ptr.h \
  RawHashTable.cc \
  RawHashTable.h \
  RbTree.cc \
  RbTree.h \
  Regex.cc \
  Regex.h \
  Regression.cc \
  Regression.h \
  SimpleTokenizer.h \
  TestBox.h \
  TextBuffer.cc \
  TextBuffer.h \
  Tokenizer.cc \
  Tokenizer.h \
  Trie.h \
  TsBuffer.h \
  Vec.cc \
  Vec.h \
  Version.cc \
  defalloc.h \
  fastlz.c \
  fastlz.h \
  ink_aiocb.h \
  ink_align.h \
  ink_apidefs.h \
  ink_args.cc \
  ink_args.h \
  ink_assert.cc \
  ink_assert.h \
  ink_atomic.h \
  ink_auth_api.cc \
  ink_auth_api.h \
  ink_base64.cc \
  ink_base64.h \
  ink_cap.cc \
  ink_cap.h \
  ink_code.cc \
  ink_code.h \
  ink_defs.cc \
  ink_defs.h \
  ink_error.cc \
  ink_error.h \
  ink_exception.h \
  ink_file.cc \
  ink_file.h \
  ink_hash_table.cc \
  ink_hash_table.h \
  ink_hrtime.cc \
  ink_hrtime.h \
  ink_inet.cc \
  ink_inet.h \
  ink_inout.h \
  ink_llqueue.h \
  ink_lockfile.h \
  ink_memory.cc \
  ink_memory.h \
  ink_mutex.cc \
  ink_mutex.h \
  ink_platform.h \
  ink_queue.cc \
  ink_queue.h \
  ink_queue_ext.cc \
  ink_queue_ext.h \
  ink_queue_utils.cc \
  ink_rand.cc \
  ink_rand.h \
  ink_res_init.cc \
  ink_res_mkquery.cc \
  ink_resolver.h \
  ink_resource.cc \
  ink_resource.h \
  ink_rwlock.cc \
  ink_rwlock.h \
  ink_sock.cc \
  ink_sock.h \
  ink_sprintf.cc \
  ink_sprintf.h \
  ink_stack_trace.cc \
  ink_stack_trace.h \
  ink_string++.cc \
  ink_string++.h \
  ink_string.cc \
  ink_string.h \
  ink_sys_control.cc \
  ink_sys_control.h \
  ink_syslog.cc \
  ink_syslog.h \
  ink_thread.cc \
  ink_thread.h \
  ink_time.cc \
  ink_time.h \
  libts.h \
  llqueue.cc \
  lockfile.cc \
  signals.cc \
  signals.h

#test_UNUSED_SOURCES = \
#  load_http_hdr.cc \
#  IntrusivePtrTest.cc \
#  IpMapTest.cc \
#  TestHttpHeader.cc \
#  test_memchr.cc \
#  test_strings.cc

# Special hacks to generate the parser rules
$(srcdir)/ParseRules.cc: ParseRulesCType

ParseRulesCType: CompileParseRules
	./CompileParseRules

mkdfa_SOURCES = mkdfa.c

test_atomic_SOURCES = test_atomic.cc
test_atomic_LDADD = libtsutil.la @LIBTCL@ @LIBPCRE@
test_atomic_LDFLAGS = @EXTRA_CXX_LDFLAGS@ @LIBTOOL_LINK_FLAGS@

test_freelist_SOURCES = test_freelist.cc
test_freelist_LDADD = libtsutil.la @LIBTCL@ @LIBPCRE@
test_freelist_LDFLAGS = @EXTRA_CXX_LDFLAGS@ @LIBTOOL_LINK_FLAGS@

test_arena_SOURCES = test_arena.cc
test_arena_LDADD = libtsutil.la @LIBTCL@ @LIBPCRE@
test_arena_LDFLAGS = @EXTRA_CXX_LDFLAGS@ @LIBTOOL_LINK_FLAGS@

test_List_SOURCES = test_List.cc
test_Map_SOURCES = test_Map.cc
test_Map_LDADD = libtsutil.la @LIBTCL@ @LIBPCRE@
test_Map_LDFLAGS = @EXTRA_CXX_LDFLAGS@ @LIBTOOL_LINK_FLAGS@

test_Regex_SOURCES = test_Regex.cc
test_Regex_LDADD = libtsutil.la @LIBTCL@ @LIBPCRE@
test_Regex_LDFLAGS = @EXTRA_CXX_LDFLAGS@ @LIBTOOL_LINK_FLAGS@

test_Vec_SOURCES = test_Vec.cc
test_Vec_LDADD = libtsutil.la @LIBTCL@ @LIBPCRE@
test_Vec_LDFLAGS = @EXTRA_CXX_LDFLAGS@ @LIBTOOL_LINK_FLAGS@

test_geometry_SOURCES = test_geometry.cc
test_geometry_LDADD = libtsutil.la @LIBTCL@ @LIBPCRE@
test_geometry_LDFLAGS = @EXTRA_CXX_LDFLAGS@ @LIBTOOL_LINK_FLAGS@

CompileParseRules_SOURCES = CompileParseRules.cc

test:: $(TESTS)
	for f in $(TESTS) ; do $$f ; done

#$(foreach F, $(TESTS), $(shell $F))

clean-local:
	rm -f ParseRulesCType ParseRulesCTypeToLower ParseRulesCTypeToUpper
