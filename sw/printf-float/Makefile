all : main.c entry.S
	riscv64-unknown-elf-gcc main.c entry.S -o main -march=rv32imafd -mabi=ilp32d -Wl,-e_reset_vector
	
sim: all
	riscv-vp main
	
dump-elf: all
	riscv32-unknown-elf-readelf -a main
	
dump-code: all
	riscv32-unknown-elf-objdump -D main
	
clean:
	rm -f main
