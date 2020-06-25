# Personal fusuma setup

The purpose of this repo is to keep track of my `fusuma` `config.yml` and to document my process of setting up `fusuma` just in case I need to do this again.

The user that is going to be using `fusuma` has to be a member of the system's input group - this is to allow the user to read from the input devices. This cand be done with the following command (assuming the current user is the user that will be using `fusuma`

```
sudo gpasswd -a $USER input
```

# Installing dependencies

## libinput-tools

This is just an input device management tool

```
sudo apt install libinput-tools
```

## xdotool

This is a program used to mock mouse and keyboard inputs

```
sudo apt install xdotool
```

## fusuma

This is assuming that ruby is setup (preferrably using rvm) 

"Fusuma is multitouch gesture recognizer. This gem makes your linux able to recognize swipes or pinchs and assign commands to them." [gem github](https://github.com/iberianpig/fusuma)


```
gem install fusuma
```

# Setting up the config

Now just put the `config.yml` that is stored in this repo @ `/.config/fusuma/`. After restarting your terminal you could then just run:

```
fusuma
```
the command should read the `config.yml` which will cause the `Present Windows (All desktops)` function to run on both 3-finger up & 3-finger down.

Note: the `Present Windows (All desktops)`'s default key bindings are not `ctrl+alt+0` as shown in the `config.yml` these are custom keybindings added under `System settings` > `Global Shortcuts` > `Kwin`

Note: `fusuma` has to be running for gestures to work. I created a simple startup script which just runs `fusuma` to allow the gestures to always be running.
