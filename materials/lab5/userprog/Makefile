CROSS_COMPILE ?= aarch64-linux-gnu-
CC := $(CROSS_COMPILE)gcc
LD := $(CROSS_COMPILE)ld

CFLAGS := -Wall -nostdlib -nostartfiles -ffreestanding -mgeneral-regs-only


all: userprog2

userprog2: userprog2.elf
	$(CROSS_COMPILE)objcopy -O binary $^ $@

userprog2.elf: linker.ld userprog2.o
	$(LD) $(LDFLAGS) -T $< -o $@ userprog2.o

userprog2.o: userprog2.c
	$(CC) $(CFLAGS) -c $< -o $@


.PHONY: clean
clean:
	rm -f *.o *.elf
