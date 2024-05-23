# Tugas Praktikum { Pertemuan ke 11 } <img src=https://logos-download.com/wp-content/uploads/2016/05/MySQL_logo_logotype.png width="130px" >


|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|Oktavia Rizkha Kurniawati|312310509|TI.23.A.5|Basis Data|

# Soal Latihan Praktikum ( Pegawai )

![image](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/84f613df-e4c9-4612-a9e6-a9cebc5baaeb)



**Perintah SQL :**

```
CREATE TABLE pegawai (
    idpegawai VARCHAR(5) PRIMARY KEY,
    nama_depan VARCHAR(10) NOT NULL,
    nama_belakang VARCHAR(15) NOT NULL,
    email VARCHAR(25) UNIQUE KEY,
    telepon VARCHAR(15),
    tgl_kontrak DATA,
    id_job VARCHAR(5),
    gaji INT,
    tunjangan INT
    );

INSERT INTO pegawai VALUES
    ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
```

***Output :***

![alt text]![Screenshot 2024-05-20 134009](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/add99746-c7d1-49bd-a980-11e6a12a2b54)



## Tugas Praktikum

**1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000 !**

```
SELECT*FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
```

***Output :***

![Screenshot 2024-05-20 134110](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/dca24173-1576-421e-9f10-629aec79492d)

Pernyataan ini menampilkan semua kolom dari tabel pegawai untuk pegawai yang gajinya tidak sama dengan 2.000.000 dan 1.250.000. Kondisi NOT IN (2000000, 1250000) memastikan bahwa hanya pegawai dengan gaji selain kedua nilai tersebut yang ditampilkan.


**2. Tampilkan pegawai yang tunjangannya NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NULL;
```

***Output :***

![Screenshot 2024-05-20 134155](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/e72b0fea-9ba1-49b8-98bf-9008a1870329)

Pernyataan ini menampilkan semua kolom dari tabel pegawai untuk pegawai yang tidak memiliki tunjangan. Kondisi tunjangan IS NULL digunakan untuk memeriksa nilai NULL dalam kolom tunjangan.


**3. Tampilkan pegawai yang tunjangannya tidak NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NOT NULL;
```

***Output :***

![Screenshot 2024-05-20 134331](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/b3ba1f71-555b-400d-b4a1-ed131185ca00)

Pernyataan ini menampilkan semua kolom dari tabel pegawai untuk pegawai yang memiliki tunjangan. Kondisi tunjangan IS NOT NULL digunakan untuk memeriksa nilai yang bukan NULL dalam kolom tunjangan.



**4. Tampilkan/hitung jumlah baris/record tabel pegawai!**

```
SELECT COUNT(*) AS jmlh_pegawai FROM pegawai;
```

***Output :***

![Screenshot 2024-05-20 134417](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/e871dd92-fd10-4452-a7a2-38d29839033b)

Pernyataan ini menghitung jumlah total baris atau record dalam tabel pegawai. Fungsi COUNT(*) mengembalikan jumlah total baris yang ada, dan hasilnya diberi alias jumlah_pegawai.


**5. Tampilkan/hitung jumlah total gaji di tabel pegawai!**

```
SELECT SUM(gaji) AS ttl_gaji FROM pegawai;
```

***Output :***

![Screenshot 2024-05-20 134453](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/0f604be8-60ce-43c1-8315-1e8e458eda67)

Pernyataan ini menghitung jumlah total gaji dari semua pegawai dalam tabel pegawai. Fungsi SUM(gaji) menjumlahkan nilai dalam kolom gaji untuk setiap baris, dan hasilnya diberi alias total_gaji.


**6. Tampilkan/hitung rata-rata gaji pegawai!**

```
SELECT AVG(gaji) AS mean_gaji FROM pegawai;
```

***Output :***

![Screenshot 2024-05-20 134536](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/99a4a7f8-0855-4cd6-a0bc-c3e0fd3df607)

Pernyataan ini menghitung rata-rata gaji dari semua pegawai dalam tabel pegawai. Fungsi AVG(gaji) mengembalikan nilai rata-rata dari kolom gaji, dan hasilnya diberi alias rata_rata_gaji.


**7. Tampilkan gaji terkecil!**

```
SELECT MIN(gaji) AS terkecil FROM pegawai;
```

***Output :***

![Screenshot 2024-05-20 134607](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/347fa29f-2252-45ae-b926-f7d19e46814c)

Pernyataan ini menampilkan gaji terkecil di antara semua pegawai dalam tabel pegawai. Fungsi MIN(gaji) mengembalikan nilai terkecil dari kolom gaji, dan hasilnya diberi alias gaji_terkecil.


**8. Tampilkan gaji terbesar!**

```
SELECT MAX(gaji) AS terbesar FROM pegawai;
```

***Output :***

![Screenshot 2024-05-20 134633](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/833a2657-2529-4069-85b4-f48040e6d904)

Pernyataan ini menampilkan gaji terbesar di antara semua pegawai dalam tabel pegawai. Fungsi MAX(gaji) mengembalikan nilai terbesar dari kolom gaji, dan hasilnya diberi alias gaji_terbesar.


# Soal Latihan Praktikum ( Hewan )

![Screenshot 2024-05-20 135743](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/aac1ed58-5970-44bd-be41-3b22da41d181)



**Perintah SQL :**

```
CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );

INSERT INTO hewan VALUES
    ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
    ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
    ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
    ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
    ('p5', 'Fang', 'Benny', 'Dog', 'M'),
    ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
    ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
    ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
    ('p9', 'Slim', 'Benny', 'Snake', 'M');
```

***Output :***

![Screenshot 2024-05-20 134743](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/7cdcf8d7-27fb-4474-a1b5-1bbd8cf4c5bb)



## Tugas Praktikum

**1. Tampilkan jumlah hewan yang dimiliki setiap owner.**

```
SELECT owner, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY owner;
```

***Output :***

![Screenshot 2024-05-20 134811](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/7da04580-a791-49be-9378-c234b92ca9ac)

Pernyataan ini menghitung jumlah hewan yang dimiliki oleh setiap pemilik (owner). Fungsi COUNT(*) menghitung jumlah hewan, dan hasilnya dikelompokkan berdasarkan kolom owner dengan menggunakan GROUP BY.


**2. Tampilkan jumlah hewan berdasarkan spesies**

```
SELECT species, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY species;
```

***Output :***

![Screenshot 2024-05-20 134835](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/dce7ef1b-b64d-4b5d-9efe-71b6444272db)

Pernyataan ini menghitung jumlah hewan berdasarkan spesies (species). Fungsi COUNT(*) menghitung jumlah hewan, dan hasilnya dikelompokkan berdasarkan kolom species dengan menggunakan GROUP BY.


**3. Tampilkan jumlah hewan berdasarkan jenis kelamin**

```
SELECT sex, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY sex;
```

***Output :***

![Screenshot 2024-05-20 134900](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/fcf2991b-e5e6-4aa4-a166-040d60b91e87)

Pernyataan ini menghitung jumlah hewan berdasarkan jenis kelamin (sex). Fungsi COUNT(*) menghitung jumlah hewan, dan hasilnya dikelompokkan berdasarkan kolom sex dengan menggunakan GROUP BY.


**4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
```

***Output :***

![Screenshot 2024-05-20 135017](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/c22cdac4-1ba4-4371-be44-bbee37c2235f)

Pernyataan ini menghitung jumlah hewan berdasarkan kombinasi spesies (species) dan jenis kelamin (sex). Fungsi COUNT(*) menghitung jumlah hewan, dan hasilnya dikelompokkan berdasarkan kombinasi kolom species dan sex dengan menggunakan GROUP BY.


**5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE
species IN ('Cat', 'Dog')
GROUP BY species, sex;
```

***Output :***

![Screenshot 2024-05-20 135226](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/2f5c2144-5113-4564-ab65-bfdd03814aae)

Pernyataan ini menghitung jumlah hewan berdasarkan spesies (species) yang hanya berupa 'cat' dan 'dog', dan jenis kelamin (sex). Kondisi WHERE species IN ('cat', 'dog') memfilter data hanya untuk spesies 'cat' dan 'dog', dan hasilnya dikelompokkan berdasarkan kombinasi kolom species dan sex dengan menggunakan GROUP BY.


**6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja**

