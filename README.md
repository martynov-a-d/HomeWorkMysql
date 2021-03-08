mysql, CREATE DATABASE vk, typing and copy/paste command in the terminal 50/50, exit, mysqldump vk_test.sql, cp vk_test.sql ~/Documents/HomeWorkMysql, git status, git add ., git commite -am , git push...TO BE CONTINUE
dowmload file with data from "http://filldb.info/", thanks, add dump to database vk  ~$ mysql vk < ~/Downloads/fulldbefore.sql , create dump ~$ mysqldump vk > vk_test_data.sql; , copypaste to git ~$ cp vk_test_data.sql ~/Documents/HomeWorkMysql/ ,git add ., git commit -am  '' , git push 

Задание #1

Задание #2

Задание #3

Задание #4

Задание #5

Задание #6

Задание #7

Задание #8

  1)  mysql> SELECT profiles.gender, COUNT(likes.user_id)   AS total  FROM profiles  JOIN likes  ON profiles.user_id = likes.user_id   GROUP BY gender   ORDER BY total DESC;
  2)  mysql> SELECT SUM(total_like_young) AS total_like_young     FROM (SELECT COUNT(target_types.id) AS total_like_young    FROM profiles    LEFT JOIN likes   ON likes.target_id = profiles.user_id    LEFT JOIN target_types    ON
likes.target_type_id = target_type_id    AND target_types.name = 'users'    GROUP BY profiles.user_id    ORDER BY profiles.birthday    DESC LIMIT 10) AS young;
  3)  SELECT users.id,    COUNT(DISTINCT messages.id) AS activity   FROM users    LEFT JOIN messages   ON users.id = messages.from_user_id    GROUP BY users.id   ORDER BY activity   LIMIT 10;

Задание #9
