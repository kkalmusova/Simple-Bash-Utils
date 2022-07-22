FLAGS = -Wall -Werror -Wextra -std=c11

CAT = s21_cat.c
OBJ = s21_cat a.out a b res

all: s21_cat

rebuild: clean all

s21_cat: s21_cat.c
	gcc $(FLAGS) $(CAT) -o s21_cat

test: s21_cat
	python3 test_cat.py

style:
	cp ../../materials/linters/CPPLINT.cfg CPPLINT.cfg
	python3 ../../materials/linters/cpplint.py --extension=c *.c *.h

leaks:
	leaks -atExit -- ./s21_cat -enbts test.txt

clean:
	rm -rf $(OBJ) CPPLINT.cfg
