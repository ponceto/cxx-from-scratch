#
# Makefile - Copyright (c) 2022-2023 - Olivier Poncet
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.
#

# ----------------------------------------------------------------------------
# global environment
# ----------------------------------------------------------------------------

FLAGS    = -g -O2 -Wall
CC       = gcc
CFLAGS   = -std=c99 $(FLAGS)
CXX      = g++
CXXFLAGS = -std=c++14 $(FLAGS)
CPPFLAGS = -I.
LD       = g++
LDFLAGS  = -L.
CP       = cp
CPFLAGS  = -f
RM       = rm
RMFLAGS  = -f

# ----------------------------------------------------------------------------
# default rules
# ----------------------------------------------------------------------------

.c.o :
	$(CC) -c $(CFLAGS) $(CPPFLAGS) $<

.cc.o :
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) $<

# ----------------------------------------------------------------------------
# global targets
# ----------------------------------------------------------------------------

all : build

build : build_program
	@echo "=== $@ ok ==="

clean : clean_program
	@echo "=== $@ ok ==="

# ----------------------------------------------------------------------------
# the project
# ----------------------------------------------------------------------------

PROGRAM_BIN = program.bin

PROGRAM_SRCS = \
	main.cc \
	$(NULL)

PROGRAM_HDRS = \
	main.h \
	$(NULL)

PROGRAM_OBJS = \
	main.o \
	$(NULL)

PROGRAM_LIBS = \
	-lpthread -lm \
	$(NULL)

build_program : $(PROGRAM_BIN)

clean_program :
	$(RM) $(RMFLAGS) $(PROGRAM_OBJS) $(PROGRAM_BIN)

$(PROGRAM_BIN) : $(PROGRAM_OBJS)
	$(LD) $(LDFLAGS) -o $(PROGRAM_BIN) $(PROGRAM_OBJS) $(PROGRAM_LIBS)

# ----------------------------------------------------------------------------
# dependencies
# ----------------------------------------------------------------------------

main.o : main.cc main.h

# ----------------------------------------------------------------------------
# End-Of-File
# ----------------------------------------------------------------------------
