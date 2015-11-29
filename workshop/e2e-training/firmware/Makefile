

CC=/opt/microchip/xc8/v1.35/bin/xc8

14K50OPTS=--chip=18F14K50 --codeoffset=0x1400 --rom=1800-3FFD
OPTS= --summary=+hex,+psect --outdir=bin/ --objdir=obj/


blink.hex: blink.c Makefile
	mkdir obj bin
	$(CC) $(OPTS) $(14K50OPTS)  $<
	cp bin/$@ $@


blflash: blink.hex
	mphidflash -w $< -r

clean:
	rm -f bin/* obj/*