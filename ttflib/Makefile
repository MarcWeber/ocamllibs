FLAGS=-I ../extlib -I ../swflib
FILES=tTFData tTFParser tTFTools tTFSwfWriter tTFCanvasWriter tTFJsonWriter
LIBS=extLib swflib unix

OUTPUT=ttf

all: native bytecode

native:
	ocamlopt $(FLAGS) $(FILES:=.ml) -g -a -o ttf.cmxa

bytecode:
	ocamlc $(FLAGS) $(FILES:=.ml) -g -a -o ttf.cma

exec:
	ocamlopt $(FLAGS) $(LIBS:=.cmxa) $(FILES:=.ml) main.ml -g -o $(OUTPUT)

clean:
	rm -rf ttf.cmxa ttf.lib ttf.a $(wildcard *.cmx) $(wildcard *.obj) $(wildcard *.o) $(wildcard *.cmi)
