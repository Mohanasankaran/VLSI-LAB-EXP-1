# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using vivado software.

APPARATUS REQUIRED: vivado ML 2023.1

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:
1.
FULL ADDER CODE:
```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
   
endmodule
```
OUTPUT:
ELOBRATED DESIGN:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/6a2848ed-8229-4aa8-a888-9e544410decc)

SIMULATION:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/2d856f9b-a314-4e57-8bf5-b9a90fd87c37)

2.
HALF ADDER CODE:
```
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; // sum and carry
or(sum,a,b);
and(carry,a,b);
endmodule
```
OUTPUT:
ELOBRATED DESIGN:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/f6785273-a02e-4c97-9822-748ca10034c3)

SIMULATION:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/ae000486-57ea-4a6f-9629-0d3ef759375c)


3.
FULL SUBTRACTOR CODE:
```
// fullsubtractor using gate level modeling
module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
```
OUTPUT:
ELOBRATED DESIGN:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/3305ec67-04aa-45a9-940f-b91377368df7)

SIMULATION:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/7ce1a211-df4d-4cfe-aa50-62eef0394483)


4.
HALF SUBTRACTOR CODE:
```
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule
```
OUTPUT:
ELOBRATED DESIGN:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/8ee9cb6f-d1fb-485d-be17-6caea4cf53cc)

SIMULATION:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/75b6ee6e-2691-4dce-98b9-9d35844cad94)


5.
LOGIC GATES CODE:
```
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b);  
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```
OUTPUT:
ELOBRATED DESIGN:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/062b9f76-41be-4835-9856-6c8f8257af9b)

SIMULATION:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/e3455e34-9984-4e2e-9e1b-4e0eefa2770b)


6.
RIPPLE CARRY ADDER(4 BIT):
```
module rippe_adder(S, Cout, X, Y,Cin);
input [3:0] X, Y;// Two 4-bit inputs
input Cin;
output [3:0] S;
output Cout;
wire wl, w2, w3;

fulladder u1(S[0], w1,X[0], Y[0], Cin);
fulladder u2(S[1], w2,X[1], Y[1], w1);
fulladder u3(S[2], w3,X[2], Y[2], w2);
fulladder u4(S[3], Cout,X[3], Y[3], w3);
endmodule
module fulladder(S, Co, X, Y, Ci);
input X, Y, Ci;
output S, Co;
wire w1,w2,w3;
//Structural code for one bit full adder 
xor G1(wl, X, Y);
xor G2(S, w1, Ci);
and G3(w2, w1, Ci);
and G4(w3, X, Y);
or  G5(Co, w2, w3);
endmodule
```
OUTPUT:
ELOBRATED DESIGN:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/1c181e41-0e2c-47ca-bf21-f4ab24a457da)

SIMULATION:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/a025f16f-b94b-4df6-a6b9-21375ffa7696)


7.
RIPPLE CARRY ADDER(8 BIT):
```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
module rippe_adder(S,Cout,X,Y,Cin);
input [7:0] X,Y;
input Cin;
output [7:0] S;
output Cout;
wire w1,w2,w3,w4,w5,w6,w7;
fulladder u1(S[0],w1,X[0],Y[0],Cin);
fulladder u2(S[1],w2,X[1],Y[1],w1);
fulladder u3(S[2],w3,X[2],Y[2],w2);
fulladder u4(S[3],w4,X[3],Y[3],w3);
fulladder u5(S[4],w5,X[4],Y[4],w4);
fulladder u6(S[5],w6,X[5],Y[5],w5);
fulladder u7(S[6],w7,X[6],Y[6],w6);
fulladder u8(S[7],Cout,X[7],Y[7],w7);
endmodule

module fulladder(S,CO,X,Y,Ci);
input X,Y,Ci;
output S,CO;
wire w1,w2,w3;
xor G1(w1,X,Y);
xor G2(S,w1,Ci);
and G3(w2,X,Ci);
and G4(w3,X,Y);
or G5(CO,w3,w3);
endmodule
```
OUTPUT:
ELOBRATED DESIGN:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/ebea7985-d2f4-402f-b49c-8967c5b8b135)

SIMULATION:
![image](https://github.com/Mohanasankaran/VLSI-LAB-EXP-1/assets/161284142/5118d134-c800-4b23-9c3e-a0d734cf013f)


RESULT:

