#------------------------------------------------------------------
SHELL		= /bin/sh
MAKEFILE	= Makefile
#--------------------------------------------------------
VLOG	= iverilog
VSIM	= vvp
#--------------------------------------------------------
TOP	= top
#--------------------------------------------------------
all: compile simulate

compile:
	$(VLOG) -o $(TOP).vvp -s $(TOP)\
		-DBMP_INPUT_FILE=\"images/starry_640x480.bmp\"\
		-DBMP_OUTPUT_FILE=\"result.bmp\"\
		-f iverilog.args
#	$(VLOG) -o $(TOP).vvp -s $(TOP) -f iverilog.args 2>&1 | tee compile.log

simulate: compile
	$(VSIM) -l vvp.log $(TOP).vvp 

#--------------------------------------------------------
clean:
	/bin/rm -f  $(TOP).vvp
	/bin/rm -f  compile.log
	/bin/rm -f  wave.vcd
	/bin/rm -f  vvp.log
	/bin/rm -f  result.bmp
	/bin/rm -f  result_conv.bmp
cleanup: clean

clobber: cleanup
#--------------------------------------------------------
