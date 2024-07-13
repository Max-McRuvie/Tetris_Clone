# Specify the compiler
CXX = g++

# Compiler flags
CXXFLAGS = -I../inc -Wall -Wextra -std=c++11

# Linker flags
LDFLAGS = -L../lib

# Name of the executable
TARGET = main

# Directories
SRC_DIR = ../src
BUILD_DIR = .

# Find all source files in the SRC_DIR
SRCS = $(wildcard $(SRC_DIR)/*.cpp)

# Generate object files in the BUILD_DIR
OBJS = $(patsubst $(SRC_DIR)/%.cpp, $(BUILD_DIR)/%.o, $(SRCS))

# Default rule to build the executable
all: $(BUILD_DIR)/$(TARGET)

# Rule to link object files into the final executable
$(BUILD_DIR)/$(TARGET): $(OBJS)
	$(CXX) $(OBJS) -o $@ $(LDFLAGS)

# Rule to compile source files into object files
$(BUILD_DIR)/%.o: $(SRC_DIR)/%.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

# Clean up build files
clean:
	rm -f $(BUILD_DIR)/$(TARGET) $(OBJS)

# Phony targets
.PHONY: all clean