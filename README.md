NS-3 installation & running scripts
WAZID ULLAH MURAD·SATURDAY, FEBRUARY 22, 2020·
NS-3 is most preferable for Linux(Ubuntu/Mint).so, here’s the installation process for ubuntu/Mint is given.
Step 1: installing libraries:
open Terminal (ctrl+Alt+T) & run the following commands one after one. if it requires (Y/N) anytime, then simply write Y & press ‘Enter’ button.
sudo apt-get install gcc g++ python python3
sudo apt-get install gcc g++ python python3 python3-dev
sudo apt-get install python3-setuptools git mercurial
sudo apt-get install qt5-default mercurial
sudo apt-get install python-pygraphviz python-kiwi python-pygoocanvas libgoocanvas-dev ipython

sudo apt-get install gir1.2-goocanvas-2.0 python-gi python-gi-cairo python-pygraphviz python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython ipython3
sudo apt-get install openmpi-bin openmpi-common openmpi-doc libopenmpi-dev
sudo apt-get install autoconf cvs bzr unrar
sudo apt-get install gdb valgrind
sudo apt-get install uncrustify
sudo apt-get install doxygen graphviz imagemagick
sudo apt-get install texlive texlive-extra-utils texlive-latex-extra texlive-font-utils texlive-lang-portuguese dvipng latexmk

sudo apt-get install python3-sphinx dia
sudo apt-get install gsl-bin libgsl-dev libgsl23 libgslcblas0
sudo apt-get install tcpdump
sudo apt-get install sqlite sqlite3 libsqlite3-dev
sudo apt-get install libxml2 libxml2-dev
sudo apt-get install cmake libc6-dev libc6-dev-i386 libclang-6.0-dev llvm-6.0-dev automake pip
python3 -m pip install --user cxxfilt
sudo apt-get install libgtk2.0-0 libgtk2.0-dev
sudo apt-get install vtun lxc uml-utilities
sudo apt-get install libboost-signals-dev libboost-filesystem-dev
Step 2: Download NS-3 & extract:
download the ns3 from here: https://drive.google.com/file/d/1vRMryHof4cBH0Zs4Z3WbxpayM3nLMaTP/view?usp=sharing
now place the file in home folder..

now, open Terminal (ctrl+Alt+T) & run the following commands:
echo $HOME
tar jxvf ns-allinone-3.30.tar.bz2
it will extract the ns3 folder ... now we have to run the commands..
cd ns-allinone-3.30/ns-3.30
./build.py --enable-examples --enable-test
it will take about 30 minutes... :) .. keep patience..
go to the folder.. home/ns-allinone-3.30/ns-3.30/examples/tutorial   ..& copy the files..
first.cc , first.py 
& paste them into..  /home/ns-allinone-3.30/ns-3.30/scratch  .. folder.
now, you are ready to run your fisrt lab code first.cc

Step 3: Running first script( first Lab code):
cd
cd ns-allinone-3.30/ns-3.30
run the .cc file:
./waf --run scratch/first


successfully running first.cc file
run the .py file:
./waf --pyrun scratch/first.py

done.....................................
if u face any problem..feel free to share screen live at.. google hangouts(wazidullahmurad@gmail.com)  or use AnyDesk software (remote desktop software)
