SHELL := /bin/bash
TARGET = ./s21_grep
CC = gcc
CFLAGS = -Wall -Werror -Wextra -std=c11

all : $(TARGET)

s21_grep : s21_grep.o
	$(CC) $(CFLAGS) s21_grep.o -o $(TARGET)
	rm -rf *.o

s21_grep.o : s21_grep.c s21_grep.h
	$(CC) $(CFLAGS) s21_grep.c -c

test:
	bash tests.sh

format-check:
	cp ../../materials/linters/.clang-format ./
	clang-format -n *.c *.h
	rm .clang-format

format:
	cp ../../materials/linters/.clang-format ./
	clang-format -i *.c *.h
	rm .clang-format

clean :
	rm -r *.o s21_grep

rebuild :
	clean s21_grep
