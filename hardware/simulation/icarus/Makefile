ROOT_DIR:=../../..

defmacro:=-D
incdir:=-I

SIMULATOR=icarus
SIM_SERVER=$(IVSIM_SERVER)
SIM_USER=$(IVSIM_USER)
SIM_PROC=a.out

include ../simulation.mk

#simulator flags
VLOG = iverilog -W all -g2005-sv $(INCLUDE) $(DEFINE)

#simulator object
$(SIM_PROC):
	$(VLOG) $(VSRC)

.PHONY: run clean debug

run:
	cp $(VEXRISCV_DIR)/hardware/src/VexRiscv.v_toplevel_RegFilePlugin_regFile.bin ./
	./$(SIM_PROC)

clean: clean-remote
	@rm -f $(SIM_PROC)

debug:
	@echo $(SUBMODULES)
	@echo $(MODULES)
	@echo $(MEM_MODULES)
	@echo $(AXIMEM_DIR)
	@echo $(INTERCON_DIR)
	@echo $(MEM_DIR)
	@echo $(CPU_DIR)
	@echo $(CACHE_DIR)
	@echo $(UART_DIR)
	@echo $(VHDR)
	@echo $(VSRC)
	@echo $(INCLUDE)
	@echo $(DEFINE)
	@echo $(MODULE)
