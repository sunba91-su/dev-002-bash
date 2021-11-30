# dev-002-bash
dwsclass dev-002-bash

[@dwsclass](https://github.com/dwsclass)dws-dev-002-bash
## introducing
In this repository, we do a dwsclass exercise that identified by `dev-002-bash` ID

There are two files in this repository that means the exercise has two steps.
## step1
In step 1 ,the  `try`  file  we pass some arguments ( -I for delay period nad -n for repeat time ) at the end we pass some commands to this shell script.

#### Example
./try1 [arguments] COMMAND
```bash
./try1 -i 60 -n 5 systemctl start nginx
./try1 -n 6 -i 20 systemctl enable nginx
```

In shell script :
It Gets an argument and sets each to its self variable then saves the ordered command to a variable.

At the first time run command and if ordered command exit with 0 code the script exit with 0 code 

If the ordered command exit with non-zero code, the script run again script in some period that config it in by passing arguments. if the loop ended and ordered command exit with non-zero code the times, script print some errors in stderr and exit with 1 code.

## step2
In step 2 we improved our code!!

#### Example
./try2 [arguments] COMMAND 
```bash
./try2 -i 60 -n 5 systemctl start nginx
./try2 -n 6 -i 20 systemctl enable nginx
./try2 -i 20 systemctl restart nginx
./try2 -n 10 service cups start
./try2 service cups start
```

In this improvement, if you don’t pass the arguments it will get that argument from environment variables and if there is not an environment variable to read from that, it will use default value; but it is necessary to pass the command to it and if no any command passed to this shell script, script exit with 1 code and print an error in stderr
##### default values and environment variables:
`TRY_INTERVAL=5 , TRY_NUMBER=12`
