<a name="readme-top"></a>
<!-- ABOUT THE PROJECT -->
## Configure OPKG

![image](https://user-images.githubusercontent.com/40128651/222686284-b580b695-2dfd-4591-bbe5-4cbd19ac7678.png)

Custom OpenWRT opkg repository bisa langsung diinstall menggunakan perintah opkg. OpenWRT merupakan opensource dan dapat dimodifikasi dengan sebgaimana mestinya. untuk itu jika hanya menginstall di repository official OpenWRT Package seperti `v2ray, Passwall, Openclash, ssr plus` dan lain sebgainya belum ada di Official OpenWRT. sehingga tidak bisa langsung install menggunakan `opkg install`

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- GETTING STARTED -->
## Getting Started

Cukup Ganti link url di Configure OPKG di OpenWRT, semua package yang tidak ada di official akan bisa diinstall di OpenWRT.
  * `masuk ke Software`

  ![image](https://user-images.githubusercontent.com/40128651/222688039-f78d12ca-1fae-40fa-a4ca-b4d71d0cdd02.png)
---------------------------------------  
  * `kemudian klik di configure opkg`
    
  ![image](https://user-images.githubusercontent.com/40128651/222688322-39c362e1-2aca-485c-b96a-0c11bf423c16.png)
---------------------------------------  
  * `maka akan muncul tampilan seperti ini`
    
  ![image](https://user-images.githubusercontent.com/40128651/222688448-26c73801-954e-4a70-a01e-2efe3e861f21.png)
---------------------------------------


<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Edit

pada `/etc/opkg/customfeeds.conf`

![image](https://user-images.githubusercontent.com/40128651/222689992-1b56fe7f-8f5f-4e28-84e3-d8fbd178fca5.png)

1. Rubah dan masukan link berikut

* Custom OPKG Package
  ```sh
  # add your custom package feeds here
  #
  # src/gz example_feed_name http://www.example.com/path/to/files

  src/gz custom_generic https://raw.githubusercontent.com/lrdrdn/my-opkg-repo/main/generic
  src/gz custom_arch https://raw.githubusercontent.com/lrdrdn/my-opkg-repo/main/x86_64
  ```
  
2. Save, kemudian Update Lists

<p align="right">(<a href="#readme-top">back to top</a>)</p>

