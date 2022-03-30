# Phantom X Robot
## Requirements
---
So far you have used git (it is cool, right),but there is a bunch of commands you should try.

### Setting the ssh key
It is the easiest way to interact with you git hub repo. Go to your home folder and generate the SSH key.

```shell
cd ~
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
![](https://i.postimg.cc/4NHshRG0/Screenshot-from-2022-03-29-18-47-04.png)

```shell
cd .ssh/
ll
cat id_rsa.pub 
```

![](https://i.postimg.cc/Mpkx73Kp/Screenshot-from-2022-03-29-18-47-33.png)

![](https://i.postimg.cc/7Zg4m1fM/Screenshot-from-2022-03-29-18-47-47.png)

Copy the key and then go to your github settings and paste the ssh key.

![](https://i.postimg.cc/TP06XRjK/Screenshot-from-2022-03-29-18-55-50.png)

From now you can use the ssh link in your repositories, it is easier, trust me.

![](https://i.postimg.cc/d1FjGYgj/Screenshot-from-2022-03-29-19-15-50.png)

If you have any doubts, consider visit this [link](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

### Setting the user and name
In order to link your name and email to git, just run:

```shell
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```
Then:

```shell
git config --list
```
![](https://i.postimg.cc/SKkh5X90/Screenshot-from-2022-03-29-18-51-59.png)

### Dynamixel packages

Just in case check the [previous class](https://github.com/fegonzalez7/rob_unal_clase3).

---

## The Phantom X



