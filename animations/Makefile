NFRAMES = 64

EANDB_FRAMES = $(patsubst %,frames/EandB_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))

EandB.gif: $(EANDB_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

frames/EandB_%.png: EandB.gpi
	gnuplot -c $< $* $(NFRAMES)
