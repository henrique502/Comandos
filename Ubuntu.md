Comanda que lista arquivos e ou partições de swap
sudo swapon -s

Cria arquivo de swap (na raiz)
sudo fallocate -l 2G /swapfile

Muda permissoes do arquivo swap
sudo chmod 600 /swapfile

Seta o arquivo como swap
sudo mkswap /swapfile
sudo swapon /swapfile

Editar o arquivo fstab para que o swap seja configurado no boot
sudo nano /etc/fstab

adicionar ao fim do arquivo:
/swapfile   none    swap    sw    0   0

#monitor ubuntu
sudo apt-get install htop
