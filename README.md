dVRK rosinstall
================

A rosinstall file for quickly downloading dVRK ROS packages.

## Usage

Install wstool if not installed 
```bash
# apt-get
sudo apt-get install python-wstool

# or when that's not possible, use pip 
sudo pip install -U wstool 
```


To create a new wstool space

```bash
cd /path/to/catkinws/src

# this will create a .rosinstall file 
wstool init  
```

Download and merge dvrk rosinstall file

```bash
cd /path/to/catkinws

# clone dvrk-rosinstall repo 
git clone https://github.com/jhu-dvrk/dvrk-rosinstall.git 

# checkout release version (replace VERSION with specific version e.g. 1.2.0)
git checkout VERSION

# merge rosinstall file
cd /path/to/catkinws/src
wstool merge /path/to/catkinws/dvrk-rosinstall/dvrk.rosinstall

# update (i.e. git clone or download all source code, git submodules will be downloaded automatically)
wstool update 
```

Build as usual 
```bash
catkin build 
```


## Reference
- wstool: http://wiki.ros.org/wstool 
- tutorial: http://wiki.ros.org/JonathanBohren/Workspace


