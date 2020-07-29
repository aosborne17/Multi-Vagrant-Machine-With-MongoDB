Note that we are drivers of the product, understanding what is going on under the bonnet and how to write JS is for the
front end team.

As DevOps engineers all we need to know is how to integrate these different parts together to integrate and get the 
product live.

In order to set up mongoDB we must have mongo.config as well as mongo.

must create a variable to make data persistent in a database

There are two types of variables
- Environment variables ---> Use these inside an environment, for example a virtual machine
- Normal variables


Each VM is an environment, we create variables within our app VM

How to create ENV variable in linux

```bash
name = "eng-67"
```

Displaying the value of the variable
``` echo $name```


store the command value in your variable and then display it
``` dir=$(pwd)```

``` echo $dir```

This is how organisations are able to create shortcuts that we use day to day

``` export name="eng-67"```

``` env ``` is a command that lists to us all the available environment variables