mysql, CREATE DATABASE vk, typing and copy/paste command in the terminal 50/50, exit, mysqldump vk_test.sql, cp vk_test.sql ~/Documents/HomeWorkMysql, git status, git add ., git commite -am , git push...TO BE CONTINUE
dowmload file with data from "http://filldb.info/", thanks, add dump to database vk  ~$ mysql vk < ~/Downloads/fulldbefore.sql , create dump ~$ mysqldump vk > vk_test_data.sql; , copypaste to git ~$ cp vk_test_data.sql ~/Documents/HomeWorkMysql/ ,git add ., git commit -am  '' , git push 

Задание #1

Задание #2

Задание #3

Задание #4

Задание #5

Задание #6

Задание #7

  1)  SELECT users.id, users.first_name   FROM users  JOIN orders   ON  users.id = orders_id;
  2)  SELECT product.name, product_type.name    FROM product    LEFT JOIN product_type    ON product.type_id = product_type.id;
  3)  SELECT product_id, product.name, product_type.name    FROM product    LEFT JOIN product_type  ON product.type_id = product_type.id;

Задание #8

  1)  SELECT profiles.gender, COUNT(likes.user_id)   AS total  FROM profiles  JOIN likes  ON profiles.user_id = likes.user_id   GROUP BY gender   ORDER BY total DESC;
  2)  SELECT SUM(total_like_young) AS total_like_young     FROM (SELECT COUNT(target_types.id) AS total_like_young    FROM profiles    LEFT JOIN likes   ON likes.target_id = profiles.user_id    LEFT JOIN target_types    ON
likes.target_type_id = target_type_id    AND target_types.name = 'users'    GROUP BY profiles.user_id    ORDER BY profiles.birthday    DESC LIMIT 10) AS young;
  3)  SELECT users.id,    COUNT(DISTINCT messages.id) AS activity   FROM users    LEFT JOIN messages   ON users.id = messages.from_user_id    GROUP BY users.id   ORDER BY activity   LIMIT 10;

Задание #9
  
  1)  START TRANSACTION;  INSERT INTO sample.users (`first_name`) SELECT `first_name` FROM online_shop.users WHERE id = 1;  DELETE FROM online_shop.users WHERE id = 1;   COMMIT;
  2)  CREATE OR REPLACE VIEW V AS SELECT product.name AS products, product_type.name AS catalogs FROM product JOIN product_type ON product.type_id = product_type.id; SELECT * FROM V;
  3)  / не выходит /
  4)  DELETE chat FROM chat	JOIN (SELECT created_at	FROM chat  ORDER BY created_at DESC LIMIT 5, 1) AS delpst
ON chat.created_at <= delpst.created_at; SELECT * FROM chat;
  5)  CREATE USER 'test_user'@'localhost' IDENTIFIED BY ''; GRANT ALL PRIVILEGES ON test_database . * TO 'test_user'@'localhost';
      REVOKE ALL PRIVILEGES ON online_shop . * FROM 'test_user'@'localhost';
      GRANT SELECT, SHOW VIEW ON online_shop.* TO 'test_user'@'localhost';
 
 Задание #10
 
   1)  SELECT DISTINCT communities.name AS group.name, COUNT(communities_users.user_id) OVER() / (SELECT COUNT(*) FROM communities) AS aq_users, (SELECT user_id FROM profiles)  OVER w_community_birthday_desc AS youngest, (SELECT user_id FROM profiles)  OVER w_community_birthday_asc AS oldest,  COUNT(communities_users.user_id) OVER w_community AS users_in_group,  (SELECT COUNT(*) AS all_users FROM profiles),   COUNT(communities_users.user_id) OVER w_community / (SELECT COUNT(*) FROM users) *100 AS '%%' FROM communities  LEFT JOIN communities_users ON communities_users.community_id = communities.id  LEFT JOIN users ON communities_users.user_id = users.id   LEFT JOIN profiles  ON profiles.user_id = users.id  WINDOW w_community AS (PARTITION BY communities.id),   w_community_birthday_desc AS (PARTITION BY communities.id ORDER BY profiles.birthday DESC),   w_community_birthday_asc AS (PARTITION BY communities.id ORDER BY profiles.birthday);
      P.S. Все в ошибки падает при моих решениях, хотя я не понимаю что ему не нравится
 
 Задание #11
 
    1) Все падает в ошибки, пока не решил
      
 Задание #12
  
  
