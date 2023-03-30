# Caravel SoC FPGA
Porting [Caravel SoC](https://github.com/bol-edu/caravel-soc) to FPGA design flow.

## Toolchain Prerequisites
* [Ubuntu 20.04+](https://releases.ubuntu.com/focal/)
* [RISC-V GCC Toolchains rv32i-4.0.0](https://github.com/stnolting/riscv-gcc-prebuilt)
* [Vitis 2022.1](https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/vivado-design-tools/2022-1.html)
* [GTKWave v3.3.103](https://gtkwave.sourceforge.net/)

## Revision from Caravel SoC to Caravel SoC FPGA
* `default_nettype none to wire (check by xvlog)  
   (01) /vip/tbuart.v:1  
   (02) /vip/spiflash.v:1  
   (03) /rtl/user/user_project_wrapper.v:16  
   (04) /rtl/user/user_proj_example.counter.v:16  
   (05) /rtl/user/user_proj_example.gcd.v:16  
   (06) /rtl/soc/gpio_control_block.v:58  
   (07) /rtl/soc/housekeeping.v:58  
   (08) /rtl/soc/mprj_io.v::58  
   (09) /rtl/soc/housekeeping_spi.v:16  
   (10) /rtl/soc/mgmt_core_wrapper.v:30  
   (11) /rtl/soc/gpio_defaults_block.v:58  
    
* redeclaration of ansi port (check by xvlog)  
   (01) /rtl/user/user_proj_example.counter.v  
   (02) /rtl/user/user_proj_example.gcd.v  
   (03) /rtl/soc/gpio_control_block.v  
   (04) /rtl/soc/gpio_defaults_block.v  
   (05) /rtl/soc/housekeeping.v
   
* comment out `timescale 1 ns / 1 ps (check by xelab)  
   (01) /testbench/counter_la_tb.v  
   (02) /testbench/counter_wb_tb.v  
   (03) /testbench/gcd_la_tb.v   
   (04) /vip/tbuart.v  
   (05) /vip/spiflash.v  
   
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
