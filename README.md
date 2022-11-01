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

