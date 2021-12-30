+++
date = 2021-12-07T10:25:12Z
title = "Got error while installing nodejs"

+++
# Got error while installing nodejs

kamu dapat mengakses issue ini di link berikut . [klik disini!](https://github.com/nodesource/distributions/issues/1157 "Error Nodejs")

Untuk teman-teman yang punya masalah yang sama:

    cd /etc/apt/sources.list.d 
    sudo rm nodesource.list

update apt, fix the install, hapus **nodejs** dan **nodejs-doc** packages

    sudo apt --fix-broken install
    sudo apt update
    sudo apt remove nodejs
    sudo apt remove nodejs-doc

Install nodejs terbaru, untuk saat ini tersedia versi 17.

  
`curl -fsSL `[`https://deb.nodesource.com/setup_16.x`](https://deb.nodesource.com/setup_16.x "https://deb.nodesource.com/setup_16.x")` | sudo -E bash -
sudo apt-get install -y nodejs
`