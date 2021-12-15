1: SELECT * FROM `students` WHERE YEAR(`date_of_birth`) = '1990';
2: SELECT * FROM `courses` WHERE `cfu` > 10;
3: SELECT * FROM `students` WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, NOW()) > 30
4: SELECT * FROM `courses` WHERE `period` = 'I semestre' AND `year` = '1';
5: SELECT * FROM `exams` WHERE HOUR(`hour`) >= '14' AND `date` = '2020-06-20';
6: SELECT * FROM `degrees` WHERE `level` = 'magistrale';
7: SELECT COUNT(*) FROM `departments`;
8: SELECT * FROM `teachers` WHERE `phone` IS NULL