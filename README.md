# Caravel SoC FPGA
Porting [Caravel SoC](https://github.com/bol-edu/caravel-soc) to FPGA design flow.

## Toolchain Prerequisites
* [Ubuntu 20.04+](https://releases.ubuntu.com/focal/)
* [RISC-V GCC Toolchains rv32i-4.0.0](https://github.com/stnolting/riscv-gcc-prebuilt)
* [Vitis 2022.1](https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/vivado-design-tools/2022-1.html)
* [GTKWave v3.3.103](https://gtkwave.sourceforge.net/)

## Testbenches for Custom Designs

* Counter with (LA) logic analyzer interface 

  Files for vitis xvlog/xelab/xsim:  
  ##################################################  
  caravel-soc_fpga/testbench/counter_la/counter_la.c  
  caravel-soc_fpga/testbench/counter_la/counter_la_tb.v  
  caravel-soc_fpga/testbench/counter_la/include.rtl.list.xsim 
  caravel-soc_fpga/testbench/counter_la/run_xsim
  caravel-soc_fpga/testbench/counter_la/waveform.gtkw  
  ##################################################
  
* Counter with wishbone interface

  Files for vitis xvlog/xelab/xsim:  
  ##################################################  
  caravel-soc_fpga/testbench/counter_la/counter_wb.c  
  caravel-soc_fpga/testbench/counter_la/counter_wb_tb.v  
  caravel-soc_fpga/testbench/counter_la/include.rtl.list.xsim 
  caravel-soc_fpga/testbench/counter_la/run_xsim
  caravel-soc_fpga/testbench/counter_la/waveform.gtkw  
  ##################################################
  
* GCD with (LA) logic analyzer interface

  Files for vitis xvlog/xelab/xsim:  
  ##################################################  
  caravel-soc_fpga/testbench/gcd_la/gcd_la.c  
  caravel-soc_fpga/testbench/gcd_la/gcd_la_tb.v  
  caravel-soc_fpga/testbench/gcd_la/include.rtl.list.xsim 
  caravel-soc_fpga/testbench/gcd_la/run_xsim
  caravel-soc_fpga/testbench/gcd_la/waveform.gtkw  
  ##################################################
