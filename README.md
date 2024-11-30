# circuit analysis: PyZero modeling tutorial

## Instructions
1. Make sure you have `conda`
```
which conda
```

2. Create the Anaconda environment named `circuit`, which hosts all the dependencies required for this repo
**WARNING: this will only work for a Linux Machine, because one dependency, `python-foton` only works for Linux**
```
conda env create -f environment_linux.yml
```

3. Activate the environment:
```
conda activate circuit
```
You should see `(circuit)` of the far left side of your terminal prompt.

4. How to use this code yourself

To use this code you're going to need to do 2 things. First of all create a .txt file in the directory that has all of this code. Look at example_nodes.txt as a general example, but you'll want to made a text file with a node list.
```
r r1 1k n1 n2
```
The first letter indicates the type(r for resistor, c for capacitor l for inductor, and op for opamp). The next is the name of the component. In the case of the opamp, next is the type(for example AD829), in the case of other components, next is the value. Then list out the nodes you want to connect the component to.
```
freq 1 5 100
```
Then you have the frequency response. This shows a response from 10^1 to 10^5, with 100 data points.
```
test n1 n8
```
Finally, indicate the input and output. Save this txt file in your directory(as well as your text file from your SR785 data) and then open PyZeroFitting.py.

5. How to run it 
```
python PyZeroFitting.py /home/input_node_file.txt /home/data_file.txt
```
This will produce your fitted model as well as residual plots.
```
python PyZeroFitting.py /home/input_node_file.txt --plot-pyzero
```
This will produce just the pyzero model(so use this if you dont have data).
