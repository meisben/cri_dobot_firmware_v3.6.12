# Common Robot Interface (Wrapper for dobot magician)

***Important Note***: This is an archived version of the cri_dobot libary which is compatible with v3.6.12 of the dobot magician firware.

cri_dobot is a dobot magician wrapper for the cri library from John Lloyd. It enables use of the cri library for the dobot magician robot arm. The wrapper is compatible with:

- version 3.6.12 of the dobot magician firware
- the latest [as of Feb 2020 v0.0.1] version of the cri library.

**Only the 64 bit dlls are included in this package, for details see installation instructions'

## Prerequisites
The cri library must be installed to use this wrapper: https://github.com/jlloyd237/cri

I recommend installing this libary by navigating to the directory of 'setup.py' in a terminal window, then running the command:

```sh
pip install -e .
```

## Installation (part 1)

To install the package on Windows, OS X or Linux, clone the repository and use the 'pip install' command inside the repository root directory.

It is suggested to do this in a virtual environment by:

(1) create a virtual environment (e.g. using venv or conda). 
(2) open a terminal window with the virtual environment activated
(3) navigate the the local directory of dobot_tactile_toolbox setup.py using the 'cd' command
(2) Then run the following command

```sh
pip install -e .
```

## Installation (part 2) of .dll for use with dobot magician arm: 

For both windows, mac and linux you should *not* need to do anything with the dll. This is packaged with cri_dobot. If you get an error message relating to the dll library (or are using mac) try the steps below. Please reach out for help if this isn't working!

To use the dobot dll (which is a prerequisite) follow these instructions 
- [A] use the correct DLL from dobot (64 bit or 32 bit), and
- [B] put the dll in either 
  - \cri_dobot\dobotMagician\dll_files
  - or the system root directory, for example on windows this is (%SystemRoot%\system32)

You can find the dll at (https://www.dobot.cc/downloadcenter/dobot-magician.html) - Look for Development Protocol -> 'DobotDemovX.X.zip' - Ensure you extract the correct DLL for your system (windows/linux/mac) (x64/x32)

## Usage

- For examples of basic usage with cri library see script in tests folder

## Bug list

(1) TCP

Dobot magician has a Tool Center Point (TCP) bug which means that it always assumed it's tool center point values (x,y,z) are 0,0,0. For this reason the tool center point is not currently used with the dobot magician in production code. It is yet to be determined whether this functionality will be replicated in future versions of the cri_dobot wrapper. An question has been opened on this topic in the dobot magician forums.
