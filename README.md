Quendi - платформа для совместного блоггинга
======

Из Википедии:
> Э́льфы (англ. Elves, ед.ч. — англ. Elf; самоназвание — кв. Quendi, «те, кто говорит», синд. Edhil) — в легендариуме Джона Р. Р. Толкина один из свободных народов, населявший вымышленный мир Средиземья в отдалённом прошлом.

http://spinoff.comicbookresources.com/wp-content/uploads/2013/12/hobbit-lilly4.jpg

1. О проекте
2. Требуемое ПО
3. Установка и настройка
4. Используемые стандарты
5. Чем я могу помочь проекту?
6. Разработчики
7. Конечная цель проекта
8. Лицензия

```
server {
    listen   80;
    root /var/www/quendy/public;
    index index.php index.html index.htm;
    server_name quendy;
    location / {
		try_files $uri $uri/ /index.php?$args;
    }
    location ~ \.php$ {
		fastcgi_split_path_info ^(.+\.php)(/.+)$;
		fastcgi_pass unix:/var/run/php5-fpm.sock;
		fastcgi_index index.php;
		include fastcgi_params;
    }
}
```