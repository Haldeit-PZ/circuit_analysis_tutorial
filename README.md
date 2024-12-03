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
You should see `(circuit)` of the far left side of your terminal prompt.

4. Using PyZero:

a) Adding circuit components as a list through a .txt file.
```
r r1 1k n1 n2
```
Here, r means resistor, r1 is the name, n1 and n2 are the node numbers.
```
freq 1 5 100
```
Frequency response. This shows a response from 10^1 to 10^5, with 100 data points.
```
test n1 n8
```
Input (node1) and output (node8), 'test' needs to be there. 

5. Plotting transfer function:
```
python PyZeroFitting.py /home/input_node_file.txt --plot-pyzero
```
This will produce the pyzero model TF, the input_node_file.txt, try with example.txt first.
