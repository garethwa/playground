IDIR=./include
LDIR=./lib
SDIR=./src
ODIR=$(SDIR)/build

CC=gcc
CFLAGS=-I$(IDIR)

LIBS=-lm

_DEPS = hello-world.h
DEPS  = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJS = hello-world.o 
OBJS  = $(patsubst %,$(ODIR)/%,$(_OBJS))


$(ODIR)/%.o: $(SDIR)/%.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

hello-world: $(OBJS)
	gcc -o $@ $^ $(CFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o $(SDIR)/*~ $(IDIR)/*~ 
