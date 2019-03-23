# mysql
select *
from count
where date >= now() - interval 1 day
#############################################################
SELECT t1.id + 1 AS empy_id
FROM bff_bbs_items AS t1
LEFT JOIN bff_bbs_items AS t2 ON t2.id = t1.id +1
WHERE t2.id IS NULL ORDER BY t1.id ASC
###############################################################
$start = microtime(1);
 $start = microtime(1) - $start;
$articles = R::getAll("SELECT songs.atime, songs.singer, songs.song, songs.created, sing_media.video_id, sing_media.cover,sing_media.parser
                                FROM songs
                                JOIN sing_media on sing_media.absnum=songs.song_id
                                JOIN (SELECT absnum, `type` FROM songs WHERE `type`='".$type."' ORDER BY absnum DESC LIMIT 600 ) as t ON t.absnum = songs.absnum
                                WHERE songs.atime > '".$time24."' ORDER BY songs.atime DESC ");
#####################################################################
24 Часа
SELECT * FROM `table` WHERE (`timestamp` > DATE_SUB(now(), INTERVAL 1 DAY));

#################################################################################
За сегодня
SELECT * FROM TABLE WHERE tc_date >= CURDATE()

За вчера
SELECT * FROM TABLE WHERE tc_date >= (CURDATE()-1) AND tc_date < CURDATE()

За неделю
SELECT * FROM TABLE WHERE tc_date >= DATE_SUB(CURRENT_DATE, INTERVAL 7 DAY)

За месяц (За 30 дней)
SELECT * FROM TABLE WHERE tc_date >= DATE_SUB(CURRENT_DATE, INTERVAL 30 DAY)
#########################################################################################
SELECT (`t1`.`phone`+1) as `empty_phone`
FROM `t1`
WHERE (
	SELECT 1 FROM `t1` as `st` WHERE `st`.`phone` = (`t1`.`phone` + 1)
) IS NULL
ORDER BY `t1`.`phone`
LIMIT 1
