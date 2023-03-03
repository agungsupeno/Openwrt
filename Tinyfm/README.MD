# Install-Tinyfm

<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]


1. Buka Terminal
-----------------------------------
      Opkg update
      Opkg install php8-cgi php8-mod-session php8-mod-ctype php8-mod-fileinfo php8-mod-mbstring php8-mod-iconv zoneinfo-asia
-----------------------------------
2. Buka via winscp
3. Masuk ke **/etc/init.d/** kemudian Buka _uhttpd_ masukan baris berikut kedalam config uhttpd 'main' (Tambahkan di baris terakhir)
-----------------------------------
      list interpreter '.php=/usr/bin/php-cgi'
      option index_page 'index.html, index.php'
      option no_dirlists 1    
      log 'true'
-----------------------------------
4. Masuk kembali ke terminal
-----------------------------------
      /etc/init.d/uhttpd restart
-----------------------------------
5. Buka Winscp kembali kemudian masukan Folder pendukung yang pertama "tinyfm" masukan ke /www/
6. Jika sudah memasukan file **Tinyfm** melalui Winscp. ketikan perintah berikut di terminal.
-----------------------------------
      cd /wwww
      cd tinyfm/
      ln -s / rootfs
 -----------------------------------
6. Cek folder nya apakah sudah terbentuk dengan mengetikan perintah
-----------------------------------
      ls -l
 -----------------------------------
8. Buka index.php di /www/tinyfm
9. Edit timezone di line 59 'UTC' menjadi 'Asia/Jakarta'
10. Masuk ke /usr/lib/lua/luci
11. Kemudian pindahkan _**'tinyfm.lua' ke "Controller"**_
12. Kemudian pindahkan _**'tinyfm.htm' ke "View"**_
13. Restart Routerboard.

