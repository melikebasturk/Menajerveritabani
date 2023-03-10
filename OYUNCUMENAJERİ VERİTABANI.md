# OYUNCUMENAJERİ VERİTABANI

*Oyuncuların kişisel bilgilerini, adlığı ödülleri, oynadığı dizi film gibi projeleri ve aylık menajere verdiği ücreti gibi verileri tutan bir Oyuncu menajeri için bir veritabanı oluşturuyoruz.*

*Bu veritabanı içine tabloları oluşturup verilerini ekliyoruz. Tabloları oluşturken Birincil Anahtar ve Yabancıl Anahtarları belirtiyoruz. Tablo oluştururken bir de dikkat ettiğimiz nokta boş geçilmemesi gereken alanları belirtmek.*

------

**Bu veritabanı kurgudur oluşturulan veriler de hiçbir yerden alınmamış olup tamamen kurmaca üzerine yapılmıştır.**

------

###### VERİTABANI KOMUTU

```sql
CREATE DATABASE OYUNCUMENAJERI
```

###### TABLO OLUŞTURMA VE VERİ GİRME KOMUTLARI

*İLETİŞİM TABLOSU VE VERİ GİRME*

```sql
CREATE TABLE ILETISIM( 
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY, 
TELEFON CHAR(10)  NOT NULL, 
MAIL VARCHAR(25)  NOT NULL,
INSTAGRAM VARCHAR(20),
TWITTER VARCHAR(20))
INSERT INTO ILETISIM (TELEFON,MAIL,INSTAGRAM,TWITTER) VALUES ('5553852463','oguzhan@deneme.com','oguzhan05','oguzhan05')
INSERT INTO ILETISIM (TELEFON,MAIL,INSTAGRAM,TWITTER) VALUES ('5375169149','aylin@deneme.com','26aylin','26aylin')
INSERT INTO ILETISIM (TELEFON,MAIL,INSTAGRAM,TWITTER) VALUES ('5349106933','tugba@deneme.com','tugba0','tugba0')
INSERT INTO ILETISIM (TELEFON,MAIL,INSTAGRAM,TWITTER) VALUES ('5439894233','eray@deneme.com','eray56','eray56')
INSERT INTO ILETISIM (TELEFON,MAIL,INSTAGRAM,TWITTER) VALUES ('5349377724','buglem@deneme.com','buglem89','buglem89')
INSERT INTO ILETISIM (TELEFON,MAIL,INSTAGRAM,TWITTER) VALUES ('5348242021','tuna@deneme.com','tuna65','tuna65')
INSERT INTO ILETISIM (TELEFON,MAIL,INSTAGRAM,TWITTER) VALUES ('5547592883','onur@deneme.com','onurrr5','onurr5')
```

*EĞİTİM TABLOSU VE VERİ GİRME*

```sql
CREATE TABLE EGITIM(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
OKULADI VARCHAR(60)  NOT NULL,
BOLUMADI VARCHAR(60) NOT NULL,
MEZUNYILI INT NOT NULL)
INSERT INTO EGITIM (OKULADI,BOLUMADI,MEZUNYILI) VALUES ('Anadolu Üniversitesi Devlet Konservatuarı','Sahne Sanatları Bölümü Oyunculuk Ana Sanat Dalı','2018')
INSERT INTO EGITIM (OKULADI,BOLUMADI,MEZUNYILI) VALUES ('İstanbul Üniversitesi Devlet Konservatuarı','Sahne Sanatları Bölümü Tiyatro Ana Sanat Dalı','2017')
INSERT INTO EGITIM (OKULADI,BOLUMADI,MEZUNYILI) VALUES ('Beykent Üniversitesi','Güzel Sanatlar Fakültesi Oyunculuk Bölümü','2021')
INSERT INTO EGITIM (OKULADI,BOLUMADI,MEZUNYILI) VALUES ('Mimar Sinan Güzel Sanatlar Anadolu Lisesi','Tiyatro Bölümü','2019')
INSERT INTO EGITIM (OKULADI,BOLUMADI,MEZUNYILI) VALUES ('Anadolu Üniversitesi Devlet Konservatuarı','Sahne Sanatları Bölümü Oyunculuk Ana Sanat Dalı','2020')
INSERT INTO EGITIM (OKULADI,BOLUMADI,MEZUNYILI) VALUES ('Beykent Üniversitesi','Güzel Sanatlar Fakültesi Oyunculuk Bölümü','2020')
```

