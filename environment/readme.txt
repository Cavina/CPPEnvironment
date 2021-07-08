###################
Chris Avina
7/7/21 - (7+7)+7^2
####################

This repo stores some scripts for my C++ environment on Linux.

Current environment:

Linux with Xubuntu Distro
Python 3.0
C++17+
C++ Compiler: Clang/Clang++
Debugger: LLDB
Test Suite: Gtest
C++ Std Lib: libc++

Notable issues in case we need to reinstall in the future:

Installation of C++/Clang was not difficult.

Difficult arose when trying compile tests because googletest couldn't find libc++.

Solution was to re-install googletest, but compile it with Clang and libc++ so that it could recognize the function
calls.

reinstallation was as follows:

sudo apt-get purge --auto-remove libgtest-dev
sudo apt-get install libgtest-dev
cd gtest
COMPILE with this command:
sudo cmake -DCMAKE_CXX_COMPILER="clang++" -DCMAKE_CXX_FLAGS="-std=c++17 -stdlib=libc++ -U__STRICT_ANSI__" cmake ..
cd googletest
sudo make

This should compile googletest with libc++





