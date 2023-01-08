
Installing and upgrading Ansible
Locating Python
Locate and remember the path to the Python interpreter you wish to use to run Ansible. The following instructions refer to this Python as python3. For example, if you’ve determined that you want the Python at /usr/bin/python3.9 to be the one that you’ll install Ansible under, specify that instead of python3.

Ensuring pip is available
To verify whether pip is already installed for your preferred Python:

python3 -m pip -V
If all is well, you should see something like the following:

python3 -m pip -V
pip 21.0.1 from /usr/lib/python3.9/site-packages/pip (python 3.9)
If so, pip is available, and you can move on to the next step.

If you see an error like No module named pip, you’ll need to install pip under your chosen Python interpreter before proceeding. This may mean installing an additional OS package (for example, python3-pip), or installing the latest pip directly from the Python Packaging Authority by running the following:

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --user


Installing Ansible
Use pip in your selected Python environment to install the Ansible package of your choice for the current user:

python3 -m pip install --user ansible
Alternately, you can install a specific version of ansible-core in this Python environment:

python3 -m pip install --user ansible-core==2.12.3
Upgrading Ansible
To upgrade an existing Ansible installation in this Python environment to the latest released version, simply add --upgrade to the command above:

python3 -m pip install --upgrade --user ansible




sudo apt install ansible


ansible --version



sudo dnf install python3 python3-pip -y



sudo dnf -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm

sudo dnf install  --enablerepo epel-playground  ansible

# Installing the epel-release package using the yum command yum install epel-release
yum install epel-release
