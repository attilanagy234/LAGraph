#-------------------------------------------------------------------------------
# Test/SSSP/Makefile
#-------------------------------------------------------------------------------

# LAGraph, (... list all authors here) (c) 2019, All Rights Reserved.
# http://graphblas.org  See LAGraph/LICENSE for license.

#-------------------------------------------------------------------------------

# simple Makefile for LAGraph/Test/SSSP/sssp_test,

# relies on cmake to do the actual build.  Use the CMAKE_OPTIONS argument to
# this Makefile to pass options to cmake.

# Install LAGraph and GraphBLAS before trying to compile.

JOBS ?= 1

# build and run test
default: compile
	#./build/gap_sssp_test jagmesh7.mtx 3 > jagmesh7.out #2>stderr.txt
	#./build/gap_sssp_check jagmesh7.out jagmesh7.check
	./build/gap_sssp_test cover.mtx 3
	./build/gap_sssp_test_16 cover.mtx 3

# build test
compile:
	( cd build ; cmake $(CMAKE_OPTIONS) .. ; $(MAKE) --jobs=$(JOBS) )

# just run cmake; do not compile
cmake:
	( cd build ; cmake $(CMAKE_OPTIONS) .. ; )

clean: distclean

purge: distclean

# remove all files not in the distribution
distclean:
	rm -rf build/* stderr.txt gap_sssp_test sssp_check *.out