```
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

***Output :***

![Screenshot 2024-05-20 135250](https://github.com/oktavia18/tugas-praktikum4/assets/147913672/5aebf95c-388e-4255-bf84-ab0a527069a1)

Pernyataan ini menghitung jumlah hewan berdasarkan jenis kelamin (sex) yang diketahui saja, yaitu yang kolom sex-nya tidak bernilai NULL. Kondisi WHERE sex IS NOT NULL memfilter data hanya untuk jenis kelamin yang diketahui, dan hasilnya dikelompokkan berdasarkan kolom sex dengan menggunakan GROUP BY.


## Tulis semua perintah-perintah SQL percobaan di atas beserta outputnya!

```
CREATE DATABASE praktikum4;
USE praktikum4;
CREATE TABLE pegawai (
    idpegawai VARCHAR (5) PRIMARY KEY,
    nama_depan VARCHAR (10) NOT NULL,
    nama_belakang VARCHAR (15) NOT NULL,
    email VARCHAR (25) UNIQUE KEY,
    telepon VARCHAR (15),
    tgl_kontrak DATE,
    id_job VARCHAR (5),
    gaji INT,
    tunjangan INT
    );

INSERT INTO pegawai VALUES
    ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);

SELECT * FROM pegawai;

SELECT * FROM pegawai WHERE gaji NOT IN (2000000, 1250000);

SELECT * FROM pegawai WHERE tunjangan IS NULL;

SELECT * FROM pegawai WHERE tunjangan IS NOT NULL;

SELECT COUNT(*) AS jumlah_pegawai FROM pegawai;

SELECT SUM(gaji) AS total_gaji FROM pegawai;

SELECT AVG(gaji) AS rata_rata_gaji FROM pegawai;

SELECT MIN(gaji) AS gaji_terkecil FROM pegawai;

SELECT MAX(gaji) AS gaji_terbesar FROM pegawai;

CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );

INSERT INTO hewan (id, name, owner, species, sex)
VALUES ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
       ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
       ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
       ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
       ('p5', 'Fang', 'Benny', 'Dog', 'M'),
       ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
       ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
       ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
       ('p9', 'Slim', 'Benny', 'Snake', 'M');

SELECT * from hewan;

SELECT owner, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY owner;

SELECT species, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species;

SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY sex;

SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;

SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE species IN ('Cat', 'Dog') GROUP BY species, sex;

SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

## Berikan Kesimpulan Anda !

Terdapat beberapa ***Query Filter*** yang ditemukan pada tugas praktikum 4 :

- Operator `IN` digunakan untuk memfilter data yang terdapat pada list IN
- Operator `NOT IN` digunakan untuk memfilter data yang tidak terdapat pada list IN
- Operator `IS NULL` digunakan untuk menampilkan data dengan nilai data NULL
- Operator `IS NOT NULL` digunakan untuk menampilkan data dengan nilai data tidak NULL
- `COUNT` adalah perintah yang digunakan untuk menghitung jumlah baris suatu kolom pada tabel.
- `SUM` adalah perintah yang digunakan untuk menghitung jumlah nilai suatu kolom pada tabel.
- `AVG` adalah perintah yang digunakan untuk menghitung rata-rata dari nilai suatu kolom pada tabel.
- `MIN` adalah perintah yang digunakan untuk menampilkan nilai terkecil dari suatu kolom pada tabel.
- `MAX` adalah perintah yang digunakan untuk menampilkan nilai terbesar dari suatu kolom pada tabel.
- Klausa `GROUP BY` berfungsi untuk mengelompokkan data berdasarkan field tertentu.

## FINISH <img align="center" alt="Ikhsan-Python" height="40" width="45" src="https://em-content.zobj.net/source/microsoft-teams/337/student_1f9d1-200d-1f393.png"> <img align="center" alt="Ikhsan-Python" height="40" width="45" src="https://em-content.zobj.net/thumbs/160/twitter/348/flag-indonesia_1f1ee-1f1e9.png">kombinasi spesies dan jenis kelamin tertentu.
#### - Jumlah hewan berdasarkan jenis kelamin yang diketahui: Dengan menggunakan klausa WHERE untuk memfilter jenis kelamin yang tidak NULL (diketahui) dan klausa GROUP BY pada kolom "sex" serta fungsi COUNT, kita dapat menghitung jumlah hewan untuk jenis kelamin yang diketahui.
#### Dengan menggunakan query-query ini, kita dapat memperoleh informasi statistik tentang jumlah hewan berdasarkan kriteria yang relevan dalam basis data MySQL.
