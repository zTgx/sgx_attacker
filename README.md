# sgx attacker

* Open Terminal A Build & Run
```shell
SGX_MODE=SW make
./app
```

STAY THERE AND DON'T PRESS ENTER.

---


* Open a new Terminal B
```shell
ps aux | grep app

ztgx       97650  1.5  0.0  26432  6068 pts/3    S+   21:55   0:00 ./app
```

* run scanmem
```shell
sudo scanmem -p 97650

enter untrusted value 987654321
```

* result
```
.ok
info: we currently have 1 matches.
info: match identified, use "set" to modify value.
info: enter "help" for other commands.
```

* set untrusted value to 1
```
set 1
```

* Back to terminal A, press enter
```shell
trusted   value  : 123456789
untrusted value  : 1
```
