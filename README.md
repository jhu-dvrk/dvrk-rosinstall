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

Update release (e.g. upgrade from 1.2.0 to 1.3.0)
```bash
# fetch new tag from repo
cd cd /path/to/catkinws/dvrk-rosinstall
git fetch

# checkout 1.3.0
git checkout 1.3.0

# merge & update (select yes to replace current rosinstall)
cd /path/to/catkinws/src
wstool merge /path/to/catkinws/dvrk-rosinstall/dvrk.rosinstall
wstool update
```


## Reference
- wstool: http://wiki.ros.org/wstool 
- tutorial: http://wiki.ros.org/JonathanBohren/Workspace


