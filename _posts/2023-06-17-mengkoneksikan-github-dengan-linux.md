---
layout: post
title: "Menghubungkan terminal Linux dengan repository Github"
author: anonim
categories: [ linux, github ]
image: assets/images/reminder1.jpg
---

1. Buka Terminal
2. Buat kunci ssh baru dengan label email yang digunakan github
<code>ssh-keygen -t ed25519 -C "your_email@example.com"</code>

3. Setelah itu akan muncul, Untuk mempermudah langsung enter saja 
> Enter a file in which to save the key (/home/YOU/.ssh/ALGORITHM):[Press enter]
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]

4. Cek apakah ssh sudah jadi
<code>eval "$(ssh-agent -s)"</code>

5. Tambah ssh ke ssh agen
<code>ssh-add ~/.ssh/id_ed25519</code>

6. Copy isi dari kunci ssh
<code>cat ~/.ssh/id_ed25519.pub</code>

7. Tambahkan kunci ssh ke github di Settings > SSH and GPG key > New/Add SSH key
8. Tentukan folder yang akan dijadikan repository dengan
<code>git init</code>
di folder yang ingin dijadikan repository

9. Koneksikan dengan repository github yang dituju
<code>git remote add origin [paste ssh repository]</code>
*origin bisa diganti dengan apapun

10. Menyesuaikan isi folder dengan repository github
<code>git pull origin main</code>
*main itu branch

11. Jika ingin melakukan update dari komputer ke github
<code>git commit -m "update"</code>
<code>git add/rm .</code>
atau
<code>git add/rm "namafile"</code>
kemudian
<code>git push origin master</code>
jika ingin menggunakan branch baru
<code>git checkout [namabranch]</code>
jika ingin pindah branch