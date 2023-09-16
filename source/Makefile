RM       = rm -f
CC       = gcc
CFLAGS   = -O4 -Wall
EXEDIR   = ..
TARGNES  = $(EXEDIR)/nesasm
OBJS     = assemble.o code.o command.o crc.o expr.o func.o\
	   input.o macro.o main.o map.o mml.o nes.o output.o\
	   pcx.o pce.o proc.o symbol.o

all: $(TARGNES)
default: $(TARGNES)

clean:
	$(RM) *.o
	$(RM) $(EXEDIR)/nesasm

# ASSEMBLER
$(OBJS)  : defs.h externs.h protos.h
main.o   : inst.h vars.h
expr.o   : expr.h
pce.o    : pce.h
nes.o    : nes.h
%.o : %.c
	$(CC) $(CFLAGS) -o $@ -c $<

# EXE
$(TARGNES) : $(OBJS)
	$(CC) -o $(TARGNES)  $(OBJS)


install: all
	cp -f $(TARGNES) /usr/local/bin
