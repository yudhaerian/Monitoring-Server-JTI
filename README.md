# MANUAL PENGGUNAAN MONITORING SERVER JTI POLINEMA

Sistem Monitoring Server JTI di Politeknik Negeri Malang menggunakan [Prometheus](https://prometheus.io/) sebagai sumber data dan [Grafana](http://grafana.org/) untuk visualisasi.
## OpenVPN
- Pertama-tama, pastikan PC sudah terhubung ke jaringan Wi-Fi "JTI-POLINEMA".

![wifi](screens/wifi.png)

- Buka OpenVPN.

![openvpn](screens/ov1.png)

- Unggah file konfigurasi "monsev", lalu tambahkan username, password, dan Secretkey berikut: 
``` bash
Username : mts
Password : yudha
Secretkey: jtifast!
``` 
![openvpn](screens/ov2.png)

- Klik tombol Connect. Setelah langkah-langkah berhasil, akan muncul tampilan berikut:

![openvpn](screens/ov3.png)
![openvpn](screens/ov4.png)

- Setelah terhubung ke OpenVPN, buka CMD dan tambahkan kode berikut:
``` bash
route ADD 10.0.0.32 MASK 255.255.255.240 10.0.0.49
```
![openvpn](screens/route.png)

- Setelah semuanya berhasil, coba uji ping ke IP server.

![openvpn](screens/ping.png)


## GRAFANA

- Untuk mengakses Grafana pada http://10.0.0.34:3000, halaman login akan muncul seperti berikut:
![grafana](screens/login.png)

- Masuk dengan akun Grafana default:
``` bash
Username : admin
Password : admin
```
- Setelah berhasil masuk, Anda akan diarahkan ke halaman utama. 
![grafana](screens/home.png)

- Pada halaman utama Grafana, pilih "SISTEM PEMANTAUAN SERVER JTI" dalam menu Dashboard, dan tampilan akan muncul seperti berikut: 
- All Panel Gauge CPU, Ram dan Disk
![grafana](screens/allcpu.png)
- All Ram
![grafana](screens/allram.png)
- All Disk
![grafana](screens/alldisk.png)

- Pada halaman utama Sistem Pemantauan Server JTI, terdapat label Filter Alamat IP.

![grafana](screens/filter.png)

Di dalam label ini terdapat daftar server yang dimonitor sehingga Anda dapat menampilkan hanya satu server. Sebagai contoh, mari pilih IP Server: 10.0.0.34.
- Filter Panel Grafik CPU, Ram dan Disk
![grafana](screens/filtercpu.png)
- Filter CPU 
![grafana](screens/filtercpuu.png)
- Filter Ram 
![grafana](screens/filterram.png)
- Filter Disk 
![grafana](screens/filterdisk.png)

- Selain itu, pada halaman Dashboard terdapat fitur Refresh Dashboard yang memungkinkan Anda untuk secara otomatis memperbarui dashboard mulai dari setiap detik hingga setiap hari.
![grafana](screens/refresh.png)