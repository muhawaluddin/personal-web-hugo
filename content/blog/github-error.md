---
title: "Solusi Github SSH Error"
date: 2021-12-05T14:29:51+08:00
draft: false
---


## Mengapa menggunakan SSH?

- Alasan Keamanan repository anda.
- Tidak repot menuliskan username dan password setiap kali Push & Pull.
- Lebih cepat akses ke remote server.
- Cara kerjanya adalah Github mengidentifikasi laptop anda dengan key number.

## Cara Generate SSH baru di laptop anda.

Jika tidak yakin apakah anda sudah memeliki SSH Key dilaptop?

Cara cek SSH di laptop anda, ketik dibawah ini:

```
cat ~/.ssh/id_rsa.pub 
```

Apabila muncul kode seperti ini :

```
ssh-rsa AAAAB3Nza..xxxxxxxxxxxxxxxxxxxyyyyyyyyyyyyyyyyyyyyyyyyyyzzzzzzzzzzzzzzzzzzzxxxxxxxxxxxxxxxxxxxxxxxyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzxxxxxxxxxxxxxxxxxxxxxxxxxxyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyzzzzzzzzzzzzz dyo-medio@dyo-mac.local 
```

xyz adalah key yang saya samarkan :)

### Apabila tidak muncul baris seperti diatas?

Anda harus generate key baru, caranya:

```
ssh-keygen -t rsa -b 4096 -C "email_anda@contoh.com" 
```

Kemudian muncul pertanyaan, anda enter-enter saja untuk set secara default.

### Apabila muncul baris seperti diatas?

Anda harus menambahkan key tsb ke SSH-Agent, cara nya:

```
eval $(ssh-agent -s)
--> akan muncul: Agent pid xxxxx 
```

Tambahkan key ke ssh-agent:

```
ssh-add -K ~/.ssh/id_rsa 
```

Kemudian tambahkan SSH key ke account Github anda.

Sebelumnya copy dulu key anda ke clipboard, dengan cara:

```
pbcopy < ~/.ssh/id_rsa.pub 
```

Anda login ke account github.com, dengan langkah:

1\. Ke profile anda. Klik Setting.

<img src=":/41225097167545a09fa8efd76be90b8f" alt="14d17e9d22628f4691de49e0b9ebb614.png" width="114" height="290" class="jop-noMdConv">

2\. Klik ssh key.

<img src=":/3f13335e53374d588a7420272ee68add" alt="af79ce634abf5a64070c7fbf5df810f8.png" width="140" height="164" class="jop-noMdConv">

3\. Beri nama pada form. Paste key ke dalam kotak yang disediakan.

<img src=":/f1000848019e4ee28aad2b5aa8111c87" alt="cb32606c529b9eccb5d3345c42972a8c.png" width="362" height="204">
