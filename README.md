# Coding In Mobile

Halo! Pernakah kalian berpikir untuk mengikuti modul pembelajaran RPN namun belum punya laptop / pc sebagai penunjang kegiatannya ? Maka disini kalian akan belajar cara menggunakan hp kalian sebagai penunjang belajar coding.

## Pendahuluan
Termux merupakan terminal emulator yang mengemulasikan linux environment di device android kalian. Aplikasi ini memungkinkan untuk mengakses tool linux dan sebagainya hanya dengan lewat simulasi.

Oleh karena itu sebenernya kita akan belajar coding lewat device yang terinstall linux, namun linux itu sendiri kita emulasikan di hp kita menggunakan aplikasi termux ini.


## Instalasi


### Instal F-Droid
F-Droid merupakan alternative app store selain playstore yang FOSS (Free Open Source Software). Di app store ini kalian bisa mendapatkan aplikasi aplikasi FOSS yang sangat respect terhadap privacy user, dan juga tranparasi terhadap user.

Kalian Bisa Download aplikasinya terlebih dahulu [disini](https://f-droid.org/en/).

### Instal Termux
1. Pertama buka App F-Droid dan klik tombol search
![step-1](/assets/termux-instalation/step-1.png)

2. Setelah kalian search pastikan memilih aplikasi termux yang benar
![step-2](/assets/termux-instalation/step-2.png)

3. Klik Instal dan tunggu sampai proses download selesai
![step-3](/assets/termux-instalation/step-3.png)

4. Jika Muncul peringatan seperti ini klik settings lalu nyalakan "Allow From This Source" atau "Izinkan dari sumber ini" atau kata kata yang serupa.
![step-4-1](/assets/termux-instalation/step-4-1.png)
![step-4-2](/assets/termux-instalation/step-4-2.png)

5. Jika Sudah muncul aplikasi termux di beranda klik, lalu kalian akan melihat "Welcome To Termux!" di barisan paling atas maka kalian berhasil menginstall termux di hp android kalian!
![step-5-1](/assets/termux-instalation/step-5-1.png)
![step-5-2](/assets/termux-instalation/step-5-2.png)

## Instal Code Editor (Neovim)

Selamat Kalian sudah berhasil dalam menginstal termux, sebelum kita menginstal code editor mari kita benahi environment linux kita terlebih dahulu dan menginstall dependensi untuk code editor kita.

### Setup Repository

1. Pertama kita harus mensetup, storage, dan juga repository termux. jalankan perintah berikut di termux kalian:
```bash
termux-change-repo
```
![step-1](/assets/storage-setup/step-1.png)

2. Setelah itu kalian akan dihadapkan dengan pilihan berikut. Kalian pilih saja yang mirror group.

> Gunakan tanda panah untuk navigasi atas bawah dan enter untuk memilih.
![step-2](/assets/storage-setup/step-2.png)

3. Setelah itu kalian pilih saja yang asia.
![step-3](/assets/storage-setup/step-3.png)

4. Tunggu Proses hingga selesai (Hingga kalian bisa memasukan perintah lagi). Setalah kalian bisa memasukan perintah lagi. masukan perintah berikut.
```bash
pkg update -y
pkg upgrade
```
![step-4](/assets/storage-setup/step-4.png)

> Jika kalian diberikan pilihan saat instalasi. gunakan pilihan default saja.

Oke selamat dengan begini kalian sudah berhasil membuat package manager dalam keadaan baru dan siap untuk kita gunakan untuk menginstall tool kita.

### Instalasi Tool
Mari kita install tool berikut untuk menunjang kegiatan coding kita.

- **Git** merupakan tool yang kita gunakan untuk version control project kita, tool ini wajib sekali di kuasai ntuk seorang programmer.
- **NodeJS** merupakan sebuah runtime javascript yang akan kita gunakan untuk mengeksekusi project kita. Karena kita juga akan mengikuti pembelajaran modul dari RPN yang notabenenya menggunakan javascript. kita wajib untuk instalasi tool ini. tool ini juga berguna untuk code editor kita karena Sebagian besar language server dijalankan oleh nodejs
- **Clang** merupakan tool yang digunakan untuk compiling code c / c++. karena nanti kita akan berurusan dengan lazy loading, maka clang ini dibutuhkan untuk mengcompile code yang dibutuhkan oleh code editor kita.
- **Neovim** code editor atau ide yang akan kita gunakan!.

Tool diatas bisa kita bach install dengan perintah berikut
```bash
pkg install git nodejs clang neovim
```

Setelah itu kita check apakah sudah terintstall dengan commandn berikut
```bash
clang -v
git -v
node -v
nvim -v
```

jika command merespon, dan memperlihatkan versi mereka maka kalian sudah berhasil menginstall tool tersebut

![step-1](/assets/tool-instalation/step-1.png)

### AstroNvim (Config Neovim)
AstroNvim merupakan salah satu config neovim yang dapat mensulap neovim menjadi sebuah ide. Makanya disini kita hanya tinggal mengclone confignya dan menggunakannya di neovim kita tanpa perlu repot setup ini itu.

```bash
git clone --depth 1 https://github.com/AstroNvim/template ~/.config/nvim
rm -rf ~/.config/nvim/.git
nvim
```

Tunggu hingga prosesnya selesai sampai nanti muncul menu utama.

![step-1](/assets/astro-nvim-instalation/step-1.png)
![step-2](/assets/astro-nvim-instalation/step-2.png)
![step-3](/assets/astro-nvim-instalation/step-3.png)

> untuk keluar dari nvim gunakan perintah `:q!` lalu enter
> ![step-4](/assets/astro-nvim-instalation/step-4.png)
> untuk perintah keluar dari nvim ini kalian harus selalu ingat. karena kita tidak bisa keluar nvim menggunakan CTRL + C (SIGINT) seperti program kebanyakan.

### Instal Nerd Font
Setelah Kita lihat lihat aplikasi nvim kita kekurang icon. oleh karena itu kita harus memasang nerd font sebagai provider untuk icon icon nya.

Kalian bisa lihat lihat disini terlebih dahulu https://www.nerdfonts.com/font-downloads

setelah menemukan font yang kalian suka misal "0xProto" disini kita salin dulu link download yang ada pada tombol downloads

![step-1](/assets/nerd-font-instalation/step-1.png)

Buka termux lalu buatlah folder dengan perintah
```bash
mkdir fonts
```
setelah itu kalian pindah ke directory fonts
```bash
cd ./fonts
```
download font dengan curl
```bash
curl -FO https://github.com/ryanoasis/nerd-fonts/releases/download/v3.3.0/0xProto.zip
```
setelah proses download selesai kalian unzip font nya
```bash
unzip 0xProto.zip
```
Setelah di unzip kalian ketik perintah `ls` untuk melihat isi dari directory fonts kita.
![step-2](/assets/nerd-font-instalation/step-2.png)

Perhatikan nama font! pastikan pilih yang mono atau yang regular misal disini ingin menginstal yang **0xProtoNerdFont-Regular.ttf** maka kalian harus mengetikann perintah berikut
```bash
mv 0xProtoNerdFont-Regular.ttf ~/.termux/font.ttf

termux-reload-settings
```

Buka kembali nvim. jika berhasil maka icon akan muncul
![step-3](/assets/nerd-font-instalation/step-3.png)

ditahap ini kalian sudah berhasil untuk mengubah font dan memunculkan icon di astro nvim

## Percobaan Mensubmit Materi RPN
Untuk environment kalian sudah siap. mari kita melakukan percobaan mensubmit materi RPN.

### Menggunakan Akun Github kita di termux
kalian bisa install dulu tool github dengan perintah berikut
```bash
pkg install gh
```
Jika sudah selesai kalian lakukan autentikasi untuk menyambungkan akun kalian dahulu dengan perintah
```bash
gh auth login
```
Kalian enter enter saja sampai muncul one time code. untuk one time code nya kalian copy terlebih dahulu, lalu tekan enter untuk membuka linknya di browser.

![step-1](/assets/using-github/step-1.png)

Jika sudah mengikuti prosedur di browsernya dan muncul halaman seperti dibawah maka kalian berhasil mengkoneksikan gh local kalian, dengan begini kalian bisa menggunakan operasi git yang berhubungan dengan remote nanti.

![step-2](/assets/using-github/step-2.png)

Sesudah itu kalian harus set config username dan email untuk config git kalian, agar nanti hasil commit menunujuk ke akun kalian. bisa gunakan perintah dibawah ini

```bash
git config --global user.name <UsernameGithubKalian>
git config --global user.email <email@github.kalian>
```

### Fork Materi RPN
kita akan mencoba menfork materi rpn disini kalian ikuti tutorial ini terlebih dahulu sampai kalian mencopy hasil link fork kalian.

[![Tutor Daftar](https://img.youtube.com/vi/TCNAxlvnlfs/maxresdefault.jpg)](https://youtu.be/TCNAxlvnlfs)

Setelah kalian mendapat link fork nya kalian clone ke termux kalian dengan cara
```bash
git clone <url repository fork kalian>
```
atau menggunkan github cli
```bash
gh repo clone <UsernameKalian>/<NamaRepository>
```

lalu kalian ubah directory ke directory hasil clone tadi contoh kalian bisa menggunakan perintah `ls` untuk melihat foldernya. setelah itu buka nvim.
```bash
cd <nama folder/directory>
nvim
```

Buka terminal dengan `Spasi`+`t`+`h` lalu kalian buat new branch terlebih dahulu dengan perintah
```bash
git checkout branch -b <nama kalian>
```
setelah selesai tutup terminal dengan `Ctrl`+`d`. lalu kalian buka neo-tree dengan `Spasi`+`e`

![step-1](/assets/rpn-fork/step-1.png)

Pilih salah satu quiz yang ingin kalian kerjakan misal disini ingin mengerjakan quiz part1 soal1 maka kalian klik tombol `a` didalam neo-tree setelah itu masukan `soal1.js` setelah terbuat kalian enter, lalu tutup neo-tree kalian dengan tombol `Spasi`+`e` lagi.

![step-2](/assets/rpn-fork/step-2.png)
![step-3](/assets/rpn-fork/step-3.png)

Mode di Neovim :

- **Normal Mode** ditandai dengan indikator berwarna biru, kalian bisa memasuki mode ini menggunakan tombol `Esc`. Mode ini berguna untuk navigasi, dan memasukan vim command.

![step-1](/assets/mode-in-neovim/step-1.png)

- **Insert Mode** ditandai dengan indikator berwarna hijau. kalian bisa memasuki mode ini dengan mengetik `i` atau `a` di dalam Normal Mode. berguna jika kita ingin mengedit file yang sedang kita buka (buffer). Untuk keluar dari mode ini kalian bisa menggunakan tombol `Esc` untuk kembali ke Normal Mode.

![step-2](/assets/mode-in-neovim/step-2.png)

- **Visual Mode** ditandai dengan indikator berwarna ungu. Visual Mode sangat berguna ketika kita ingin menyeleksi lalu melakukan yank (copy), put (paste), dan delete. Kalian bisa memasuki mode ini dengan mengetik `v` atau `V` di dalam Normal Mode. Lalu untuk kembali ke Normal Mode kalian bisa menggunakan tombol `Esc`.

![step-3](/assets/mode-in-neovim/step-3.png)

Setelah kalian paham mode mode diatas cobalah untuk membuka file Readme.MD lalu masuk visual mode dan lakukan yank (copy) untuk soal1 saja, lalu masuk ke normal mode kembali lalu kembali ke soal1.js dan lakukan put (paste).

Setelah itu kalian coba kerjakan soal tersebut menggunakan insert mode. setelah selesai bukalah terminal dan test code kalian mengunakan perintah
```bash
node <nama file>.js
```

![step-4](/assets/rpn-fork/step-4.png)
![step-5](/assets/rpn-fork/step-5.png)
![step-6](/assets/rpn-fork/step-6.png)

Cobalah untuk membuat commit kalian. dengan perintah berikut
```bash
git add .
git commit -m "feat: Pengerjaan Part 1 Soal 1"
```
![step-7](/assets/rpn-fork/step-7.png)

Setelah itu cobalah mengetik `git push`. maka akan muncul peringatan, kalian ikuti saja perintah yang muncul dari peringatan tersebut untuk membuat branch di remote repository kalian sekaligus push hasil commit kalian. setelah selesai remote branch terbuat kalian hanya tingal mengetik `git push` saja

![step-8](/assets/rpn-fork/step-8.png)

Bukalah repository fork kalian di browser maka akan terlihat tombol untuk compare & pull request kalian klik saja itu.
![step-9](/assets/rpn-fork/step-9.png)

Pastikan untuk base repository berada pada repository asli. misalnya disini RPN-Phase-0/Week1-Welcome-To-Code dengan branch main. Dan ubah title dengan nama kalian
![step-10](/assets/rpn-fork/step-10.png)

Setelah itu klik create pull request
![step-11](/assets/rpn-fork/step-11.png)

Jika muncul pull request kalian di base repository. maka kalian berhasil mengerjakan soal dan mintalah helper untuk mereview hasil kerja kalian!.
![step-12](/assets/rpn-fork/step-12.png)
![step-13](/assets/rpn-fork/step-13.png)

## Instal Typescript Pack (Optional)
Typescript Pack berguna untuk code-completion, formatting, dan type lens pada proyek javascript kita. Ini sebenernya optional jadi kalian boleh skip saja untuk part ini

Pertama-tama buka nvim kalian, dan klik `Space`+`f`+`a`. Maka akan muncul dialog Telescope seperti dibawah. Kalian cari `./lua/community.lua` lalu enter.

![step-1](/assets/typescript-pack-instalation/step-1.png)

Lalu kalian comment terlebih dahulu baris paling atas dan masukan
```lua
{ import = "astrocommunity.pack.typescript" }
```
didalam scope return nya.
![step-2](/assets/typescript-pack-instalation/step-2.png)

Save dengan `Spasi`+`w`. lalu keluar terlebih dahulu, masuk nvim, dan tunggu proses hingga selesai.

![step-3](/assets/typescript-pack-instalation/step-3.png)
![step-4](/assets/typescript-pack-instalation/step-4.png)

Check didalam file javascript kalian. jika code completion atau warning muncul saat kalian mengetik sesuatu. selamat kalian berhasil menginstall typescript pack

![step-5](/assets/typescript-pack-instalation/step-5.png)