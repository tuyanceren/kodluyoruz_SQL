# Kodluyoruz İlk Repo

Bu repo [kodluyoruz](https://www.kodluyoruz.org/) Front-End Eğitiminde oluşturduğumuz ilk repo. İçerisinde bir adet README dosyası, bir adet de index.html barındırıyor.
## Installation
Öncelikle projeyi clonelayın. (Buraya sizin reponuzdan aldığınız link gelecek.
 ``` 
 git clone https://github.com/tuyanceren/kodluyoruz_SQL.git
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

# SQL_ODEV7
**Patika SQL eğitimi kapsamında yaptığım ödev7**
-------
1._film tablosunda bulunan filmleri rating değerlerine göre gruplayınız._
```sql
SELECT rating FROM film
GROUP BY rating;
```
2._film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız._
```sql
SELECT replacement_cost, COUNT(*) FROM film
GROUP BY replacement_cost
HAVING COUNT(*)>50;
```
3._customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?_
```sql
SELECT store_id, COUNT(*) FROM customer
GROUP BY store_id;
```
4._city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıra country_id bilgisini ve şehir sayısını paylaşınız._
```sql
SELECT country_id , COUNT(*) FROM city
GROUP BY country_id
ORDER BY COUNT(*) DESC
LIMIT 1;
```
--------
Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.

# SQL_ODEV8
**Patika SQL eğitimi kapsamında yaptığım ödev8**
-------------
1._test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım._
```sql
CREATE TABLE employee (
	id INTEGER,
	name VARCHAR(50) NOT NULL,
	email VARCHAR(100),
	birthday DATE 
);
```
2._Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim._

**[Mockaroo](https://www.mockaroo.com) ya tıklayarak sizde kendi tablonuzu oluşturabilirsiniz.**
```sql
insert into employee (id, name, email, birthday) values (1, 'Adam', 'acolam0@google.com.hk', '9/16/1944');
insert into employee (id, name, email, birthday) values (2, 'Jordan', 'jelverstone1@marketwatch.com', '9/11/1983');
insert into employee (id, name, email, birthday) values (3, 'Nat', 'nrubert2@deviantart.com', '3/30/1916');
insert into employee (id, name, email, birthday) values (4, 'Roch', 'rwallett3@yolasite.com', '12/31/2011');
insert into employee (id, name, email, birthday) values (5, 'Ewan', 'eorbine4@reverbnation.com', '10/16/1937');
insert into employee (id, name, email, birthday) values (6, 'Alair', 'agreatbatch5@naver.com', '7/3/2011');
insert into employee (id, name, email, birthday) values (7, 'Maure', 'mhallan6@msn.com', '4/24/1973');
insert into employee (id, name, email, birthday) values (8, 'Duff', 'dsazio7@nydailynews.com', '1/10/1902');
insert into employee (id, name, email, birthday) values (9, 'Cyndia', 'clepere8@yolasite.com', '11/15/1985');
insert into employee (id, name, email, birthday) values (10, 'Laryssa', 'ldohmer9@360.cn', '12/17/2001');
insert into employee (id, name, email, birthday) values (11, 'Phillipe', 'pjeffa@hhs.gov', '10/31/1926');
insert into employee (id, name, email, birthday) values (12, 'Maddie', 'mferronb@theguardian.com', '6/22/2020');
insert into employee (id, name, email, birthday) values (13, 'Giffer', 'givensc@google.fr', '8/30/1951');
insert into employee (id, name, email, birthday) values (14, 'Lyndy', 'lbenitod@bluehost.com', '6/18/1957');
insert into employee (id, name, email, birthday) values (15, 'Lanette', 'lkondratoviche@baidu.com', '10/18/2002');
insert into employee (id, name, email, birthday) values (16, 'Danna', 'dailwardf@yellowbook.com', '5/15/1930');
insert into employee (id, name, email, birthday) values (17, 'Francyne', 'fdempseyg@goo.ne.jp', '1/3/1952');
insert into employee (id, name, email, birthday) values (18, 'Gwennie', 'gyeelesh@nationalgeographic.com', '10/6/1997');
insert into employee (id, name, email, birthday) values (19, 'Eolande', 'ewhetsoni@wikispaces.com', '1/15/1996');
insert into employee (id, name, email, birthday) values (20, 'Mavra', 'mhandysidej@addtoany.com', '1/15/2008');
insert into employee (id, name, email, birthday) values (21, 'Delano', 'dheathornk@example.com', '10/2/1936');
insert into employee (id, name, email, birthday) values (22, 'Justine', 'jmarcuml@devhub.com', '1/21/1955');
insert into employee (id, name, email, birthday) values (23, 'Giorgi', 'gbrandsm@dailymail.co.uk', '1/24/1909');
insert into employee (id, name, email, birthday) values (24, 'Ollie', 'odoonen@wunderground.com', '12/10/1945');
insert into employee (id, name, email, birthday) values (25, 'Ferdie', 'fmooreyo@jiathis.com', '7/16/1928');
insert into employee (id, name, email, birthday) values (26, 'Lacee', 'lterbrugp@mapy.cz', '11/23/1979');
insert into employee (id, name, email, birthday) values (27, 'Lammond', 'lmenureq@indiegogo.com', '3/15/1934');
insert into employee (id, name, email, birthday) values (28, 'Amanda', 'afintophr@qq.com', '11/8/1906');
insert into employee (id, name, email, birthday) values (29, 'Val', 'vfinlows@noaa.gov', '4/6/1930');
insert into employee (id, name, email, birthday) values (30, 'Angy', 'aailsburyt@hostgator.com', '2/6/1931');
insert into employee (id, name, email, birthday) values (31, 'Dorelia', 'dcherrisonu@telegraph.co.uk', '8/25/1925');
insert into employee (id, name, email, birthday) values (32, 'Danyelle', 'dallomv@craigslist.org', '5/18/1907');
insert into employee (id, name, email, birthday) values (33, 'Aretha', 'abuschw@ovh.net', '1/19/1986');
insert into employee (id, name, email, birthday) values (34, 'Leopold', 'lmorpheyx@jalbum.net', '2/19/1923');
insert into employee (id, name, email, birthday) values (35, 'Adriena', 'ajosephiy@blog.com', '7/1/1958');
insert into employee (id, name, email, birthday) values (36, 'Wilow', 'wmcwhirterz@xinhuanet.com', '7/18/1933');
insert into employee (id, name, email, birthday) values (37, 'Travus', 'tketchen10@com.com', '1/28/1962');
insert into employee (id, name, email, birthday) values (38, 'Freemon', 'fromaynes11@trellian.com', '10/7/1926');
insert into employee (id, name, email, birthday) values (39, 'Valerye', 'vranderson12@biblegateway.com', '8/24/1945');
insert into employee (id, name, email, birthday) values (40, 'Nollie', 'ntrahearn13@merriam-webster.com', '10/18/1923');
insert into employee (id, name, email, birthday) values (41, 'Wyatan', 'wvansaltsberg14@w3.org', '7/28/1992');
insert into employee (id, name, email, birthday) values (42, 'Pascal', 'pdiffley15@ftc.gov', '8/30/1990');
insert into employee (id, name, email, birthday) values (43, 'Crystie', 'croels16@nydailynews.com', '1/23/1978');
insert into employee (id, name, email, birthday) values (44, 'Barnebas', 'bgurg17@newyorker.com', '8/20/1978');
insert into employee (id, name, email, birthday) values (45, 'Thekla', 'tdomokos18@yellowpages.com', '2/13/1931');
insert into employee (id, name, email, birthday) values (46, 'Shelbi', 'sbrotherhood19@elegantthemes.com', '2/4/1967');
insert into employee (id, name, email, birthday) values (47, 'Aida', 'achansonne1a@admin.ch', '8/8/1935');
insert into employee (id, name, email, birthday) values (48, 'Alejoa', 'aterrington1b@nytimes.com', '12/12/2020');
insert into employee (id, name, email, birthday) values (49, 'Noellyn', 'nnono1c@google.nl', '9/14/2008');
insert into employee (id, name, email, birthday) values (50, 'Madelin', 'mondrusek1d@netvibes.com', '6/12/1965');
```
3._Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım._
```sql
UPDATE author
SET id = '28745',
	  name = 'tuyan ceren',
	  email = 'tuyanceren@icloud.com'
WHERE id = '23';
```
4._Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım._
```sql
DELETE FROM author 
WHERE id = 12;
-- yada WHERE komutundan sonra bunlarıda yazabilirsiniz.
DELETE FROM author 
WHERE name = 'tuyan';
WHERE email = 'example@example.com'
```
-------------
Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.

# SQL_ODEV9
**Patika.dev sayfasındaki SQL eğitimi kapsamında yaptığım 9. ödev**
------------------------
1._city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız._
```sql
SELECT city, country FROM city
INNER JOIN country ON country.country_id =city.city_id ;
```
2._customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız._
```sql
SELECT  payment_id, first_name, last_name FROM customer
INNER JOIN payment ON payment.customer_id = customer.customer_id ;
```
3._customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız._
```sql
SELECT  rental_id, first_name, last_name FROM customer
INNER JOIN rental ON rental.customer_id = customer.customer_id ;
```
------------------------------------
**Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.**

# SQL_ODEV10
**Patika SQL eğitimi kapsamında yaptığım ödev10.**
----------------
1._city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız._
```sql
SELECT city, country FROM city 
LEFT JOIN country ON city.country_id=country.country_id;
```
2._customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız._
```sql
SELECT  payment_id, first_name, last_name FROM customer
RIGHT JOIN payment ON payment.customer_id = customer.customer_id ;
```
3._customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız._
```sql
SELECT  rental_id, first_name, last_name FROM customer
FULL JOIN rental ON rental.customer_id = customer.customer_id ;
```
----------------------
**Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.**

# SQL_ODEV11
**Patika SQL eğitimi kapsamında yaptığım ödev 11**
--------------
1._actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım._
```sql
(SELECT  first_name FROM customer)
UNION
(SELECT first_name FROM actor);
```
2._actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım._
```sql
(SELECT  first_name FROM customer)
INTERSECT
(SELECT first_name FROM actor);
```
3._actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım._
```sql
(SELECT  first_name FROM customer)
EXCEPT
(SELECT first_name FROM actor);
```
4._İlk 3 sorguyu tekrar eden veriler için de yapalım._
```sql
(SELECT  first_name FROM customer)
UNION ALL
(SELECT first_name FROM actor);
-------------------------------
(SELECT  first_name FROM customer)
INTERSECT ALL
(SELECT first_name FROM actor);
-------------------------------
(SELECT  first_name FROM customer)
EXCEPT ALL
(SELECT first_name FROM actor);
```

---------------
**Sorgu senaryolarını [dvdrental.tar](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) isimli dosyayı indirerek gerçekleştirebilirsiniz.**

***
