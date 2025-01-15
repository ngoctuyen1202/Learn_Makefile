build: my_lib.o main.o
	g++ main.o my_lib.o -o main
my_lib.o:
	g++ my_lib.cc -c mylib.o
main.o:
	g++ main.cc -c main.o
execute:
	./main
clean:
	rm -f *.o
	rm -f main