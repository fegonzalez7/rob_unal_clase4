# Phantom X Robot
## Requirements

## bashrc tricks

Editing the bashrc means a great power but a huge responsibility as well.

![](https://i.redd.it/tcso5tdlzy631.png)

Edit the *bash*:

```sh
gedit ~/.bashrc
```
<details><summary>bashrc example</summary><p>

[![Screenshot-from-2022-04-02-18-36-24.png](https://i.postimg.cc/J0QnJfcd/Screenshot-from-2022-04-02-18-36-24.png)](https://postimg.cc/30dYQbqg)

</p></details></br>

Add the *aliases*, *exports*, all the stuff you want, it will allow you free the use of the terminal. Close using <kbd>ctrl</kbd>+<kbd>q</kbd>, close an reopen. 

## Git stuff

So far you have used git (it is cool, right), but there is a bunch of commands you should try.

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


## Create your own Github repo

Well, what I am presenting here is just a summary, Git and its use deserve a full course, but I am gonna try to provide the basics (again if you got a job using what you learned here, help me!).

The following example is related to the px_robot repo. So let's start. 

I just created a folder, in this case is a ROS package, so open the terminal and run:

```shell
git init
```
![](https://i.postimg.cc/JhwPtB8s/Screenshot-from-2022-03-29-20-12-36.png)

The check the status:

```shell
git status
```
![](https://i.postimg.cc/sDqJ0ZvT/Screenshot-from-2022-03-29-20-17-31.png)

It should be crying because no files/folders have been added. 

**Tip:** DO NOT ADD THE .VSCODE FOLDER.

Let's add the files.

All files:

```shell
git add .
```

All files except the .vscode folder:
```shell
 git add --all -- ':!/.vscode'
```

![](https://i.postimg.cc/x1GbykHJ/Screenshot-from-2022-03-29-20-19-05.png)

There is a more **pro** way using .gitignore, but hey google it.

Run a *git status* to check:

![](https://i.postimg.cc/m2CSJgCR/Screenshot-from-2022-03-29-20-19-16.png)

It is time to make a commit, for God's sake, add a comment.

```shell
git commit -m 'Primera version px_robot'
```

![](https://i.postimg.cc/cLWcSGB3/Screenshot-from-2022-03-29-20-20-23.png)

So far you have created a local repo, you can jump between versions, commits, etc. I encourage you to experiment by yourself, Git is useful tool.

Now it is time to create a remote repo, I know it is mainstream but Github is your friend, just go to your Github account and create a new repo. 

**Tip:** Use logical names, in this case the repo's name is the same that the package.

![](https://i.postimg.cc/52f8rqfq/Screenshot-from-2022-03-29-20-20-59.png)

Take note of the repo URL:

![](https://i.postimg.cc/d1csWnYJ/Screenshot-from-2022-03-29-20-30-21.png)

Come back to your local repo and add the remote url.

```shell
git remote add origin git@github.com:felipeg17/px_robot.git
git remote -v
```
![](https://i.postimg.cc/fR5YQtL4/Screenshot-from-2022-03-29-20-22-11.png)

The repos are linked, now just make a pull (take from the the cloud):

```shell
git pull origin master --allow-unrelated-histories 
```
Merge wit your local repo and that's it.

![](https://i.postimg.cc/5N6hCvhg/Screenshot-from-2022-03-29-20-23-01.png)

![](https://i.postimg.cc/J0dSF4kj/Screenshot-from-2022-03-29-20-22-45.png)

Now push your local repo:

```shell
git push origin master 
```

![](https://i.postimg.cc/50srHNpD/Screenshot-from-2022-03-29-20-23-32.png)

Check the internet, and voila:

![](https://i.postimg.cc/qqg52V5q/Screenshot-from-2022-03-29-20-23-47.png)

Just in case check the time line using *git log*:

```shell
git log
```

![](https://i.postimg.cc/cC8csszR/Screenshot-from-2022-03-29-20-24-05.png)

Now just repeat the process: make changes - add them - make commits - pull the repo - push your changes.

If you are using *vs code*, it determines that you have git, you can use the GUI to make commits and pushes. You must be logged with your git account into *vscode*.

<details><summary>VSCode Style</summary><p>

![](https://i.postimg.cc/CK3Gcy5d/Screenshot-from-2022-03-29-19-23-55.png)

Git detects the changes, just add them with the *+*.

![](https://i.postimg.cc/wMHhdhhp/Screenshot-from-2022-03-29-19-24-13.png)

Create a commit.

![](https://i.postimg.cc/qBXsx5TM/Screenshot-from-2022-03-29-19-24-29.png)

Push the changes.
</p></details>

**Tip:** Maybe more advanced topics are gonna be covered in the course, but in the case we could not. Check: git branches, git stage, git checkouts.

## Dynamixel packages

Just in case check the [previous class](https://github.com/fegonzalez7/rob_unal_clase3).

Because Matlab is so **freaking useless**, the dynamixel_workbench packages are not added by default. So we have to created them as custom messages.

We need to create a isolated *workspace* with these messages.
```shell
cd 
mkdir -p dyna_ws/src
cd dyna_ws/src
git clone https://github.com/ROBOTIS-GIT/dynamixel-workbench-msgs.git
cd ..
catkin build dynamixel_workbench_msgs 
```

Never source that **ws** for God sake.

Now go to matlab and on the console type:

```shell
pyenv
```
[![Screenshot-from-2022-04-02-15-18-10.png](https://i.postimg.cc/05MfcRkT/Screenshot-from-2022-04-02-15-18-10.png)](https://postimg.cc/Sj4CxPzd)

Surely it is not set up properly (**matlab is so dumb**), so type:

```shell
pyenv('Version','/usr/bin/python2.7')
```
[![Screenshot-from-2022-04-02-15-18-17.png](https://i.postimg.cc/TYncvVWQ/Screenshot-from-2022-04-02-15-18-17.png)](https://postimg.cc/MvKByj5j)

Now it is time to generate the msgs, first get the just compiled dynamixel package, in my case */home/felipe/dyna_ws/src/dynamixel-workbench-msgs*, but in your may be different. Go to matlab and type:

```shell
rosgenmsg('/home/felipe/dyna_ws/src/dynamixel-workbench-msgs')
```

It takes some time trying to compile, the dumblab ask you to follow some steps, just follow them.

[![Screenshot-from-2022-04-02-15-18-25.png](https://i.postimg.cc/3x7F8kXh/Screenshot-from-2022-04-02-15-18-25.png)](https://postimg.cc/WhWkSbYY)

```shell
addpath('/home/felipe/dyna_ws/src/dynamixel-workbench-msgs/matlab_msg_gen_ros1/glnxa64/install/m')
savepath
clear classes
rehash toolboxcache
```

If you get the following, that's fine you got it. Otherwise you are kinda f***ed. 

[![Screenshot-from-2022-04-02-15-19-39.png](https://i.postimg.cc/R0Z1t2pb/Screenshot-from-2022-04-02-15-19-39.png)](https://postimg.cc/NKZrqCc1)

Seriously I spent more than a day trying to figure out this. [Fajardo](https://github.com/jmfajardod) helped me in the end, but if you guys do not say thanks, donate and leave starts, ....well "no hay palabras...en la buena! :skull_and_crossbones: :skull_and_crossbones:".

**Notice:** join to my research team (:grin:).

**P.D:** It works on Matlab 2020b, I tried in the 2022 and it did not work, if someone managed to make it work, add it here. This is the las semester that we use Matlab.

## Issues

### cmake
Sometimes dumblab does not detect cmake, so on matlab console run:

```sh
!ckmake --version
```

If you get:

```sh
cmake: /usr/local/MATLAB/R2020b/bin/glnxa64/libcurl.so.4: no version information available (required by cmake)
cmake: /usr/local/MATLAB/R2020b/sys/os/glnxa64/libstdc++.so.6: version `GLIBCXX_3.4.26' not found (required by cmake)
cmake: /usr/local/MATLAB/R2020b/sys/os/glnxa64/libstdc++.so.6: version `GLIBCXX_3.4.26' not found (required by /usr/lib/x86_64-linux-gnu/libjsoncpp.so.1)
```

I tried a lot of things, edit the path, change dirs, anyway, what finally works:

```sh
cd 
gedit .bashrc
```

In the very last part add:

```
export LD_PRELOAD="/usr/lib/x86_64-linux-gnu/libstdc++.so.6"
export LD_PRELOAD="/usr/lib/x86_64-linux-gnu/libstdc++.so.6:/usr/lib/x86_64-linux-gnu/libcurl.so"
```

If you are using zrc just edit its config.

Save, close and rerun matlab, it should have worked. 

[![Screenshot-from-2022-04-02-18-32-11.png](https://i.postimg.cc/9FGPg01v/Screenshot-from-2022-04-02-18-32-11.png)](https://postimg.cc/XpYypVR8)

Again last time that we use matlab, it creates more problems than what it solves.

---

## The Phantom X

Time to the action. Go an clone the [px_robot](https://github.com/felipeg17/px_robot.git) repo.

<img src="https://www.trossenrobotics.com/Shared/Images/Product/PhantomX-Pincher-Robot-Arm-Kit-Mark-II/pincher.jpg" alt="px" width="400"/>

**The duel:** Make your bet...the robot vs the dogo.

<details><summary>The Fighters</summary><p>
  <img src=https://i.postimg.cc/15pncyqW/Screenshot-from-2022-04-03-01-07-50.png alt="duel" width="400"/>
</p></details>

<details><summary>The Result</summary><p>
  <img src=https://i.postimg.cc/9fHsNj0x/Screenshot-from-2022-04-03-21-30-33.png alt="dogo" width="400"/>
</p></details>

------------

`<Lab guide>` : 
------------

**Acknowledgments:**

 - Jose Manuel Fajardo
 - Sebastian Realpe 

This repo has taken a lot of effort, so consider to leave a star, [follow me](https://felipeg17.github.io/index.html), and if you feel generous I have [Paypal](https://paypal.me/fegonzalez17?country.x=CO&locale.x=en_US) (just kidding or :neckbeard:).


I have a new request: Create questions in [ROS Answers](https://answers.ros.org/users/67666/fegonzalez/) and in [stack overflow](https://stackoverflow.com/users/10837057/fegonzalez), send me the links, I will answer them. I need reputation. 

**P.D:** No animals were hurt making this repo, but a Phantom X was defeated.....:skull: :robot:
