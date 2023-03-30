# Caravel SoC FPGA
Porting [Caravel SoC](https://github.com/bol-edu/caravel-soc) to FPGA design flow.

## Toolchain Prerequisites
* [Ubuntu 20.04+](https://releases.ubuntu.com/focal/)
* [RISC-V GCC Toolchains rv32i-4.0.0](https://github.com/stnolting/riscv-gcc-prebuilt)
* [Vitis 2022.1](https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/vivado-design-tools/2022-1.html)
* [GTKWave v3.3.103](https://gtkwave.sourceforge.net/)

## Revision from Caravel SoC to Caravel SoC FPGA
* `default_nettype none to wire [x11]   
   /vip/tbuart.v:1
   /vip/spiflash.v:1
   /rtl/user/user_project_wrapper.v:16
   /rtl/user/user_proj_example.counter.v:16
   /rtl/user/user_proj_example.gcd.v:16
   /rtl/soc/gpio_control_block.v:58
   /rtl/soc/housekeeping.v:58
   /rtl/soc/mprj_io.v::58
   /rtl/soc/housekeeping_spi.v:16
   /rtl/soc/mgmt_core_wrapper.v:30
   /rtl/soc/gpio_defaults_block.v:58
* xxx



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
