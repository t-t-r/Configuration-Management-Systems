# Configuration-Management-Systems
ict4tn022-3018 - Autumn 2022

## A

Created directory 'testi' with a file init.sls. In init.sls instructions to create a file 'hellohello.txt' to my home directory
```
$mkdir /srv/salt/testi
$sudo micro /srv/salt/testi/init.sls
  /home/tuomor/hellohello.txt:
    file.managed
 ```
 Then apllied the state with the following
```
$sudo salt-call local state.apply testi
```

Git a confirmation message that the file has been created. Went to confirm. It had.


## B

Went to create some random content to the file i created in last assignment /home/tuomor/hellohello.txt file
```
$ sudo micro /home/tuomor/hellohello.txt
  this is a random sentence.
```
Then modified the init.sls file to change the content of the target file and ran the state
```
$sudo micro /srv/salt/testi/init.sls

  /home/tuomor/hellohello.txt:
    file.managed:
      - contents: "Hello World"
 
 $sudo salt-call --local state.apply testi
 ```
Got a confirmation that the content of the file 'testi was changed as instructed.
Went to see that the change had actually happened. It had.

## C

```
$sudo salt-call --local grains.items
```
Got the whole list of information with the above command. Wanted to test out how be more precise and with the following got only the info i wanted.
```
$sudo salt-call --local grains.item cpu_model kernelversion
```
Want to point out that took a while to realize the needed difference between grains.items <-> grains.item



### Sources
Tero Karivnen - https://terokarvinen.com/2018/salt-states-i-want-my-computers-like-this/
eshelman - https://gist.github.com/eshelman/8263175
