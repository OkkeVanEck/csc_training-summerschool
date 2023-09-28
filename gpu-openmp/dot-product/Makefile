ifeq ($(COMP),)
COMP=lumi
endif

ifeq ($(COMP),gnu)
FC=mpif90
CC=gcc
FCFLAGS=-O3 -Wall -fopenmp
CCFLAGS=-O3 -Wall -fopenmp
endif

ifeq ($(COMP),lumi)
FC=ftn
CC=cc
FCFLAGS=-O3 -fopenmp
CCFLAGS=-O3 -fopenmp
endif

all: base v1 v2


v0:
	$(FC) $(FCFLAGS) v0_dot-product.F90 -o v0.o

v1:
	$(FC) $(FCFLAGS) v1_target_dot-product.F90 -o v1.o

v2:
	$(FC) $(FCFLAGS) v2_parallel_dot-product.F90 -o v2.o

v3:
	$(FC) $(FCFLAGS) v3_simd_dot-product.F90 -o v3.o

v4:
	$(FC) $(FCFLAGS) v4_reduction_dot-product.F90 -o v4.o


.PHONY: clean
clean:
	-/bin/rm -f *.o *~
