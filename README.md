# circuit_analysis

Circuit analysis for making a resonant gain circuit for PDH locking.
Currently working on analyzing passive and active circuits

## Instructions

### `interactivefitter_resg_tf.py`

These are the instructions to get `interactivefitter_resg_tf.py` working.

1. Make sure you have `conda`
```
which conda
```
2. `git clone` InteractiveFitter at https://git.ligo.org/gabriele-vajente/interactivefitting
Make sure to `cd` into a convenient directory before you do this.
I like to put git repos in my `~/Git/` folder; you may have to modify this:
```
cd ~/Git/
git clone git@git.ligo.org:gabriele-vajente/interactivefitting.git
```

3. `cd` back to the top of this directory (i.e. where this `README.md` is):
```
cd ~/Git/circuit_analysis
```

4. Create the Anaconda environment named `circuit`, which hosts all the dependencies required for this repo
**WARNING: this will only work for a Linux Machine, because one dependency, `python-foton` only works for Linux**
```
conda env create -f environment_linux.yml
``` 

5. Activate the environment:
```
conda activate circuit
```
You should see `(circuit)` of the far left side of your terminal prompt.

6. Open the python code in `code/interactivefitter_resg_tf.py`, and ensure that the `sys.path.append(path)` is pointing to the correct location on your machine for where you `git clone`'d the `interactivefitting` repo.

7. Run the code in your new `(circuit)` environment
```
python code/interactivefitter_resg_tf.py
```

You should see a `pyqt5` window open that looks like this:
![pic_from_running_interactivefitting_resg_tf](figures/pic_from_running_interactivefitting_resg_tf.png)
