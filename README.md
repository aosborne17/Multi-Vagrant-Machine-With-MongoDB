# MongoDB Configuration and Understanding Variable Persistence in Linux :penguin: :computer:


## Different Types Of Variables

There are two types of variables
- Environment variables
- Normal variables


Each Virtual Machine is an environment, we can make variables within this environment


### Creating a Variable

```bash
name = "eng-67"
```

Displaying the value of the variable
``` echo $name```


store the command value in your variable and then display it
``` dir=$(pwd)```

``` echo $dir```
- When the user, enters the above command it will show them their current location, the variable has stored a linux command
- This is how organisations are able to create shortcuts that we use day to day

---

### How to create ENV variable in linux

``` export name="eng-67"```

For the variable we have created to become an environment variable, we must use the export command

``` env ``` is a command that lists to us all the available environment variables, we can do this to check if the variable
we created is present


## Steps to Creating an Environment variable and using it from a Bash Script

### 1) Within the VM, make your way to the /app directory and create a bash script
```bash
touch env_var.sh
```
---

### 2) We then entered the file and inputted the following code
```bash
name="Andrew"
echo $name

dir=$(ls)
echo $dir
```
---

### 3) Allowing Permission to the script file
```bash
chmod +x env_var.sh
```
Now when we run the script in the terminal we should see both our name
as well as the current components of the folder

---

 
 
## Permanently storing Variables 

### 1) Locate the .profile file

- After doing the sudo su command to become root user, locate to the /vagrant folder within the
VM, then type ls -a and this should show us the .profile file

- Note that the command ``` ls -a ``` allows us to see all the hidden files, this is where .profile is located
```bash
nano .profile
```
This will allow us to enter the profile file.


- When you create a profile inside a vm, it will inherit everything inside .bashrc
- Our vagrant file and our Virtual Machine are two different things, when we do vagrant destroy
our VM is destroyed but our vagrant folder is still there
thus .profile is still present.

---
### 2) Adding the export command to the file to make it persistent
 
- Once inside the profile file, scroll to the bottom and add the following command
```bash
EXPORT DB_HOST="mongodb://192.168.10.111:27017/posts"
```
---
### 3) Making sure the variables have persisted

- After having done these steps, we can save the file and exit the Virtual Machine
- We then run ``` vagrant ssh app``` and type ``` env ```

If we are able to see the variable that we have created, our variable has persisted!

![Persistent Data](images/checking_variable_persistence.png)


