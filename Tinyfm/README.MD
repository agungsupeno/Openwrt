# Install-Tinyfm
<a name="readme-top"></a>

  <p align="left">
    Kegunaan Tinyfm adalah untuk mengakses file Openwrt selain menggunakan WinSCP, Tinyfm juga memudahkan akses File Openwrt yang memiliki tampilan GUI memudahkan untuk mengola file layaknya File Explorer atau File Manager. Tinyfm merupakan sebuah program pengelola file yang berbasis web yang include dengan openwrt. Namun sebelum instalasi harus punya winSCP terlebih dahulu untuk memasukan beberapa file kedalam OpenWRT.
  </p>

</div>
<!-- USAGE EXAMPLES -->

_Download WinSCP [Download](https://winscp.net/eng/download.php)_


<p align="right">(<a href="#readme-top">back to top</a>)</p>

 
<!-- GETTING STARTED -->
## Getting Started

1. Buka Terminal di OpenWRT
2. Kemudian Update dan Install php8
    * **Update**
      ```sh
      opkg update
      ```
    * **Install php8**
      ```sh
      Opkg install php8-cgi php8-mod-session php8-mod-ctype php8-mod-fileinfo php8-mod-mbstring php8-mod-iconv zoneinfo-asia
      ```
 3. Buka **WinSCP** kemudian masuk ke `/etc/init.d/`
 4. Buke dengan File `uhttpd` masukan baris berikut kedalam `config uhttpd 'main'` Tambahkan di Baris terakhir
    * **Edit config uhttpd 'main'**
      ```sh
      list interpreter '.php=/usr/bin/php-cgi'
      option index_page 'index.html, index.php'
      option no_dirlists 1
      log 'true'
      ```
      ![image](https://user-images.githubusercontent.com/40128651/222652843-8bb355cc-46cd-457c-b04d-862d657b9c0b.png)
      
  5.  Masuk kembali ke Terminal untuk Restart OpenWRT kemudian ketikan
      * **Restart OpenWRT**
      ```sh
      /etc/init.d/uhttpd restart
      ``` 
   6. Buka **Winscp** kembali kemudian masukan Folder pendukung yang pertama `tinyfm` masukan ke `/www/`
   7. Jika sudah, kembali ke terminal. Kemduian ketikan perintah berikut.
      
      ```sh
      cd /wwww
      cd tinyfm/
      ln -s / rootfs
      ```
   8. Cek foldernya apakah sudah terbentuk dengan mengetikan perintah
   
      ```sh
      ls -l
      ```
   9. Balik kembali ke **WinSCP** kemudian buka `/www/tinyfm` edit dengan file editor pada file `index.php`
   10. Cari dan edit timezone di `line 59` pada `UTC` menjadi `Asia/Jakarta`
   11. Buka WinSCP kembali
   12. Kemudian pindahkan `tinyfm.lua` ke `Controller`
   13. Kemudian pindahkan `tinyfm.htm` ke `View`
   14. Kemudian Logout pada OpenWRT Login kembali
   15. Done


<p align="right">(<a href="#readme-top">back to top</a>)</p>
