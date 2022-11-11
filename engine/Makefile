PROG	= jazecminer.js
OBJ	= main.bc blake2b.bc equihash.bc sha256.bc
HDR	= blake2b.h sha256.h equihash.h util.h

EMCC	= emcc
EMCC	+= -g -W -Wall -O2
EMCC	+= -s WASM=1

$(PROG): $(HDR)
	$(EMCC) main.c blake2b.c equihash.c sha256.c -s EXPORTED_FUNCTIONS=_mine -s TOTAL_MEMORY=256mb -o $(PROG)

clean:
	rm -f $(PROG) $(OBJ)
