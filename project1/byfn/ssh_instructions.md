To access the AWS Virtual Machine:
----------------------------------

There are 2 ways to access the AWS virtual machine:

1. Using vocareum command prompt
2. Using your personal computer terminal/command prompt

 **Using Vocareum command prompt:**

1. Click on the Start Lab button
2. Click on the AWS button that would take you to the AWS console.
3. Search EC2 in the search box. You must have one running instance.
4. Click on the Running instance > Scoll down and copy the public IP of the running instance.
5. Now use this command to ssh into the virtual machine:

```
ssh -i .ssh/labsuser.pem ubuntu@<EC2publicIP>
```
Replace \<EC2publicIP> with the IP that you had copied earlier.

When asked about the verification enter yes and you'll be inside your virtual machine.

You have root access to this virtual machine which means you can run any command as super user.

**Using your personal machine terminal/command prompt:**

Make sure SSH is installed on your virtual machine.After that you can follow these steps to SSH into the virtual machine:

* Now on Vocareum, Click on the Start Lab button
* Click on the AWS button that would take you to the AWS console.
* Search EC2 in the search box. You must have one running instance.
* Click on the Running instance > Scoll down and copy the public IP of the running instance.

**!!! Before running the ssh command please ensure that the EC2 instance has completed all the initializatons**

Execute the following command on veocareum terminal
```
  cp .ssh/labsuser.pem key.pem
```
You'll notice at the left hand side a new file has been added to the work directory. Highlight that **key.pem** file and download it on your local machine.

Change the mode to 400 using
```
sudo chmod 400 key.pem
```


* Now use this command to ssh into the virtual machine:
```
ssh -i key.pem ubuntu@<EC2publicIP>
```