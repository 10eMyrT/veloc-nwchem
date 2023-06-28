#
# $Id$
#
#
ifdef USE_VELOC
    ifneq ($(USE_VELOC),y)
        $(error USE_VELOC should be defined as y)
    endif
    OBJ=veloc_module.o veloc_wrapper.o sp_init.o sp_main.o
else
    OBJ=sp_init.o sp_main.o
endif

LIBRARY=libspace.a

HEADER=

USES_BLAS=

include ../config/makefile.h

include ../config/makelib.h
