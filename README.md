# BE-Project


About my B.E. final year Major Project.

So here, I've shown how to use Iverilog and Gtkwave with VScode as an IDE to verify and simulate verilog modules.
As we all know, iverilog and gtkwave are opensource EDA tools that can only be run from a command prompt.To make things easier, I'm using vscode, which provides a compact view for dealing with Opensource tools.

Please install the following before proceeding:

1.icarus verilog (download link: https://bleyer.org/icarus/ for Windows).

2.VScode download link - https://code.visualstudio.com/download (also expansions i.Verilog-HDL/SystemVerilog/Bluespec SystemVerilog and ii.Graphviz Preview).

**We're ready to begin**

**Step-1**

I've opened the vscode and clicked on openfolder,it can be done in two methods as shown.


![1](https://user-images.githubusercontent.com/48184231/139592710-88827e56-72da-4875-84d9-8ec65815bee3.png)

![2](https://user-images.githubusercontent.com/48184231/139592765-a0930fff-b6a8-4f23-a3bc-04453641386f.png)


**Step-2**
Created a New Folder as shown. I named mine mux2x1.
![image](https://user-images.githubusercontent.com/93651596/140561318-cf0f8e86-0813-42a7-b222-81aa7b3b189b.png)

**Step-3**

Created a new file with .v extension i.e., mux2x1.v by clicking on the button shown.

![5](https://user-images.githubusercontent.com/48184231/139593464-78dd702d-71b8-4db5-8338-8d440551d195.png)

I've written my verilog code in the created file

![6](https://user-images.githubusercontent.com/48184231/139593656-26a4905a-1598-4244-9f72-2c62954d3453.png)

(i will update a repository for various verilog modules, for now get verilog codes here : https://github.com/vision-vlsi/verilog/tree/main/Combinational_circuits )

**Step-3**
Creat a TestBench file for the written verilog module. the main key point to take care while writing testbench is as follows

1.include "$dumpfile"

2.include "$monitor"

![7](https://user-images.githubusercontent.com/48184231/139593761-927ae4de-6297-4d33-80e0-a42f1b8cab03.png)

**Step-4**
Now open a new terminal as shown 

![8](https://user-images.githubusercontent.com/48184231/139593788-c1b02dc3-790a-478c-807e-ccbf29ccc721.png)

In terminal type the following commands 

1. **iverilog modulename testbenchname** in my case => iverilog encoder.v tb.v
![10](https://user-images.githubusercontent.com/48184231/139594344-aa18f396-fc46-46fb-b4c4-20888a5c57d4.png)


after this a new file "a.out" is generated use following command
![11](https://user-images.githubusercontent.com/48184231/139594347-277ba208-8da1-4ffd-a2a3-70d6f05685dd.png)

2.**vvp a.out**
![12](https://user-images.githubusercontent.com/48184231/139594352-c41da818-2c6f-450f-9f2a-bdcf8c61d678.png)

you will be able to see resut in terminal as well as a new file with .vcd extention which is further use for generating waveforms![13](https://user-images.githubusercontent.com/48184231/139594359-9b6ee381-8244-4a14-a40f-32fcc96c345a.png)


for generating waveforms we are using gtkwave EDA Tool for waveform representation. use the following command for opening .vcd file in gtkwave

3.**gtkwave modulename.vcd** in my case => gtkwave encoder8to3.vcd
![14](https://user-images.githubusercontent.com/48184231/139594369-13593648-5748-44a7-ab84-50a4e36cec9e.png)

the following window pop's up click the testbench as shown and append ports.after that click zoom fit butten to observe all changing waveforms in a single window use mouse and click on the various points on waves to observe the values on left signals window.
![15](https://user-images.githubusercontent.com/48184231/139594376-87661085-476f-436c-bbca-67b8a1c8143c.png)

![16](https://user-images.githubusercontent.com/48184231/139594411-a0669e25-12ff-4128-b693-827adf87d99b.png)

![17](https://user-images.githubusercontent.com/48184231/139594412-896d3750-e51f-40a9-881a-bcca63708ffd.png)




**all codes in one place**

1. iverilog modulename.v testbenchname.v
2. vvp a.out
3. gtkwave name.vcd
