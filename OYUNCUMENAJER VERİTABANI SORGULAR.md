# OYUNCU MENAJER VERİTABANI

*Oluşturulan veritabanı ile ilgili yenilikler ekliyoruz.*

*Oluşturulan rastgele sorguları yanıtlıyoruz.* 

----

**Oyuncular tablosuna yaş kolonu oluştur ve içine yaşlarını gir.**

```sql
USE OYUNCUMENAJERI
ALTER TABLE OYUNCULAR
ADD YAS INT

UPDATE OYUNCULAR SET YAS=DATEDIFF(YEAR,DOGUMGUNU,GETDATE()) 
```

**Oyuncular tablosunda cinsiyeti kız olup 20 - 23 yaş arasını getir.**

```sql
SELECT AD,SOYAD,YAS,CINSIYET FROM OYUNCULAR WHERE YAS BETWEEN '20'AND'23' AND CINSIYET ='K'
```

**Oyuncular tablosundan yaşlarını küçükten büyüğe ve adlarını A'dan Z'ye doğru sıralı şekilde getir.**

```sql
SELECT AD,SOYAD,YAS FROM OYUNCULAR  ORDER BY  YAS,AD
```

**Eğitim tablosundaki beşinci kaydı getir.**

```sql
SELECT * FROM EGITIM WHERE ID=5
```

**Oyuncuların adı soyadı telefon mail açıkadres şeklinde kolonları getir.**

```sql
SELECT AD,SOYAD,TELEFON,MAIL,ACIKADRES FROM OYUNCULAR RIGHT JOIN ILETISIM ON OYUNCULAR.ID=ILETISIM.ID
```

**Oyuncuların ad soyad okuduğu bölüm mezun oldukları yılları getir.**

```sql
SELECT AD, SOYAD, BOLUMADI, MEZUNYILI FROM OYUNCULAR INNER JOIN EGITIM ON OYUNCULAR.ID=EGITIM.ID
```

**Oyuncuların ad soyad ve hukuk danışmanları ile reklam sorumlusu olanları getir.**

```sql
SELECT AD, SOYAD, HUKUKSORUMLUSU, REKLAMSORUMLUSU FROM OYUNCULAR RIGHT JOIN TAKIM ON OYUNCULAR.ID=TAKIM.ID
```

**Dizilerde yer alan oyuncuları ad soyad yaş dizinin adı bölüm sayısı olarak getir.**

```sql
SELECT AD,SOYAD,DIZIADI,BOLUMSAYISI FROM OYUNCULAR INNER JOIN DIZI ON OYUNCULAR.ID=DIZI.ID
```

**Tiyatroda oyun alan oyuncuları ad soyad tiyatro adı sahne aldığı yıl olarak getir.**

```sql
SELECT AD,SOYAD,TIYATROADI,YIL FROM OYUNCULAR INNER JOIN TIYATRO ON OYUNCULAR.ID=TIYATRO.ID
```

**Filmlerde yer alan oyuncuları ad soyad film adı yayınlandığı yıl olarak getir.**

```sql
SELECT AD,SOYAD,FILMADI,YIL FROM OYUNCULAR INNER JOIN FILM ON OYUNCULAR.ID=FILM.ID
```
