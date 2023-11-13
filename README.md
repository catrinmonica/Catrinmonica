# Catrin-Monica - 09011182126012
## Code Wordpress
# 1. Saat login ke ubuntu masukkan username dan password, lalu ketik ifconfig -a untuk mengecek IP
        ifconfig-a
 ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/afef49a9-a40a-4d51-b28e-4a3ee87ebb1f)

# 2. Login ke Ubuntu Server dengan menggunakan Putty SSH server, lalu masukan Host Name atau IP Address
 ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/5a5d9140-6c7e-4174-bc4a-b20c223170c8)

# 3. Setelah itu login ke putty dengan cara memasukkan username dan password
 ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/bfbd6521-2f2f-4306-a53b-8b70b981e838)

# 4. Jalankan perintah dibawah ini untuk menginstal server web Apache
        sudo apt update
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/6ac70fef-99e3-41e5-ba6b-71e78c0463c5)

        sudo apt install apache2
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/47a50410-62ad-4fea-b209-94a80df5d942)

# 5. Setelah instalasinya selesai, lalu aktifkan dan mulai Apache
        sudo systemctl start apache2
        sudo systemctl enable apache2
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/a630625f-4ced-4294-9962-f9a79e4f8495)

# 6. Instal PHP dan modul yang diperlukan untuk berjalan bersama Apache
        sudo apt install php libapache2-mod-php php-mysql
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/9cb020df-aa42-4c8b-a9bc-4e187ce44e7d)

        sudo systemctl restart apache2  
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/ce6047bc-7222-4015-aaa9-f6c324b0f7d8)

# 7. Instal Database Server (MySQL)
        sudo apt install mysql-server
  ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/f55f681e-7808-41b3-8b62-a2bbef68f68a)
  	
        sudo mysql_secure_installation
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/96bf71af-ca10-4287-a3f9-1d6abf139a3e)

# 8. Selanjutnya membuat Database dan Pengguna Database
        sudo mysql
 ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/25959875-ccf6-462b-b3d5-e9dba333d779)
## Buat	database baru dan pengguna database untuk WordPress. Ubah bagian `nama_database`, `nama_pengguna`, dan `password_pengguna`
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/85b80930-1832-43e7-9dfb-f379fc672854)

# 9. Instal WordPress:
## Dwonload lalu ekstrak arsip WordPress ke dalam direktori web root. Dan ubahlah `nama_folder` dengan nama folder yang diinginkan:

         cd /var/www/html
         sudo wget https://wordpress.org/latest.tar.gz
 ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/1c9038be-5674-40f9-b11d-4c3e443d15d3)
 
          sudo tar -xzvf latest.tar.gz
          sudo mv wordpress nama_folder
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/b68221ec-34e8-4f0d-95e7-430bd84679f6)

# 10. Konfigurasi pada WordPress
## Membuat salinan file konfigurasi pada WordPress dan edit file `wp-config.php
        sudo cp /var/www/html/nama_folder/wp-config-sample.php /var/www/html/nama_folder/wp-config.php
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/d12874c0-153e-414f-9cc5-381c1b5af865)

# 11. Atur Izin Akses
## Pastikan Apache memiliki hak akses yang tepat ke folder WordPress.
        sudo chown –R www-data:www-data /var/www/html/nama_folder
        /var/www/htmls
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/0efb0a45-a00c-45c4-ac7d-3db02afcb77e)
## Isi konfigurasi pada server web:
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/e54131b0-2327-4c0c-b257-abb60d3d34fa)
 
# 12. Aktifkan Konfigurasi dan Restart Apache
## Aktifkan konfigurasi situs, lakukan restart pada Apache, serta cek status keaktifan Apache2
        sudo nano /etc/apache2/sites-available/nama_domain.conf
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/0a14cad2-cc7a-46a9-b391-2ff3fc1eea21)

        sudo a2ensite nama_domain.conf
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/4cbc177b-95e7-4b6c-ab5d-2d5c3bb05116)

        sudo systemctl restart apache2
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/de8ab79d-d5ea-4181-b28a-fec8a41ac1e0)

# 13. Kemudian ke laman web dan ketik sesuai dengan domain
        “http://192.168.181.137/wp-admin/install.php” 
 ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/f4a8f03c-7eb9-40df-bbbe-5ed0407c6868)
 ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/8d618570-92eb-4beb-a169-1e17915a12e8)

## Selanjutnya masukkan judul situs, email, dan password. Setelah selesai coba login dengan menggunakan nama pengguna/email dan password yang telah diatur sebelumnya sehingga akan muncul tampilan berikut
 ![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/dad36562-c48b-474a-ae74-7228d6644568)

#  Tampilan Homepage untuk Admin Server
![image](https://github.com/catrinmonica/Catrinmonica/assets/150575002/787811da-49e0-41e9-ab06-3bb7aa0b0bfc)

