# circuit analysis: PyZero modeling tutorial

## Instructions
1.  Make sure you have `conda`, then navigate to where you want the repo.
```
which conda
```
```
cd path/you/want/repo
```

2. Create the Anaconda environment, which hosts all the dependencies required for this repo. This environment is call `pyzero_env`.
**WARNING: this will only work for a Linux Machine, because one dependency, `python-foton` only works for Linux**
```
conda env create -f environment_linux.yml
```

3. Activate the environment:
```
conda activate pyzero_env
```
You should see `(pyzero_env)` of the far left side of your terminal prompt.

## Creating The Text File

1. Create a text file that stores the circuit information
```
vim circuit.txt
```
(replace vim with your choice of editor, nano etc.) 

2. Add circuit components as a list in the .txt file. The first letter indicates the type(r for resistor, c for capacitor, l for inductor, and op for opamp). The next letter/number is the name of the component (r1 in following exmaple). The following number is the value of the element (1 kilo Ohm), and n1 & n2 are the nodes to which the element is connected. In the case of an op amp, the format is component type (op), name (1ua), model# (here it is a lt1124), and the node connections. 
```
r r1 1k n1 n2
op u1a lt1124 gnd n1 n2
```

3. List the frequency parameters for the test you want to run. Here we're doing a frequency response from 10^1 Hz to 10^5 Hz with 100 data points. 
```
freq 1 5 100
```
4. Finally, indicate the input and output of the circuit as nodes. Here, input is node1, output is node 8, and "test" always needs to be included.
```
test n1 n8
```
### Plotting a Transfer Function:

1. To see the transfer funciton of your circuit, run the following script:
```
python PyZeroFitting.py /home/input_node_file.txt --plot_pyzero
```
You can then save the figure as a png file.

2. You can plot other things as well. Use `-h` to see all options for plotting, such as bode plots and noise plots. 
 
