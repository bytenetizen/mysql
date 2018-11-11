# mysql
select *
from count
where date >= now() - interval 1 day
###############################################################
$articles = R::getAll("SELECT songs.atime, songs.singer, songs.song, songs.created, sing_media.video_id, sing_media.cover,sing_media.parser
                                FROM songs
                                JOIN sing_media on sing_media.absnum=songs.song_id
                                JOIN (SELECT absnum, `type` FROM songs WHERE `type`='".$type."' ORDER BY absnum DESC LIMIT 600 ) as t ON t.absnum = songs.absnum
                                WHERE songs.atime > '".$time24."' ORDER BY songs.atime DESC ");
#####################################################################
24 Часа
SELECT * FROM `table` WHERE (`timestamp` > DATE_SUB(now(), INTERVAL 1 DAY));
