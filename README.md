# multiple github accounts one computer
1. buka powershell
2. ketik akun pertama lu ssh-keygen -t ed25519 -C "email_akun_lama@gmail.com" -f "$HOME/.ssh/akun_ke1"
3. lalu ketik akun ke 2 ssh-keygen -t ed25519 -C "email_akun_lama@gmail.com" -f "$HOME/.ssh/akun_ke2"
4. buat file config type nya all files jangan ada .txt hapus
   lalu isi dengan
    Host github-akun1
        HostName github.com
        User git
        IdentityFile ~/.ssh/akun_ke1

    Host github-akun2
        HostName github.com
        User git
        IdentityFile ~/.ssh/akun_ke2
5. simpan ke C:\Users\Admin\.ssh\config

# daftarkan SSH ke github
1. ketik di powershell cat ~/.ssh/akun_ke1.pub lalu enter
2. ketik di powershell cat ~/.ssh/akun_ke12.pub lalu enter
3. nanti akan muncul ssh lalu copy
4. masuk ke github
5. masuk ke setting
6. lalu klik di sebelah kiri SSH and GPG keys atau (https://github.com/settings/keys)
7. klik new ssh title nya setarah
10. key type nya authentication key
11. lalu di bagian key copy yang muncul di powershel paste sesuai akun
12. untuk akun yang ke 2 ikutin yang nomor 11
13. lalu add SSH key
14. lalu cek di powershell ketik ssh -T git@github-akun_ke1
15. lalu cek di powershell ketik ssh -T git@github-akun_ke2
16. akan muncul Hi (nama yang kamu set)! You've successfully authenticated...

# terakhir cara ganti ganti akun nya saat project
1. git remote set-url origin git@github-akun_ke1:username_akun1/nama-repo
2. kalau ada project lain dan ingin ganti ke akun ke 2
3. git remote set-url origin git@github-akun_ke2:username_akun2/nama-repo

# detail
untuk lihat detail file nya kamu bisa ke `C:\Users\Admin\.ssh`