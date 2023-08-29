Installing Canopy
=================

[Back to Canopy front page](../README.md)

Canopy is written in Python and integrates several existing tools for sequence alignment and phylogenetic inference. Canopy is provided as a downloadable package (works on Linux and MacOSX systems) and as a Docker image (works on all major operating systems).

### Install Canopy from the Docker image.

1.  Download (and rename) the image:
```    
docker pull veidenberg/canopy
docker tag veidenberg/canopy canopy
```    
    
Alternatively, you can build your own image from the Dockerfile in the Canopy source code package. For that, download/unpack the tarball (see step 1 in the guide below) and run the build command:
        
```    
docker build -t canopy .
```    
        
The image contains preinstalled Canopy with all the dependencies.
Runs on all major operating systems, but requires [Docker](https://www.docker.com).
2.  Run the image:
    
```    
docker run --rm -it -v "($pwd)/data:/results" canopy
```    
    
The [“-v” flag](https://docs.docker.com/storage/bind-mounts/) will provide a data folder for Canopy input/output ($pwd = current working directory).

Continue with the [usage instructions](using-canopy.md). The example dataset is included with the image (or add your own to the specified data folder). Type “exit” when done.

* * *

### Install Canopy from the source code.

*   Canopy source code is available form [here](../files/).
*   Prerequisites:
    *   Python version 2.7.x
    *   Python library dependencies:
        *   Numpy (ver. 1.14.0)
        *   Biopython (ver. 1.58)
        *   Dendropy (ver. 3.10.0)
    *   You can install these libraries manually ([using pip](https://docs.python.org/2.7/installing/index.html)) or use the Canopy installer script.

#### Install Canopy with the installer script.

*   This will install the Canopy module, the main application script and all the library dependencies.
*   You need to have [pip](https://pip.pypa.io/en/stable/) (preinstalled in Python 2.7.9+) and [setuptools](https://setuptools.readthedocs.io/en/latest/) installed first.  
    On Ubuntu Linux, these can be installed with:
    
```    
sudo apt-get install python-pip
pip install setuptools
```    
    

1.  Download Canopy, unpack it, and go to its directory:
    
```    
wget https://raw.githubusercontent.com/ariloytynoja/canopy/main/files/canopy-0.1.5.tar.gz
tar pxf canopy-0.1.5.tar.gz
cd canopy-0.1.5/
```    
    
      
    
2.  Install Canopy, either globally:
    
```    
sudo python setup.py install
```    
    
      
or for a single user:
    
```    
python setup.py install --user
```    
    
      
    
3.  Test the new Canopy installation:
    
```    
canopy test
```    
    
      
You should see the following confirmation text:  
        
```    
Succeed!
```    
        
          
or, if you installed to a Python virtual environment:
        
```    
Virtual environment is ready to launch by "source env/bin/activate"
```    
        
          
        
If some of the dependencies failed to install, you will be presented with the following options:  
        
```    
Biopython(==1.58) is not installed
Dendropy(==3.10.0) is not installed
Please choose:
  1. exit (Install the requirement libraries manually and then run the script again.)
  2. setup python virtual environment.
Your choice: [1/2]:
```    
        
          
Here, you can select to install the listed libraries manually (option 1), or retry the automatic installation in [Python virtual environment](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/) (option 2):  
        
```    
Your choice: [1/2]:2
Creating virtual environment
virtualenv env
Activating...
source env/bin/activate
Installing python packages...
pip install numpy
pip install biopython==1.58
pip install dendropy==3.10.0
```    
        
          
After this, a virtual Python environment has been set up in ./env directory.  
Enter the environment to use Canopy:  
        
```    
source env/bin/activate
```    
        
          
To exit the environment:  
        
```    
deactivate
```    
        
          
        
4.  The installation is now complete. You are ready to [run Canopy](using-canopy.md).