*TAKIM TABLOSU VE VERİ GİRME*

```sql
CREATE TABLE TAKIM(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
REKLAMSORUMLUSU VARCHAR(50),
HUKUKSORUMLUSU VARCHAR(50) NOT NULL,
BASINDANISMANI VARCHAR(50))
INSERT INTO TAKIM (REKLAMSORUMLUSU,HUKUKSORUMLUSU,BASINDANISMANI) VALUES ('Yaşar SAVURGAN','Nazlı ÖRNEK','Birsen AKKOR')
INSERT INTO TAKIM (REKLAMSORUMLUSU,HUKUKSORUMLUSU,BASINDANISMANI) VALUES ('Necdet ERÇAM','Irmak HAMİDİ','Muhammed Ali ABDULLAH')
INSERT INTO TAKIM (REKLAMSORUMLUSU,HUKUKSORUMLUSU,BASINDANISMANI) VALUES ('Ömer Faruk KOCANOĞLU','Irmak HAMİDİ','Elif ÖZÇELİKBAŞ')
INSERT INTO TAKIM (REKLAMSORUMLUSU,HUKUKSORUMLUSU,BASINDANISMANI) VALUES ('Mira TÜTER','Ada VAPUR','Can DOLAR')
INSERT INTO TAKIM (REKLAMSORUMLUSU,HUKUKSORUMLUSU,BASINDANISMANI) VALUES ('Mira TÜTER','İsa BÖLÜK','Muhammed Ali ABDULLAH')
```

*TİYATRO TABLOSU VE VERİ GİRME*

```sql
CREATE TABLE TIYATRO(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
TIYATROADI VARCHAR(50) NOT NULL,
YIL INT NOT NULL)
INSERT INTO TIYATRO (TIYATROADI,YIL) VALUES ('Aldatanlar Kulübü','2023')
INSERT INTO TIYATRO (TIYATROADI,YIL) VALUES ('Gelecek Kaygısı','2022')
INSERT INTO TIYATRO (TIYATROADI,YIL) VALUES ('Sosyal Medya','2023')
```

*FILM TABLOSU VE VERİ GİRME*

```sql
CREATE TABLE FILM(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
FILMADI VARCHAR(50) NOT NULL,
YIL INT NOT NULL)
INSERT INTO FILM (FILMADI,YIL) VALUES ('Cadı Okulu','2023')
INSERT INTO FILM (FILMADI,YIL) VALUES ('Katil','2021')
INSERT INTO FILM (FILMADI,YIL) VALUES ('Sticker Avcısı','2022')
INSERT INTO FILM (FILMADI,YIL) VALUES ('Yazdığım Şiirdin','2023')
INSERT INTO FILM (FILMADI,YIL) VALUES ('Uyumayanlar','2023')
```

*DİZİTABLOSU VE VERİ GİRME*

```sql
CREATE TABLE DIZI(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
DIZIADI VARCHAR(50) NOT NULL,
YIL VARCHAR(10) NOT NULL,
BOLUMSAYISI INT NOT NULL)
INSERT INTO DIZI (DIZIADI,YIL,BOLUMSAYISI) VALUES ('Marjinal Gün','2021','25')
INSERT INTO DIZI (DIZIADI,YIL,BOLUMSAYISI) VALUES ('Aldatmak da suç','2022','3')
INSERT INTO DIZI (DIZIADI,YIL,BOLUMSAYISI) VALUES ('Kusursuz Katil','2021-2022','32')
INSERT INTO DIZI (DIZIADI,YIL,BOLUMSAYISI) VALUES ('Masalımın Gargameli','2020','15')
INSERT INTO DIZI (DIZIADI,YIL,BOLUMSAYISI) VALUES ('Güzeliğin Kusuru','2019-2021','60')
```

