NFRAMES = 64

EANDB_FRAMES = $(patsubst %,frames/EandB_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
EANDB45_FRAMES = $(patsubst %,frames/EandB45_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
EANDBCIRC_FRAMES = $(patsubst %,frames/EandBcirc_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
ECIRC_FRAMES = $(patsubst %,frames/Ecirc_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
ELLIPSE_FRAMES = $(patsubst %,frames/ellipse_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))
VELA_FRAMES = $(patsubst %,frames/vela_%.png,$(shell seq -w 0 $(NFRAMES) | head -n-1))

TARGETS = EandB.gif \
		  EandB45.gif \
		  EandBcirc.gif \
		  Ecirc.gif \
		  ellipse.gif

all: $(TARGETS)

#------------------------------------------
# Converting sets of PNGs to GIFs

EandB.gif: $(EANDB_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

EandB45.gif: $(EANDB45_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

EandBcirc.gif: $(EANDBCIRC_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

Ecirc.gif: $(ECIRC_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

ellipse.gif: $(ELLIPSE_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

vela.gif: $(VELA_FRAMES)
	convert -loop 0 -delay 5 -dispose previous $^ $@

#------------------------------------------
# Creating the individual PNG frames

frames/EandB_%.png: EandB.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

frames/EandB45_%.png: EandB45.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

frames/EandBcirc_%.png: EandBcirc.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

frames/Ecirc_%.png: Ecirc.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

frames/ellipse_%.png: ellipse.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

frames/vela_%.png: vela.gpi
	@mkdir -p frames
	gnuplot -c $< $* $(NFRAMES)

#------------------------------------------
# Miscellaneous

# The source file for the Vela pulsar's profile (from EPN database)
J0835-4510.1400MHz.txt:
	wget -O $@ http://www.epta.eu.org/epndb/ascii/jk17/J0835-4510/$@


