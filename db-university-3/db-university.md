Query con Group by
1: SELECT COUNT(*) AS `number_student`, YEAR(`enrolment_date`) AS `enrolment_year` FROM `students` GROUP BY `enrolment_year`;
2: SELECT COUNT(*) AS `number_building`, `office_address` FROM `teachers` GROUP BY `office_address`;
3: SELECT AVG(`vote`) AS `average_vote`, `exam_id` FROM `exam_student` GROUP BY `exam_id`;
4: SELECT COUNT(*) AS `number_courses`, `department_id` AS `department` FROM `degrees` GROUP BY `department`;

Query con Join
1: SELECT * FROM `students` JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id` WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
2: SELECT * FROM `degrees` JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` WHERE `departments`.`name` = 'Dipartimento di Neuroscienze';
3: SELECT * FROM `course_teacher` JOIN `courses` ON `courses`.`id` = `course_teacher`.`course_id` JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id` WHERE `teachers`.`name` = 'Fulvio' AND `teachers`.`surname` = 'Amato';
4: SELECT `students`.`name`, `students`.`surname`, `students`.`date_of_birth`, `students`.`email`, `degrees`.`name`, `degrees`.`level`, `degrees`.`address`, `departments`.`name` FROM `students` JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id` JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` ORDER BY `students`.`surname`, `students`.`name`; 
5: SELECT * FROM `degrees` JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id` JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id` JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`;
6: SELECT DISTINCT `teachers`.* FROM `teachers` JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id` JOIN `courses` ON `courses`.`id` = `course_teacher`.`course_id` JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id` JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` WHERE `departments`.`name` = 'Dipartimento di Matematica';