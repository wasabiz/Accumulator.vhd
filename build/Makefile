TESTBENCH = Accumulator_tb
OBJECTS = ../types.o ../ALU.o ../tx.o ../rx.o ../uart.o ../Accumulator.o ../Accumulator_tb.o

GHDLC = ghdl
GHDLFLAGS  = -fexplicit --ieee=synopsys
GHDL_SIM_OPT = --stop-time=1ms --ieee-asserts=disable

.PHONY: clean
all: $(TESTBENCH)

$(OBJECTS): %.o: %.vhd
	$(GHDLC) -a $(GHDLFLAGS) $^

$(TESTBENCH): $(OBJECTS)
	$(GHDLC) -e $(GHDLFLAGS) $@
	$(GHDLC) -r $(GHDLFLAGS) $@ $(GHDL_SIM_OPT) --vcd=$@.vcd

clean :
	$(GHDLC) --clean
	rm *.vcd work-obj93.cf
