FLAGS = -Wall -Werror -Wextra -std=c11 -pedantic

GREP = s21_grep.c
OBJ = s21_grep a.out a b res

all: s21_grep

rebuild: clean all

s21_grep: s21_grep.c
	gcc $(FLAGS) $(GREP) -o s21_grep

test: s21_grep
	python3 test_grep.py

style:
	cp ../../materials/linters/CPPLINT.cfg CPPLINT.cfg
	python3 ../../materials/linters/cpplint.py --extension=c *.c *.h

leaks:
	leaks -atExit -- ./s21_grep reflect 1.txt

clean:
	rm -rf $(OBJ) CPPLINT.cfg
