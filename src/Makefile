# COMPILER = clang++
# FLAGS = -std=c++11 -Wall
# LDFLAGS = -lraylib
# SRCDIR = src
# BUILDDIR = build
# EXECUTABLE = game

# SOURCES = $(wildcard $(SRCDIR)/*.cpp)
# OBJECTS = $(patsubst $(SRCDIR)/%.cpp,$(BUILDDIR)/%.o,$(SOURCES))
# DEPENDENCIES = $(OBJECTS:.o=.d)

# .PHONY: all clean

# all: $(EXECUTABLE)

# $(EXECUTABLE): $(OBJECTS)
# 	$(COMPILER) $(FLAGS) $(OBJECTS) -o $(EXECUTABLE) $(LDFLAGS)

# $(BUILDDIR)/%.o: $(SRCDIR)/%.cpp
# 	@mkdir -p $(@D)
# 	$(COMPILER) $(FLAGS) -MMD -MP -c $< -o $@

# -include $(DEPENDENCIES)

# clean:
# 	rm -rf $(BUILDDIR) $(EXECUTABLE)

# # Compiler
# COMP = clang++

# # Compiler flags
# FLAGS = -std=c++11 -Wall -framework CoreVideo -framework IOKit -framework Cocoa -framework GLUT -framework OpenGL ../libraylib.a -I ../../raylib/src

# # Header files
# HDRS = action.h button.h spritesheet.h tile.h tilemap.h toolbar.h utils.h

# # Source file and executable name
# SRCS = main.cpp
# EXEC = app

# # Build target
# all: $(EXEC)

# # Rule to build the executable
# $(EXEC): $(SRCS) $(HDRS)
# 	$(COMP) $(FLAGS) -o $(EXEC) $(SRCS)

# # Clean target to remove the executable
# clean:
# 	rm -f $(EXEC)

# Compiler
COMP = clang++

# Compiler flags
# -framework ... options are for macOS, plus the path to your raylib includes/libraries
FLAGS  = -std=c++11 -Wall
LDFLAGS= -framework CoreVideo -framework IOKit -framework Cocoa \
         -framework GLUT -framework OpenGL \
         ../libraylib.a -I ../../raylib/src

# Name of the final executable
EXEC = app

# Source and header files
SRCS = main.cpp \
       action.cpp \
       button.cpp \
       spritesheet.cpp \
       tile.cpp \
       tilemap.cpp \
       toolbar.cpp \
       utils.cpp

HDRS = action.h \
       button.h \
       spritesheet.h \
       tile.h \
       tilemap.h \
       toolbar.h \
       utils.h

# Generate object file names from SRCS (e.g., main.cpp -> main.o)
OBJS = $(SRCS:.cpp=.o)

# Default rule: build the executable
all: $(EXEC)

# Link all object files into the final executable
$(EXEC): $(OBJS)
	$(COMP) $(FLAGS) $(OBJS) -o $@ $(LDFLAGS)

# Compile each .cpp file into an object file
%.o: %.cpp $(HDRS)
	$(COMP) $(FLAGS) -c $< -o $@

# Clean up object files and the executable
clean:
	rm -f $(EXEC) *.o

