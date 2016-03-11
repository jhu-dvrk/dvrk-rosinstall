dVRK rosinstall
================

A rosinstall file for quickly downloading dVRK ROS packages.

## Usage

To create a new wstool space

```bash
cd /path/to/catkinws/src

# this will create a .rosinstall file 
wstool init  
```

Download and merge dvrk rosinstall file

```bash
cd /path/to/workspace/

# clone dvrk-rosinstall repo 
git clone https://github.com/jhu-dvrk/dvrk-rosinstall.git 

# checkout release version (replace VERSION with specific version e.g. 1.2.0)
git checkout VERSION

# merge rosinstall file
wstool merge /path/to/workspace/dvrk-rosinstall/dvrk.rosinstall

# update (i.e. git clone or download all source code, git submodules will be downloaded automatically)
wstool update 
```

Build as usual 
```bash
catkin build 
```

