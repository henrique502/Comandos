# portas
sudo setcap cap_net_bind_service=+ep /usr/bin/nodejs

# alias node ubuntu antigos
sudo ln -s /usr/bin/nodejs /usr/bin/node

# PM2 ver logs
pm2 logs 4park [--lines 1000]
