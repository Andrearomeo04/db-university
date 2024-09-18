group by

1. Contare quanti iscritti ci sono stati ogni anno

SELECT COUNT(*) AS `numero_iscritti`, YEAR(`enrolment_date`) AS `anno`
FROM `students`
GROUP BY YEAR(`enrolment_date`);

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT COUNT(*) AS `n_docenti`, `office_address` AS `uffici` 
FROM `teachers`
GROUP BY `office_address`

3. Calcolare la media dei voti di ogni appello d'esame

SELECT AVG(`vote`) AS `media`, `exam_id` AS `esame`
FROM `exam_student`
GROUP BY `exam_id`


4. Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT COUNT(*) AS `corsi`, `department_id` AS `dipartimento`
FROM `degrees`
GROUP BY `department_id`;

join

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT 
    `students`.name,
    `students`.surname,
    `students`.date_of_birth,
    `students`.fiscal_code,
    `students`.enrolment_date,
    `students`.registration_number,
    `students`.email
FROM `students`
JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id`
WHERE `degrees`.`name` = "corso di laurea in economia";

 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
 Neuroscienze

SELECT 
    `degrees`.name,
    `degrees`.`level`,
    `degrees`.`address`,
    `degrees`.`email`,
    `degrees`.`website`
FROM `degrees`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = "dipartimento di neuroscienze"
AND `degrees`.`level` = "magistrale";

 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)



 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
 sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
 nome



 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti



 6. Selezionare tutti i docenti che insegnano nel Dipartimento di
 Matematica (54)


 
 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
 per ogni esame, stampando anche il voto massimo. Successivamente,
 filtrare i tentativi con voto minimo 18.
