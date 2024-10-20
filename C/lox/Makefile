# Compiler
CC = gcc

# Compiler flags
CFLAGS = -Wall -Wextra -std=c99 -Iinclude

# Directories
SRC_DIR = src
BUILD_DIR = build

# Executable name
TARGET = $(BUILD_DIR)/lox

# Source files
SRCS = $(wildcard $(SRC_DIR)/*.c)

# Object files
OBJS = $(SRCS:$(SRC_DIR)/%.c=$(BUILD_DIR)/%.o)

# Default rule to build the program
all: $(TARGET)

# Rule to link object files into executable
$(TARGET): $(OBJS)
	$(CC) $(OBJS) -o $(TARGET)

# Rule to compile source files into object files
$(BUILD_DIR)/%.o: $(SRC_DIR)/%.c | $(BUILD_DIR)
	$(CC) $(CFLAGS) -c $< -o $@

# Rule to create build directory
$(BUILD_DIR):
	mkdir -p $(BUILD_DIR)

# Clean up object files and executable
clean:
	rm -rf $(BUILD_DIR)

.PHONY: all clean
