SHELL := /bin/bash
TARGET = ./s21_cat
CC = gcc 
CFLAGS:=-Wall -Werror -Wextra -std=c11
RM = rm -rf 
SRC = s21_cat.c

all: $(TARGET)

s21_cat: s21_cat.o
	$(CC) $(CFLAGS) s21_cat.o -o $(TARGET)
	rm -rf *.o

s21_cat.o: $(SRC) s21_cat.h
	$(CC) $(CFLAGS) $(SRC) -c

test:
	bash t_cat.sh

format-check:
	cp ../../materials/linters/.clang-format ./
	clang-format -n *.c *.h
	rm .clang-format

format:
	cp ../../materials/linters/.clang-format ./
	clang-format -i *.c *.h
	rm .clang-format

clean:
	$(RM) *.o $(TARGET) log.txt s21_cat.txt cat.txt

rebuild: clean $(TARGET)
