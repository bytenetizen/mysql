# mysql
select *
from count
where date >= now() - interval 1 day



24 Часа
SELECT * FROM `table` WHERE (`timestamp` > DATE_SUB(now(), INTERVAL 1 DAY));
