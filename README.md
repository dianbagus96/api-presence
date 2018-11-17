# api-presence
### SCHEDULE
SELECT A.MAPEL_CLASS_DAY `day`, CONCAT(B.CLASS_NUMBER, B.TYPE) `kelas`, C.MAPEL_DESC `mapel`, 
CONCAT(TIME_FORMAT(A.MAPEL_CLASS_START, '%H:%i'), ' - ', TIME_FORMAT(A.MAPEL_CLASS_END, '%H:%i')) `jam`, D.GURU_ID `nip`, CONCAT(GURU_FIRST_NAME, ' ',GURU_LAST_NAME) `guru`, E.GURU_IMG `pic` FROM tx_class_mapel A
LEFT JOIN tm_class B ON B.CLASS_ID = A.CLASS_ID
LEFT JOIN tm_mapel C ON C.MAPEL_ID = A.MAPEL_ID
LEFT JOIN tx_guru_mapel D ON D.JADWAL_ID = A.JADWAL_ID
LEFT JOIN tm_guru E ON E.GURU_ID = D.GURU_ID
