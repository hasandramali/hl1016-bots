# Makefile for PODBot on Linux

# Compiler and linker
CXX = g++
CXXFLAGS = -m32 -O2 -Wall -Wextra -I../dlls -I../engine -I../utils/common -I../cl_dll -DTRUE=1 -DFALSE=0 -include cstring -D_GLIBCXX_USE_CXX11_ABI=0
LDFLAGS = -m32 -shared -static-libgcc -static-libstdc++ -Wl,-z,noexecstack
TARGET = podbot.so

# Source files
SRCS = bot.cpp \
       bot_client.cpp \
       bot_combat.cpp \
       bot_globals.cpp \
       bot_sounds.cpp \
       compress.cpp \
       dll.cpp \
       engine.cpp \
       h_export.cpp \
       linkfunc.cpp \
       util.cpp \
       waypoint.cpp

# Object files (automatically generated from source files)
OBJS = $(SRCS:.cpp=.o)

# Default rule to build the target
all: $(TARGET)

# Rule to link the target shared library
$(TARGET): $(OBJS)
	$(CXX) $(LDFLAGS) -o $@ $(OBJS)

# Rule to compile each source file
%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

# Clean up build files
clean:
	rm -f $(OBJS) $(TARGET)
