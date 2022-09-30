/*
film tablosundan 'K' karakteri ile başlayan en uzun ve replacenet_cost u en düşük 4 filmi sıralayınız.
film tablosunda içerisinden en fazla sayıda film bulunduran rating kategorisi hangisidir?
cutomer tablosunda en çok alışveriş yapan müşterinin adı nedir?
category tablosundan kategori isimlerini ve kategori başına düşen film sayılarını sıralayınız.
film tablosunda isminde en az 4 adet 'e' veya 'E' karakteri bulunan kç tane film vardır?
*/

/* 1. film tablosundan 'K' karakteri ile başlayan en uzun ve replacement_cost u en düşük 4 filmi sıralayınız. */

(
	SELECT title, replacement_cost, length FROM film
 	WHERE title LIKE 'K%'
	ORDER BY length DESC
	LIMIT 4
)
UNION
(	
	SELECT title, replacement_cost, length FROM film
  	WHERE title LIKE 'K%'
	ORDER BY replacement_cost ASC
	LIMIT 4
);

/* 2. film tablosunda içerisinden en fazla sayıda film bulunduran rating kategorisi hangisidir? */

SELECT rating, COUNT(rating) FROM film
GROUP BY rating;

/* 3. customer tablosunda en çok alışveriş yapan müşterinin adı nedir? */

SELECT customer_id, COUNT(payment_id) FROM payment
GROUP BY customer_id
ORDER BY COUNT(payment_id) DESC;

/* 4. category tablosundan kategori isimlerini ve kategori başına düşen film sayılarını sıralayınız. */

SELECT category.category_id, category.name , COUNT(film.film_id)
FROM film_category
INNER JOIN category	ON category.category_id = film_category.category_id
INNER JOIN film ON film.film_id = film_category.film_id
GROUP BY category.category_id
ORDER BY category.category_id;

/*5. film tablosunda isminde en az 4 adet 'e' veya 'E' karakteri bulunan kç tane film vardır? */

SELECT film.title, COUNT(film.title) FROM film
WHERE title ILIKE '%e%e%e%e%';
