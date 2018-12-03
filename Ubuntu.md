### Comanda que lista arquivos e ou partições de swap
```
sudo swapon -s
```
### Cria arquivo de swap (na raiz)
```
sudo fallocate -l 2G /swapfile
```
### Muda permissoes do arquivo swap
```
sudo chmod 600 /swapfile
```
### Seta o arquivo como swap
```
sudo mkswap /swapfile
sudo swapon /swapfile
```
### Editar o arquivo fstab para que o swap seja configurado no boot
```
sudo nano /etc/fstab
```
### adicionar ao fim do arquivo:
```
/swapfile none swap sw 0 0
```
### monitor ubuntu
```
sudo apt-get install htop
```

## Eclipse to the launcher

> Source: https://askubuntu.com/questions/80013/how-to-pin-eclipse-to-the-unity-launcher

First, create a .desktop file to eclipse:
```sh
gedit ~/.local/share/applications/opt_eclipse.desktop
```

Then, paste this inside (dont forget to edit Exec and Icon values):

```txt
[Desktop Entry]
Type=Application
Name=Eclipse
Comment=Eclipse Integrated Development Environment
Icon=** something like /opt/eclipse/icon.xpm **
Exec= ** something like /opt/eclipse/eclipse **
Terminal=false
Categories=Development;IDE;Java;
StartupWMClass=Eclipse
```

After that, open that folder with nautilus:

```sh
nautilus ~/.local/share/applications
```

If you want to use this launcher outside dash/launcher (ex: as a desktop launcher) you need to add execution permission by right clicking the file and choosing Properties -> Permissions -> Allow execution, or, via the command-line:

```sh
chmod +x ~/.local/share/applications/opt_eclipse.desktop
```

Finally drop `opt_eclipse.desktop` to launcher.

## Telcado US

Abra o terminal e edite o arquivo: 

```sh
vim ~/.bashrc 
```

Na última linha adicione: 

```sh
setxkbmap -model pc104 -layout us_intl
```
