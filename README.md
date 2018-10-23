# CTFbox
Setting up Linux VM with CTF tools

## Vagrant


## PwnDBG

### Capstone
First, setup [Capstone](https://github.com/aquynh/capstone)
```
git clone https://github.com/aquynh/capstone
cd capstone
git checkout -t origin/next
./make.sh
sudo ./make.sh install
cd bindings/python
sudo python2 setup.py install # Ubuntu 12.04, GDB uses Python2
sudo python3 setup.py install # Ubuntu 14.04+, GDB uses Python3

```

### UnicornEngine
Then, setup [UnicornEngine]()

```
sudo apt-get install libglib2.0-dev
git clone https://github.com/unicorn-engine/unicorn
cd unicorn
./make.sh
sudo ./make.sh install
cd bindings/python
sudo python2 setup.py install # Ubuntu 12.04, GDB uses Python2
sudo python3 setup.py install # Ubuntu 14.04+, GDB uses Python3
```
### Requirements

Install Python packages from [requirements](../blob/master/requirements.txt)
```
sudo pip install -Ur requirements.txt --user
```
**Note**:

You may get the following warning messages if you're running Ubuntu and Python 2.7.3:
```
/usr/local/lib/python2.7/dist-packages/pip/_vendor/urllib3/util/ssl_.py:160: InsecurePlatformWarning: A true SSLContext object is not available. This prevents urllib3 from configuring SSL appropriately and may cause certain SSL connections to fail. You can upgrade to a newer version of Python to solve this. For more information, see https://urllib3.readthedocs.io/en/latest/advanced-usage.html#ssl-warnings
  InsecurePlatformWarning
```
Since,they're just warnings you can ignore them for now. Or look into the following solutions to fix: [1](https://stackoverflow.com/questions/29134512/insecureplatformwarning-a-true-sslcontext-object-is-not-available-this-prevent)[2](https://urllib3.readthedocs.io/en/latest/advanced-usage.html#ssl-warnings)


References:
[Exploit Development and Reverse Engineering with GDB Made Easy](https://libraries.io/github/pwndbg/pwndbg)

### Finally, install `PwnDBG`
```
git clone https://github.com/zachriggle/pwndbg
echo "source $PWD/pwndbg/gdbinit.py" >> ~/.gdbinit
```
