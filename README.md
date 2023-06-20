### Benchmarking ansible-core like AWX perfscale tests

Test different ansible-core installs.

```
deactivate
python -m venv env213
source ./env213/bin/activate
pip install "ansible-core<2.14"

deactivate
python -m venv env214
source ./env214/bin/activate
pip install "ansible-core<2.15"
```

```
time ansible-playbook -i inventories/hosts_100.ini chatty_tasks.yml -e num_messages=50
```

#### Numbers

Ansible 2.13

```
real	0m5.477s
user	0m18.358s
sys	0m1.371s
```

Ansible 2.14

```
real	0m17.247s
user	0m51.977s
sys	0m1.566s
```
