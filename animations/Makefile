NFRAMES = 64

EANDB_FRAMES = $(patsubst %,frames/EandB_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
EANDB45_FRAMES = $(patsubst %,frames/EandB45_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
EANDBCIRC_FRAMES = $(patsubst %,frames/EandBcirc_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
ELLIPSE_FRAMES = $(patsubst %,frames/ellipse_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))

TARGETS = EandB.gif \
		  EandB45.gif \
		  EandBcirc.gif \
		  ellipse.gif

all: $(TARGETS)

#------------------------------------------

EandB.gif: $(EANDB_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

EandB45.gif: $(EANDB45_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

EandBcirc.gif: $(EANDBCIRC_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

ellipse.gif: $(ELLIPSE_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

#------------------------------------------

frames/EandB_%.png: EandB.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

frames/EandB45_%.png: EandB45.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

frames/EandBcirc_%.png: EandBcirc.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

frames/ellipse_%.png: ellipse.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

#------------------------------------------

# The source file for the Vela pulsar's profile (from EPN database)
J0835-4510.1400MHz.txt:
	wget -O $@ http://www.epta.eu.org/epndb/ascii/jk17/J0835-4510/$@


