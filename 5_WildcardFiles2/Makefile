# CC: Program for compiling C programs; default cc
# CXX: Program for compiling C++ programs; default g++
# CFLAGS: Extra flags to give to the C compiler
# CXXFLAGS: Extra flags to give to the C++ compiler
# CPPFLAGS: Extra flags to give to the C preprocessor
# LDFLAGS: Extra flags to give to the linker
DEBUG = 1
EXECUTABLE_NAME = main

CXX_STANDARD = c++17
CXX_WARNINGS = -Wall -Wextra -Wpedantic
CXX = g++
CXXFLAGS =  $(CXX_WARNINGS) -std=$(CXX_STANDARD)
LDFLAGS = 
ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
EXECUTABLE_NAME = mainDebug
else
CXXFLAGS += -O3
EXECUTABLE_NAME = mainRelease
endif

CXX_COMPILER_CALL = $(CXX) $(CXXFLAGS)

CXX_SOURCE = $(wildcard *.cc)
# pattern : $(text: pattern = replacement)
CXX_OBJECTS = $(patsubst %.cc, %.o, $(CXX_SOURCE))
build: $(CXX_OBJECTS)
	@echo $(CXX_SOURCE)
	$(CXX_COMPILER_CALL) $(CXX_OBJECTS) $(LDFLAGS) -o $(EXECUTABLE_NAME)
execute:
	./$(EXECUTABLE_NAME)
clean:
	rm -f *.o
	rm -f $(EXECUTABLE_NAME)
##############
## PATTERNS ##
##############
# $@: the file name of the target
# $<: the name of the first ependency
# $^: the names of all prerequisites
%.o: %.cc
	$(CXX_COMPILER_CALL) -c $< -o $@
