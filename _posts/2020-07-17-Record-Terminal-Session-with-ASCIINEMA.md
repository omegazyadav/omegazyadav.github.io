---
layout: post
title: 'Record Terminal Session with asciinema'
---

![asciinema](/_img/asciinema.png)
## ASCIINEMA
asciinema is a terminal session recorder which captures all the output that is being printed on the terminal. It is a light-weight 
text based terminal recorder in which you can copy the terminal text and paste it elsewhere. Installation procedure and ussage are
straight forward which won't be difficult to follow along. Furtermore you can integrate asciinema with terminal multiplexer(tmux)
to record multiple terminal session within one recordings. 

## Installation 

There are many alternatives for the installation of asciinema within your system. 

### 1. Installation with pip

``` sudo pip3 install asciinema ``` 

### 2. Installation on Linux 

Arch Linux

``` pacman -S asciinema ``` 

Debian 

``` sudo apt-get install asciinema ``` 

Fedora 

``` sudo dnf install asciinema ``` 

Geneto Linux 

``` emerge -av asciinema ``` 

openSUSE

``` zypper in asciinema ``` 

Ubuntu

``` 
    sudo apt-add-repository ppa:zanchey/asciinema 
    sudo apt-get update 
    sudo apt-get install asciinema

``` 
### 3. Installation on macOS

Homebrew

``` brew install asciinema ```

MacPorts

``` sudo port selfupdate && sudo port install asciinema ``` 

Nix

``` nix-env -i asciinema ``` 

### 4. Running on Docker Container 

Pull the official image for asciinema

``` docker pull asciinema/asciinema ``` 

Run the container 

``` 
docker run --rm -ti -v "$HOME/.config/asciinema":/root/.config/asciinema 
asciinema/asciinema 
``` 

### 5. Running from source 

Clone the github repo for asciinema and install it from the master branch 

``` 
    git clone https://github.com/asciinema/asciinema.git
    cd asciinema
    python3 -m asciinema --version

``` 

## Usage 

After the installation of asciinema, you can record the terminal session with ``` asciinema rec ``` command. 
Besides simply recording the terminal session, asciinema also has some notable features some of which are mentioned below. 

You can mention the filename of your recorded video. Just append the name of the file while recording the terminal session. 

``` asciinema rec your_file_name ``` 

When recording finishes then hit ``` CTRL+D ``` or type ``` exit ```. You can
later play that video with the command ``` asciinema play your_file_name ```.
Similarly you can upload the recorded video to the asciinema server with ``` asciinema upload your_file_name ``` command. 


## asciinema with tmux

We can use asciinema with tmux for recording multiple terminal session. Follow
the given steps to implement the asciinema with tmux.

1. Start the tmux session

    ``` tmux new -s omega ``` 
2. Create a multiple window 

    i. For vertical window use ``` [ctrl + b] + % ``` 

    ii. For horizontal window use ``` [ctrl+b]  + " ``` 

3. Detach the current tmux session with ``` [ctrl + b ] + d ``` 

4. Attach the tmux session along with asciinema 

    ``` asciinema rec -c "tmux attach -t omega" ``` 

5. After recording completed, detach the tmux session and save the recording. 

#### Voila! See the recording with the given link shown in your screen. 





