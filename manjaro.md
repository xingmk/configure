# Manjaro install 

## Prepare  
1. Download manjaro.ios file   
Address: [manjaro.ios](https://manjaro.org/download/) 

2. Make U-disk   
Tool:[Rufus](https://rufus.ie/zh/)   
 
3. Go to ur UEFI and close these chooses    
Turn off: `Secure Boot` 


## Install 
1. Start OS from U-disk
2. Connect Wi-Fe
3. Start Installing
4. Reboot
 
## Question:
- #### Maybe your wife cann't work
 
1. Connect the wire-net  
`sudo pacman -S yay`  
2. Check your wireless network card model and download the corresponding driver  
`yay -S ...` 

> eg: if your wireless network card is rtl18821ce  
> `yay -S rtl18821ce-dkms-git` 
3. Check your linux kernel and download the corresponding headers   
`sudo pacman -S linux000-headers` 
 
> eg: if your linux kernel is 4.19   
> `sudo pacman -S linux419-headers` 

4. Restart driver  
`sudo modprobe network-card-model` 
> eg: 8821ce  
> `sudo modprobe 8821ce` 

## Change The Mirrors To China 
**First:**  
`sudo nano /etc/pacman.conf `  
 
**Add these**  
```
【archlinuxcn】
 SigLevel = Never
 Server = https: //mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```

**Execute** 
```sh
1. sudo pacman-mirrors -c China
2. sudo pacman -Syyu
3. reboot
```

## Do Some Config
- **Install editor**   
`sudo pacman -S neovim`  


- **Shell: fish**  

1. Install fish:  
`sudo pacman -S fish`

2. Change shell to fish:  
`chsh -s /usr/bin/fish`  

3. Install fish extension:  
`curl -L https://get.oh-my.fish | fish`   

4. U can change theme by this command:  
`fish_config`  
 

- **WM: i3** 
1. Install i3WM:  
`sudo pacman -S i3` 
 
2. **Modify the i3-config**   
`git clone https:github.com/Xingmk/i3.git`   
or   
`vim ~/.config/i3/config`   
 
3. Go to i3WM:
>  1. Log out your account 
> 2. In the lower right foot landing interface has a setting symbol click and select the i3 and landed


- **Terminal: st**  
`git clone https:github.com/Xingmk/st.git`  

- **Display**  
`sudo pacman -S feh variety picom`  

- **Modify keyboard** 
1. Install firstly xorg:  
`sudo pacman -S xorg`

2. The export file:  
`xmodmap -pke > ~/.xmodmap`

3. Edit it:  
`~/.xmodmap` 


- **Chinese input method** 
1. Download fcitx5   
`sudo pacman -S fcitx5-im fcitx5-chinese-addons fcitx5-pinyin-zhwiki`

2. Configure the environment variables  
`vim ~/.pam_environment`  
```
 GTK_IM_MODULE DEFAULT=fcitx
 QT_IM_MODULE  DEFAULT=fcitx
 XMODIFIERS    DEFAULT=\@im=fcitx
 SDL_IM_MODULE DEFAULT=fcitx
```

## Other stuffs 
**Look IP Address**  
`curl cip.cc` 

**Voice**   
`sudo pacman -S sof-firmware`  

```sh
1. dmenu 
 sudo pacman -S dmenu 

2. pip paru nodejs ccls 
 sudo pacman -S python-pip paru yarn nodejs ccls npm

3. music dingtalk google-chrome
 paru -S qqmusic-bin dingtalk-bin google-chrome-bin  
```

## **Git** 

```
git config –global user.name 'xxxxx'   
git config –global user.email 'xxx@xx.xxx'

ssh-keygen -t rsa -C 'xxx@xx.xxx'
```



