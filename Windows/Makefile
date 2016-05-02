TARGET := psxtract

LIBRETRO_COMM_DIR := ../../..

SOURCES := \
	lz.c \
	libkirk/aes.c \
	libkirk/amctrl.c \
	libkirk/bn.c \
	libkirk/des.c \
	libkirk/ec.c \
	libkirk/kirk_engine.c \
	libkirk/sha1.c

SOURCES_CXX := \
	cdrom.cpp \
	crypto.cpp \
	psxtract.cpp \
	utils.cpp

OBJS := $(SOURCES:.c=.o) $(SOURCES_CXX:.cpp=.o)

CFLAGS += -Wall -pedantic -std=gnu99 -g

CXXFLAGS += -Wall -pedantic -g

all: $(TARGET)

%.o: %.cpp
	$(CXX) -c -o $@ $< $(CXXFLAGS)

%.o: %.c
	$(CC) -c -o $@ $< $(CFLAGS)

$(TARGET): $(OBJS)
	$(CXX) -o $@ $^ $(LDFLAGS)

clean:
	rm -f $(TARGET) $(OBJS)

.PHONY: clean

