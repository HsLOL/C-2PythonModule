## This repo is used to practice the C++ file to transform Python module  
Here is a way to realize this request. And it needs four files.  
* name.h file  
* name.cpp/name.c file  
* name.i file  
* setup.py file  
## You can run this demo by following steps:clap:  
* First you need a python environment(Anaconda is recommended)  
`conda create -n <env_name> python=3.6`  
`conda activate <env_name>`
Maybe you also need numpy, you can type the command line `pip install numpy` to install numpy.  
* Second Install swig  
`sudo apt-get install swig`  
* Third Create the C++/C extensionn for python
If you use the name.c file, you can do like this.
`swig -c -python polyiou.i`  
`python setup.py build_ext --inplace`  
Else you use the name.cpp file, you can do like this.
`swig -c++ -python polyiou.i`  
`python setup.py build_ext --inplace`  
* Note!
When you run the command `swig -c++/c -python polyiou.i`, there will be 2 files in the current dir (polyiou_wrap.cxx and polyiou.py files)  
Then you run the command `python setup.py build_ext --inplace`, there will be a file named `_polyiou.cpython-36m-x86_64-linux-gnu.so`.  
Finally, you can import polyiou module to check if all the steps are sucessful.  
#### Good Luck.

