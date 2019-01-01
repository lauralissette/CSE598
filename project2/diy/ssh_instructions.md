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

* Press **Details** button on vocareum > then press the **show** button. Copy the **SSH key**
* On your local machine, create a file called **key.pem** using any text editor of your choice. I prefer using vim:
```
  vim key.pem
```
* Paste the copied key into the **key.pem** file. It should look something like this:

```
-----BEGIN RSA PRIVATE KEY-----
5XP2i5HKfyzBe1qSWn+qL66HnVU9NarVoU53F58Q/3O1bqpX/sph6olwg89ScRWSIBaWSfm6cCgYA0aYHmWn6zz9E/+HqHVjAIMEXJ4NbFNsPf6mITOfujpVOhP5Qwi25fSlpX+jT8yrwYbu2BRLtKH12bUUWYOK6uqqCiW1Q1dBnuRaEtBTUaipDJWH4/yLFkkajgN/u3B6kes8LiKbN6vF1zbdQIKtUL1iE6wVcl73vj/7ism3m6QKBgGFv2gwQ8qB5sXheHRtM6iQn2IDdnyjaczAm6uw5L/eKMhBluBVcNMlPwGsV3dI4DFgSp+NCRjG7i3WofRrtPl6t9hJ1gLPYQTSF/KpryEfT+LtG5RfLg8tbBCOcBx6fqmpeDtWNxlqrEfxMrjWPxR4NcZFwsV8l7bdXJVvsIpAoGAQb0twRy/njdxt6/mv2zDTz02HErvrRtzcAfw1kHG6Iw4lmNIri62O2pphUqof9woTIBqkTnXf1fw9nk9MR24T5ainna4hifoUhcNst7Yp61YJElSQuh/QzZgCyhtkQYsJ+MiuXFMMQA8i2Uu+gUjwnkJI3xjXOQf6TMUmyn2l8Y
-----END RSA PRIVATE KEY-----
```
* Save the file using **Esc + :wq**
* Now on Vocareum, Click on the Start Lab button
* Click on the AWS button that would take you to the AWS console.
* Search EC2 in the search box. You must have one running instance.
* Click on the Running instance > Scoll down and copy the public IP of the running instance.
* Now use this command to ssh into the virtual machine:
```
ssh -i key.pem ubuntu@<EC2publicIP>
```