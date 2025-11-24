# PROJECK_SISTEMOPRASI_KHANZA
# MANAJEMEN FILE SERVER

# LANGKAH 1 BUAT STRUKTRUR DIREKTORI
berikut cara membuat struktur direktori Project_manajemen_file_server:
[Deskripsi gambar] : ( https://drive.google.com/file/d/1QRf0l3XqfI1_XGMyh0kwoDMTrF7UjgQP/view?usp=drivesdk )

~~~~
mkdir project_manajemen_file_server
cd project_manajemen_file_server
mkdir -p marketing/documents marketing/archives
mkdir -p engineering/documents marketing/archives
ls
~~~~
penjelasan :
mkdir = membuat direktori baru
cd = masuk ke folder atau direktori
ls = menampilkan 

# LANGKAH 2 PINDAHKAN DAN SALIN FILE
memindahkan file yanf salah tempat ke direktori uang benar, dan buat backup di folder archives
[Deskripsi gambar] : ( https://drive.google.com/file/d/14FQ5V1d2n8hrYT8Hg2D2ikMw3z9Hx_qN/view?usp=drivesdk )

~~~~
mv /home/khanzak/project_manajemen_file/documents/file{1..10}.txt /home/khanzak/project_manajemen_file_server/marketing/documents
cp -R /home/khanzak/project_manajemen_file/documents/ /home/khanzak/project_manajemen_file_server/marketing/documents
~~~~
penjelasan : 
mv = memindahkan file atau folder
cp = menyalin file
-R = seluruh data atau file

# LANGKAH 3  ATUR PERMISSION
set permission yang tepat agar hanya departemen terkait yang bisa mengakses folder
[Deskripsi gambar] : ( https://drive.google.com/file/d/1zg8ByICicDpoO86aZFgTs6bx0SgJ0CGa/view?usp=drivesdk )

~~~~
sudo adduser admin_marketing
sudo chown -R admin_marketing /home/khanzak/project_manajemen_file_server/marketing
sudo chmod -R 700 /home/khanzak/project_manajemen_file_server/marketing

sudo adduser admin_engineering
sudo chown -R admin_engineering /home/khanzak/project_manajemen_file_server/engineering
sudo chmod -R 700 /home/khanzak/project_manajemen_file_server/engineering

sudo adduser hr
sudo chown -R admin_hr /home/khanzak/project_manajemen_file_server/hr
sudo chmod -R 700 /home/khanzak/project_manajemen_file_server/hr

su admin_marketing
cd marketing
ls
exit exit

su admin_engineering
cd engineering
ls
exit exit

su admin_hr
cd hr
ls
exit exit
~~~~
penjelasan
sudo adduser = menambahkan user
sudo chown -R = mengubah kepemilikan sebuah folder dan isinya
sudo chmod -R 700 = mengatur izin akses folder dan semua isinya
su = subtitute user(mencoba masuk ke user)
ls = menampilkan
exit = keluar

# LANGKAH KE 4 CARI DAN FILTER
temukan semua file pdf yang di buat minggu lalu dan buat daftar lengkapnya
[Deskripsi gambar] : ( https://drive.google.com/file/d/1zuyziA0Lh1GsZrK3zDyGZ0FyekFqgmgK/view?usp=drivesdk )

~~~~
find /home/khanzak/project_manajemen_file -type f -name "*.pdf" > daftar_pdf.txt
ls
cat daftar_pdf.txt
~~~~
penjelasan : 
find = mencari
-type file = mencari file
-name "*.pdf" = file yang eksistensi nya pdf
ls = menampilkan
cat = menampikan isi file