*ÖDÜLTABLOSU VE VERİ GİRME*

```sql
CREATE TABLE ODUL(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
ODULADI VARCHAR(100) NOT NULL,
YIL INT NOT NULL)
INSERT INTO ODUL (ODULADI,YIL) VALUES ('Pink Kelebek En İyi Kadın Oyuncu','2021')
INSERT INTO ODUL (ODULADI,YIL) VALUES ('Pink Kelebek En İyi Erkek Oyuncu','2021')
INSERT INTO ODUL (ODULADI,YIL) VALUES ('4. Uluslararası Film Festivali En İyi Film Kadın Oyuncu','2022')
INSERT INTO ODUL (ODULADI,YIL) VALUES ('4. Uluslararası Film Festivali En İyi Film Erkek Oyuncu','2022')
INSERT INTO ODUL (ODULADI,YIL) VALUES ('Pink Kelebek En İyi Kadın Oyuncu','2022')
INSERT INTO ODUL (ODULADI,YIL) VALUES ('Pink Kelebek En İyi Erkek Oyuncu','2022')
```

*PROGRAM TABLOSU VE VERİ GİRME*

```sql
CREATE TABLE PROGRAM(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
PROGRAMADI VARCHAR(40) NOT NULL,
YIL VARCHAR(15) NOT NULL)
INSERT INTO PROGRAM (PROGRAMADI,YIL) VALUES ('Sabahın Körü','2019-günümüz')
INSERT INTO PROGRAM (PROGRAMADI,YIL) VALUES ('Dedikodunun Peşinde','2017-günümüz')
INSERT INTO PROGRAM (PROGRAMADI,YIL) VALUES ('Sağlıklı Yaşam','2022-günümüz')
INSERT INTO PROGRAM (PROGRAMADI,YIL) VALUES ('Gençlerin Sesi','2020-günümüz')
INSERT INTO PROGRAM (PROGRAMADI,YIL) VALUES ('Z Kuşağı','2020-2021')
```

*REKLAM TABLOSU VE VERİ GİRME*

```sql
CREATE TABLE REKLAM(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
MARKA VARCHAR(15) NOT NULL)
INSERT INTO REKLAM (MARKA) VALUES ('Demo')
INSERT INTO REKLAM (MARKA) VALUES ('ASN')
INSERT INTO REKLAM (MARKA) VALUES ('Pink')
INSERT INTO REKLAM (MARKA) VALUES ('Turkcell')
INSERT INTO REKLAM (MARKA) VALUES ('Labne')
```

*OYUNCULAR TABLOSU VE VERİ GİRME*

