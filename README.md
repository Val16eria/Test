# Working with Git via the console


## Let's check the availability of Git

```
git --version
```


## Setting up Git

Add a name (enter it inside the quotation marks):
```
git config --global user.name "your name"
```

Add email (replace email@example. com to your email):
```
git config --global user.email email@example.com
```


## Checking SSH-keys

Before creating a new SSH key, let's check if there are other keys on the computer
```
ls -al ~/.ssh
```


## Creating a new key

```
ssh-keygen -t ed25519 -C "your_email@example.com"
or
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

The terminal will ask where to save the key. If you don't want to change the file name that the terminal offers, just press Enter
```
Generating public/private имя-ключа key pair.
> Enter a file in which to save the key (/c/Users/ваш-профиль/.ssh/id_имя-ключа):*[Press enter]*
```

Now you need to add a password that will encrypt your key. It's worth doing, otherwise there may be problems with the setup in the future, and it's just safer that way.
As a result, a new SSH key is created, linked to your email

<p align="center">
<img src="https://user-images.githubusercontent.com/85391921/216120470-645447bc-a40e-44bb-bb91-eda4be8bc3dd.png"/>
</p>


## Copying the SSH key

```
cat ~/.ssh/id_ed25519.pub

ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIO63MT6VCFuZtCLhLj1J6I7dgEU2BsRdIsnvnr4ax+Fr shklyar@htmlacademy.ru
```


## Adding an SSH-key to GitHub

Go to the key management page in your GitHub profile and click the New SSH key button

<p align="center">
<img src="https://user-images.githubusercontent.com/85391921/216121868-5d5855b7-956e-42a5-9780-4fa3b0c23d58.png"/>
</p>

Paste the key that you copied in the last step into the Key field

<p align="center">
<img src="https://user-images.githubusercontent.com/85391921/216122204-3ccf7466-12f0-40b7-9691-f2b97c9c1171.png"/>
</p>

Now click the Add SSH key button and, if necessary, enter your GitHub password to confirm saving

<p align="center">
<img src="https://user-images.githubusercontent.com/85391921/216122397-616d3b51-3350-4739-8450-9a6676d4ce9d.png"/>
</p>


## Git clone

Open the terminal and go to the folder with the future project — for this we use the cd your-project command. If you want the project to be in the device folder, enter

```
cd device
```

When you go to the folder, enter the git clone command to clone the repository:

```
git clone git@github.com:your-nickname/your-project.git
```

Replace your-nickname with your username on GitHub, and your-project with the project name

If you have configured SSH keys correctly, Git will copy the repository to your computer.

```
➜  device git clone git@github.com:academy-student/1173761-device-34.git
Клонирование в «1173761-device-34»…
remote: Enumerating objects: 15, done.
remote: Counting objects: 100% (15/15), done.
remote: Compressing objects: 100% (14/14), done.
remote: Total 15 (delta 0), reused 15 (delta 0), pack-reused 0
Получение объектов: 100% (15/15), 145.07 КиБ | 900.00 КиБ/с, готово.
```


## Creating a new branch

If we are in master , then we create a new branch with the command

```
git checkout -b имя-новой-ветки
```

```
➜  1173761-device-34 git:(master) git checkout -b task1
Переключено на новую ветку «task1»
➜  1173761-device-34 git:(task1)
```


## Saving changes — git add

To save all changes at once, use the command

```
git add -A
```


## Making a commit — git commit

```
git commit -m "ваше сообщение"
```


## Sending changes to GitHub — git push

```
git push origin название-текущей-ветки
```
