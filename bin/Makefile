# makefile

INCLUDE_DIRECTORY = src
SOURCE_DIRECTORY = src
OBJECT_DIRECTORY = bin
OUTPUT_DIRECTORY = .

EXECUTABLE = asembler

SOURCE = $(wildcard $(SOURCE_DIRECTORY)/*.cpp)
OBJECT = $(patsubst $(SOURCE_DIRECTORY)/%.cpp, $(OBJECT_DIRECTORY)/%.o, $(SOURCE))

CC = g++
FLAGS = -I$(INCLUDE_DIRECTORY) -Wall -std=c++14

$(OUTPUT_DIRECTORY)/$(EXECUTABLE): $(OBJECT)
	$(CC) -o $@ $^ $(FLAGS)

$(OBJECT_DIRECTORY)/%.o: $(SOURCE_DIRECTORY)/%.cpp
	$(CC) -MMD -c -o $@ $< $(FLAGS)

-include $(OBJECT_DIRECTORY)/*.d 

clean:
	rm -f $(OBJECT_DIRECTORY)/*.o
	rm -f $(OBJECT_DIRECTORY)/*.d
	rm -f $(OUTPUT_DIRECTORY)/$(EXECUTABLE)

.PHONY: clean
