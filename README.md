# Walkthrough for the bandit wargame by Overthewire.org

## Level 0

**This level requires you to just ssh over the server they provided.**<br>
The credentials are :

<pre>
    username : bandit0
    hostname : bandit.labs.overthewire.org
    password : bandit0
</pre>

Tutorial on ssh : [LearnLinuxTV](https://www.youtube.com/watch?v=YS5Zh7KExvE)

The following command format is used :

<pre>
    $ ssh user@hostname/ip -p port
</pre>

The command :

<pre>
    $ ssh bandit0@bandit.labs.overthewire.org -p 2220
</pre>

Provide the password, Don't worry if you type and can't see the password or any asteriks. Its just for security purposes. <br>

Now that we've logged in, onto the next level !

## Level 0 -> Level 1

### Logging in

<pre>
    $ ssh bandit0@bandit.labs.overthewire.org -p 2220
    password : bandit0
</pre>

The root directory has a readme file, which contains the password for the next level.<br>
We can list all the files & directory using this command:

<pre>
    bandit0@bandit:~$ ls
    readme      // This is our file
</pre>

Tutorial on filesystem navigation : [LearnLinuxTV](https://www.youtube.com/watch?v=MnY0K-3_Fjk&list=PLT98CRl2KxKHaKA9-4_I38sLzK134p4GJ&index=4)

Upon furthur inspection by using the `file` command, we get

<pre>
bandit0@bandit:~$ file readme
readme: ASCII text
</pre>

Text files can be inspected using any text editor like more, less, vim, emacs but the easiest way to do it is using the `cat` command

<pre>
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL    // This is our password
</pre>

## Level 1 -> Level 2

### Logging in

<pre>
    $ ssh bandit1@bandit.labs.overthewire.org -p 2220
    password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
</pre>

The root directory has a file containing the password, but interestingly the filename is `-` <br>

Dashed filename requires some special attention as a preceding dash is commonly used to specify options for command. <br>

Tutorial on dashed filename : [Dashed Filename](https://www.webservertalk.com/dashed-filename)

For using cat on the dashed file we can use any of the two solutions:

<pre>
    bandit1@bandit:~$ cat < -
    rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi    // This is our password
</pre>

<pre>
    bandit1@bandit:~$ cat ./-
    rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi    // This is our password
</pre>

Then we simply logout and proceed to the next level.

## Level 2 -> Level 3

### Logging in

<pre>
    $ ssh bandit2@bandit.labs.overthewire.org -p 2220
    password : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
</pre>
