#
# Copyright (c) 2017 Robert Quattlebaum
# Portions Copyright (c) 2016 Nest Labs, Inc.
# All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

AM_CPPFLAGS = \
	-I$(top_srcdir)/src \
	-I$(top_srcdir)/src/common \
	-I$(top_srcdir)/src/concordd \
    -I$(top_srcdir)/src/missing \
	$(NULL)

DISTCLEANFILES = .deps Makefile

bin_PROGRAMS = concordctl

concordctl_SOURCES = \
	concordctl.c \
	concordctl-utils.c \
	concordctl-utils.h \
	../common/config-file.c \
	../common/string-utils.c \
	concordctl-cmds.h \
	tool-cmd-arm.c tool-cmd-arm.h \
	tool-cmd-log.c tool-cmd-log.h \
    tool-cmd-keypad.c tool-cmd-keypad.h \
    tool-cmd-keypad-emu.c \
    tool-cmd-zone.c tool-cmd-zone.h \
    tool-cmd-light.c tool-cmd-light.h \
    tool-cmd-output.c tool-cmd-output.h \
    tool-cmd-system.c tool-cmd-system.h \
    tool-cmd-panic.c tool-cmd-panic.h \
    tool-cmd-refresh.c tool-cmd-refresh.h \
    tool-cmd-partition-info.c tool-cmd-partition-info.h \
	$(NULL)

concordctl_LDADD = \
	$(DBUS_LIBS) \
    $(MISSING_LIBADD) \
	$(LIBREADLINE_LIBS) \
	$(NULL)

concordctl_CPPFLAGS = \
	$(AM_CPPFLAGS) \
	$(DBUS_CFLAGS) \
    $(MISSING_CPPFLAGS) \
	$(LIBREADLINE_CPPFLAGS) \
	$(NULL)


SOURCE_VERSION=$(shell git describe --dirty --always --match "[0-9].*" 2> /dev/null)
BUILT_SOURCES  = $(top_builddir)/$(subdir)/version.c
CLEANFILES = $(top_builddir)/$(subdir)/version.c
.INTERMEDIATE: concordctl-version.$(OBJEXT)
$(top_builddir)/$(subdir)/version.c: ../version.c.in Makefile
	sed 's/SOURCE_VERSION/"$(SOURCE_VERSION)"/' < $< > $@
concordctl_SOURCES += $(top_builddir)/$(subdir)/version.c
