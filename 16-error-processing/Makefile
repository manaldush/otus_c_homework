NAME := loggerLib

SRC_DIR     := src
OBJ_DIR     := obj
BUILD_DIR   := build
SRCS        := \
	logger.c
SRCS        := $(SRCS:%=$(SRC_DIR)/%)
OBJS        := $(SRCS:$(SRC_DIR)/%.c=$(OBJ_DIR)/%.o)

FULL_NAME   := $(BUILD_DIR)/$(NAME)

CC          := gcc
CFLAGS      := -Wall -Wextra -Wpedantic -g3 -std=c11 

RM          := rm -f

all: $(NAME)

$(NAME): $(OBJS)
	mkdir -p $(BUILD_DIR)
	ar rcs $(FULL_NAME).a $(OBJS)

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	mkdir -p $(@D)
	$(CC) $(CFLAGS)-c -o $@ $<

clean:
	$(RM) $(OBJS)
	$(RM) $(FULL_NAME).a

.PHONY: clean