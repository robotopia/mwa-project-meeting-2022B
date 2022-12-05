NFRAMES = 64

EANDB_FRAMES = $(patsubst %,frames/EandB_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
EANDB45_FRAMES = $(patsubst %,frames/EandB45_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))

all: EandB.gif EandB45.gif

EandB.gif: $(EANDB_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

frames/EandB_%.png: EandB.gpi
	gnuplot -c $< $* $(NFRAMES)

EandB45.gif: $(EANDB45_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

frames/EandB45_%.png: EandB45.gpi
	gnuplot -c $< $* $(NFRAMES)
