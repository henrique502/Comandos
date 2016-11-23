### Libera portas abaixo da 1024 para o node
```
sudo setcap cap_net_bind_service=+ep /usr/bin/nodejs
```
### Alias node ubuntu antigos
```
sudo ln -s /usr/bin/nodejs /usr/bin/node
```
### PM2 comandos
```
pm2 logs 4park [--lines 1000]
```
```
pm2 start index.js -i 2 --name '4park'
```
