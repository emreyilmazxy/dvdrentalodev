# 🎬 PostgreSQL Film ve Müşteri Sorguları

Bu repoda film ve müşteri tabloları üzerinde yazılmış temel SQL sorguları yer alır.

```sql
-- 1. Film adları ve açıklamaları
SELECT title, description FROM film;

-- 2. Süresi 60-75 dakika arası olan filmler
SELECT * FROM film
WHERE length > 60 AND length < 75;

-- 3. Kiralama ücreti 0.99 ve değiştirme maliyeti 12.99 olan
-- veya sadece değiştirme maliyeti 28.99 olan filmler
SELECT * FROM film
WHERE (rental_rate = 0.99 AND replacement_cost = 12.99)
   OR replacement_cost = 28.99;

-- 4. Adı "Mary" olan müşteriler
SELECT first_name, last_name FROM customer
WHERE first_name = 'Mary';

-- 5. Süresi 50 dakikadan kısa ve kiralama ücreti 2.99 veya 4.99 olmayan filmler
SELECT * FROM film
WHERE length <= 50
  AND rental_rate <> 2.99
  AND rental_rate <> 4.99;