```sql
CREATE TABLE OYUNCULAR(
ID INT IDENTITY(1,1)  NOT NULL PRIMARY KEY,
AD VARCHAR(50) NOT NULL,
SOYAD VARCHAR(10) NOT NULL,
CINSIYET VARCHAR(1) NOT NULL,
DOGUMGUNU DATE NOT NULL,
ACIKADRES VARCHAR(250) NOT NULL,
ILETISIMID INT FOREIGN KEY REFERENCES ILETISIM(ID) NOT NULL,
EGITIMID INT FOREIGN KEY REFERENCES EGITIM(ID),
TAKIMID INT FOREIGN KEY REFERENCES TAKIM(ID) NOT NULL,
FILMID INT FOREIGN KEY REFERENCES FILM(ID),
TIYATROID INT FOREIGN KEY REFERENCES TIYATRO(ID),
DIZIID INT FOREIGN KEY REFERENCES DIZI(ID),
PROGRAMID INT FOREIGN KEY REFERENCES PROGRAM(ID),
ODULID INT FOREIGN KEY REFERENCES ODUL(ID),
REKLAMID INT FOREIGN KEY REFERENCES REKLAM(ID),
ALINANUCRET MONEY NOT NULL)
INSERT INTO OYUNCULAR (AD,SOYAD,CINSIYET,DOGUMGUNU,ACIKADRES,ILETISIMID,EGITIMID,TAKIMID,FILMID,TIYATROID,DIZIID,PROGRAMID,ODULID,REKLAMID,ALINANUCRET) 
VALUES ('Oğuzhan','UZUNKAYA','E','1993.01.21','İHSANİYE MERKEZ MAH.4375.. SOKAK NO:607 100231 GÖLCÜK/KOCAELİ','1','2','5','2',NULL,'2','1',NULL,NULL,'20640')
INSERT INTO OYUNCULAR (AD,SOYAD,CINSIYET,DOGUMGUNU,ACIKADRES,ILETISIMID,EGITIMID,TAKIMID,FILMID,TIYATROID,DIZIID,PROGRAMID,ODULID,REKLAMID,ALINANUCRET) 
VALUES ('Aylin','TAŞHAN','K','1999.10.19','ATAMER MAH.2581. SOKAK NO:529 96650 KONAK/İZMİR','2','5','1','1','2',NULL,NULL,NULL,'5','20640')
INSERT INTO OYUNCULAR (AD,SOYAD,CINSIYET,DOGUMGUNU,ACIKADRES,ILETISIMID,EGITIMID,TAKIMID,FILMID,TIYATROID,DIZIID,PROGRAMID,ODULID,REKLAMID,ALINANUCRET) 
VALUES ('Tuğba','UZUNBAYIR','K','2000.10.19','FATIH MAH.PLEVNE CADDESİ SOKAK NO:563 119342 SANCAKTEPE/İSTANBUL','3','6','4','3','1','5',NULL,'1','1','20640')
INSERT INTO OYUNCULAR (AD,SOYAD,CINSIYET,DOGUMGUNU,ACIKADRES,ILETISIMID,EGITIMID,TAKIMID,FILMID,TIYATROID,DIZIID,PROGRAMID,ODULID,REKLAMID,ALINANUCRET) 
VALUES ('Eray','BOZNA','E','1999.05.19','SÜMER MAH.440. SOKAK NO:506 96717 KONAK/İZMİR','4','5','3','4',NULL,'2',NULL,'6',NULL,'20640')
INSERT INTO OYUNCULAR (AD,SOYAD,CINSIYET,DOGUMGUNU,ACIKADRES,ILETISIMID,EGITIMID,TAKIMID,FILMID,TIYATROID,DIZIID,PROGRAMID,ODULID,REKLAMID,ALINANUCRET) 
VALUES ('Buğlem','ÖZDEK','K','2001.05.19','SEVGİ MAH.87. SOKAK NO:377 96596 GAZİEMİR/İZMİR','5','3','2','2','1','3','5','5','2','20640')
INSERT INTO OYUNCULAR (AD,SOYAD,CINSIYET,DOGUMGUNU,ACIKADRES,ILETISIMID,EGITIMID,TAKIMID,FILMID,TIYATROID,DIZIID,PROGRAMID,ODULID,REKLAMID,ALINANUCRET) 
VALUES ('Tuna','KUZUN','E','2000.07.12','FATİH MAH.2757. SOKAK NO:856 116027 KIRIKKALE MERKEZ/KIRIKKALE','6','5','1','5',NULL,'1',NULL,'4','3','20640')
INSERT INTO OYUNCULAR (AD,SOYAD,CINSIYET,DOGUMGUNU,ACIKADRES,ILETISIMID,EGITIMID,TAKIMID,FILMID,TIYATROID,DIZIID,PROGRAMID,ODULID,REKLAMID,ALINANUCRET) 
VALUES ('Onur','KIRIT','E','1999.05.22','YENİ MAH.BADEMKENT KÜME EVLERİ SOKAK NO:662 88689 ACIPAYAM/DENİZLİ','7','3','4','1','3','3',NULL,NULL,NULL,'20640')
```
