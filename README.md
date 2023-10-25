## SF2 Image Processing project

The aim of this project is to design a compression scheme that compresses raw ```.mat``` images of ~60kB down to under 5kB.

### Notebooks

The notebooks in the ```notebooks``` folder contain mostly pedagogical examples of the various methods that are to be used in the scheme. They also have the very early implementations of more complex functions (multi-level DWT, step-size optimisers, etc.). The final implementations of those were transfered to the ```my_(...).py``` files.

In ```experiments.ipynb``` we tested most of the functions in the ```.py``` files.

### Python files

Each python file contains functions corresponding to a different energy-compaction method. The functions implemented mostly adhere to the same structure. For example, for the DWT:

+ a ```DWT()``` function that returns the ```N```-level Discrete Wavelet Transform of the image ```X```
+ an ```inverse_DWT()``` function that returns the original image ```X``` given the DWT ```Y```
+ two functions ```quantdwt1()``` and ```quantdwt2()``` which together are used to quantise the transform ```Y``` with an arbitrary step and reduce its entropy
+ various functions that extract useful metrics of each DWT subimage, such as ```get_factors()```, ```get_ratios()```
+ optimiser functions, which find the best values for the various parameters of the scheme, e.g. the step to be used for quantisation
+ a ```DWT_quant()``` function which takes the results of the optimisers and returs the most optimal DWT of the input image
+ Huffman encoding and decoding functions
+ a ```DWT_analysis``` function, which performs the entire compression-decompression pipeline and computes error metrics and performance metrics, for experimental purposes

The ```common.py``` file contains various quantities that are useful in both the other python files and the ```experiemnts.ipynb``` notebook.

### Competition folder

This contains our final pipeline of the image encoder and image decoder. It uses various functions defined in the python files. 


