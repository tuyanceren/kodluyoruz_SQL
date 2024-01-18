# Kodluyoruz İlk Repo

Bu repo [kodluyoruz](https://www.kodluyoruz.org/) Front-End Eğitiminde oluşturduğumuz ilk repo. İçerisinde bir adet README dosyası, bir adet de index.html barındırıyor.
## Installation
Öncelikle projeyi clonelayın. (Buraya sizin reponuzdan aldığınız link gelecek.
 ``` 
 git clone https://github.com/tuyanceren/kodluyoruzilkrepo.git
 ``` 


## Usage
Projeyi cloneladıktan sonra Visual Studio Code programında açınız.

Linux için:
``` 
cd kodluyoruzilkrepo
code .
``` 



## Contributing
Pull requestler kabul edilir. Büyük değişiklikler için, lütfen önce neyi değiştirmek istediğinizi tartışmak için bir konu açınız.


## License
[MIT](https://choosealicense.com/licenses/mit/)

----------------------------------------------
# sql_odev1
**Patika SQL eğitimi kapmasında yaptığım ödev1 çalışması**
-
1._film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız._

 ` SELECT title, description FROM film; `

2._film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız._

 ` SELECT * FROM film WHERE length > 60 and length < 75; `

3._film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız._

 ` SELECT * FROM film WHERE rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99; `

4._customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?_

 ` SELECT last_name FROM customer WHERE first_name = 'Mary'; `

5._film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız._

 ` SELECT * FROM film WHERE NOT length > 50 AND NOT (rental_rate = 2.99 OR rental_rate = 4.99); `
 
**Sorgu senaryolarını dvdrental.tar isimli dosyamızda bulunan örnek veri tabanı üzerinden gerçekleştirebilirsiniz.**

# SQL_ODEV2
**Patika SQL eğitimi kapsamındaki ikinci ödev**

1._film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)_
```sql
SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99;  
```
2._actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)_
```sql
SELECT first_name, last_name FROM actor WHERE first_name IN ('Penelope','Nick','Ed') ;
```
3._film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)_
```sql 
SELECT * FROM film WHERE rental_rate IN (0.99, 2.99, 4.99) AND replacement_cost IN (12.99, 15.99, 28.99)
```
Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip)  isimli dosyayı indirerek gerçekleştirebilirsiniz.

# SQL_ODEV3
**Patika SQL eğitimi kapsamındaki ödev3**
-
1._country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız._
```sql
SELECT country FROM country WHERE country LIKE 'A%a';
```
2._country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız._
```sql 
SELECT country FROM country WHERE country LIKE '_____%n';
```
3._film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız._
```sql
SELECT title FROM film WHERE title ILIKE 'T%T%T%T%';
```
4._film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız._
```sql
SELECT * FROM film WHERE title LIKE 'C%' AND length>90 AND  rental_rate = 2.99
```

Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.

# SQL_ODEV4
**Patika SQL eğitimi kapsamında yaptığım ödev4**
-
1._film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız._
```sql
SELECT DISTINCT(replacement_cost) FROM film;
```
2._film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?_
```sql
SELECT COUNT(DISTINCT(replacement_cost)) FROM film;
```
3._film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?_
```sql
SELECT COUNT(*) FROM film WHERE title LIKE 'T%' AND  rating = 'G';
```
4._country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?_
```sql
SELECT COUNT(*) FROM country WHERE country LIKE '_____';
```
5._city tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?_
```sql
SELECT COUNT(*) FROM city WHERE city ILIKE '%r';
```
---------
Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.

# SQL_ODEV5
**Patika SQL eğitimi kapsamında yaptığım ödev5**
-----
1._film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız._
```sql
SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5; 
```
2._film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci 5 filmi sıralayınız._
```sql
SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
LIMIT 5;
```
3._customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız._
```sql
SELECT * FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4;
```
---------
Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.

# SQL_ODEV6
**Patika SQL eğitimi kapsamında yaptığım ödev6**
----------
1._film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?_
```sql
SELECT ROUND(AVG(rental_rate),3) FROM film;
```

2._film tablosunda bulunan filmlerden kaçtanesi 'C' karekteri ile başlar?_
```sql
SELECT COUNT(*) FROM film
WHERE title LIKE 'C%';
```

3._film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?_
```sql
SELECT MAX(length) FROM film
WHERE rental_rate = 0.99;
```

4._film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?_
```sql
SELECT DISTINCT replacement_cost FROM film
WHERE length>150;
```
--------
Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.

***
