# Spice2Verilog
Spice netlist to Verilog netlist translation

**Usage: perl sp2vlog.pl -s spfile [-d dfile] [-h]**

                  -s <spfile> Spice transistor level file to be translated (required)
                  -d <dfiles Data file from vlog2sp.pl containing port types (defaults to basename.data)
                  -h prints this message

*copied from the patent* : US6792579B2 expired on 2021-12-02, assigned to : LSI Corp ; Bell Semiconductor LLC



*limitation* :
              if in your spice netlist, the nodes are only numbers such as : X1 1 2 3 4 MY_SUBCKT

              the node will also be numbers in the verilog netlist ... it is not good !
              
              So, first respell your nodes such as :  X1 N1 N2 N3 N4 MY_SUBCKT
              
              but, pay attention that you don't have other nodes in your netlist already called N1, N2, N3 or N4 ;)
              
              

*example of dfile Data for a 2 inputs AND :*

 module LIB_AND2 (A, B, Z);
   input  A,B;
   output  Z;
 endmodule
