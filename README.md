# SQL
My works in the database
Подключится к

Host: 159.69.151.133

Port: 5056

DB: qa_db_2

User: user_22_34

Pass: 123

1. Вывести все поля и все строки: select * from qa_users;

2. Вывести всех студентов в таблице: select * from qa_users;

3. Вывести только Id пользователей: select user_id from qa_users;

4. Вывести только имя пользователей: select username from qa_users;

5. Вывести только email пользователей:
select email from qa_users;

6. Вывести имя и email пользователей: select username, email from qa_users;

7. Вывести id, имя, email и дату создания пользователей: select user_id, username, email, created_on from qa_users;

8. Вывести пользователей где password 12333: select * from qa_users where "password" = '12333';

9. Вывести пользователей которые были созданы 2021-03-26 00:00:00 : select user_id, username from qa_users where created_on = '2021-03-26 00:00:00.00';

10. Вывести пользователей где в имени есть слово Анна: select * from qa_users where username like '%Anna%’;

11. Вывести пользователей где в имени в конце есть 8: select * from qa_users where username like '%8';

12. Вывести пользователей где в имени в есть буква а: select * from qa_users where username like '%a%';

13. Вывести пользователей которые были созданы 2021-07-12 00:00:00: select * from qa_users where created_on = '2021-07-12 00:00:000';

14. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и имеют пароль 1m313: select * from qa_users where created_on = '2021-07-12 00:00:000' and password = '1m313';

15. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и у которых в имени есть слово Andrey: select * from qa_users where created_on = '2021-07-12 00:00:000' and username like '%Andrey%';

16. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и у которых в имени есть цифра 8: select * from qa_users where created_on = '2021-07-12 00:00:000' and username like '%8%';

17. Вывести пользователя у которых id равен 10: select* from qa_users where user_id = 10;

18. Вывести пользователя у которых id равен 53: select * from qa_users where user_id = 53;

19. Вывести пользователя у которых id больше 40: select * from qa_users where user_id > 40;

20. Вывести пользователя у которых id меньше 30:
select * from qa_users where user_id < 30;

21. Вывести пользователя у которых id меньше 27 или больше 88:
select * from qa_users where user_id < 27 or user_id > 88;

22. Вывести пользователя у которых id меньше либо равно 37:
select * from qa_users where user_id <= 37;

23. Вывести пользователя у которых id больше либо равно 37: select * from qa_users where user_id >= 37;

24. Вывести пользователя у которых id больше 80 но меньше 90:
select * from qa_users where user_id > 80 and user_id <90;

25. Вывести пользователя у которых id между 80 и 90: select * from qa_users where user_id between 80 and 90;

26. Вывести пользователей где password равен 12333, 1m313, 123313:
select * from qa_users where password in ('12333', '1m313', '123313');

27. Вывести пользователей где created_on равен 2020-10-03 00:00:00, 2021-05-19 00:00:00, 2021-03-26 00:00:00 :
select * from qa_users where created_on in ('2020-10-03 00:00:00', '2021-05-19 00:00:00', '2021-03-26 00:00:00');

28. Вывести минимальный id: select min (user_id) as Smallest_ID from qa_users;

29. Вывести максимальный:
select max (user_id) as Max_ID from qa_users;

30. Вывести количество пользователей: select count(user_id) from qa_users;

31. Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку возрастания даты добавления пользоватлеля: select user_id, username, created_on
from qa_users order by created_on;

32. Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку убывания даты добавления пользоватлеля: select user_id, username, created_on
from qa_users order by created_on desc;

SQL HomeWork 2. Joins

Подключится к Host: 159.69.151.133 Port: 5056 DB: qa_db_2 User: user_22_34 Pass: 123

1. Вывести всех работников чьи зарплаты есть в базе, вместе с зарплатами.

select e.employee_name, es.monthly_salary from employees as e join employees_salary as es on e.id = es.employee_id;

2. Вывести всех работников у которых ЗП меньше 2000.

select e.employee_name, es.monthly_salary from employees as e join employees_salary as es on e.id = es.employee_id where monthly_salary < 2000;

3. Вывести все зарплатные позиции, но работник по ним не назначен. (ЗП есть, но не понятно кто её получает.)

select employee_name, monthly_salary from employees as e right join employees_salary as es on e.id = es.employee_id where employee_name is null;

4. Вывести все зарплатные позиции меньше 2000 но работник по ним не назначен. (ЗП есть, но не понятно кто её получает.)

select employee_name, monthly_salary from employees as e right join employees_salary as es on e.id = es.employee_id where employee_name is null and monthly_salary <2000;

5. Найти всех работников кому не начислена ЗП.

select employee_name, monthly_salary from employees as e full join employees_salary as es on e.id = es.employee_id where monthly_salary is null;

6. Вывести всех работников с названиями их должности.

select e.employee_name, roles.role_name
from employees as e full join roles_employees as re on e.id = re.employee_id join roles on re.role_id = roles.id;

7. Вывести имена и должность только Java разработчиков.

select e.employee_name, roles.role_name
from employees as e full join roles_employees as re on e.id = re.employee_id join roles on re.role_id = roles.id where roles.role_name like '%Java %';

8. Вывести имена и должность только Python разработчиков.

select e.employee_name, roles.role_name
from employees as e full join roles_employees as re on e.id = re.employee_id join roles on re.role_id = roles.id where roles.role_name like '%Python%';

9. Вывести имена и должность всех QA инженеров.

select e.employee_name, roles.role_name
from employees as e full join roles_employees as re on e.id = re.employee_id join roles on re.role_id = roles.id where roles.role_name like '%QA%';

10. Вывести имена и должность ручных QA инженеров.

select e.employee_name, roles.role_name
from employees as e full join roles_employees as re on e.id = re.employee_id join roles on re.role_id = roles.id where roles.role_name like '%QA%' and roles.role_name like '%Manual%';

11. Вывести имена и должность автоматизаторов QA

select e.employee_name, roles.role_name
from employees as e full join roles_employees as re on e.id = re.employee_id join roles on re.role_id = roles.id where roles.role_name like '%Automation%' and roles.role_name like '%QA%';

12. Вывести имена и зарплаты Junior специалистов

select e.employee_name, es.monthly_salary
from employees as e full join roles_employees as re on e.id = re.employee_id join roles on re.role_id = roles.id full join employees_salary as es on re.employee_id = es.employee_id where roles.role_name like '%Junior%';

13. Вывести имена и зарплаты Middle специалистов

select e.employee_name, es.monthly_salary
from employees as e full join roles_employees as re on e.id = re.employee_id join roles on re.role_id = roles.id full join employees_salary as es on re.employee_id = es.employee_id where roles.role_name like '%Middle%';

14. Вывести имена и зарплаты Senior специалистов select employee_name, monthly_salary

from employees as e left join roles_employees as re on e.id = re.employee_id full join roles on re.role_id = roles.id full join employees_salary as es on es.employee_id = re.employee_id where roles.role_name like '%Senior%';

15. Вывести зарплаты Java разработчиков select role_name, monthly_salary

from employees as e left join roles_employees as re on e.id = re.employee_id full join roles on re.role_id = roles.id join employees_salary as es on es.employee_id = re.employee_id where roles.role_name like '%Java %';

16. Вывести зарплаты Python разработчиков select role_name, monthly_salary

from employees as e left join roles_employees as re on e.id = re.employee_id full join roles on re.role_id = roles.id join employees_salary as es on es.employee_id = re.employee_id where roles.role_name like '%Python%';

17. Вывести имена и зарплаты Junior Python разработчиков

select e.employee_name , r.role_name, es.monthly_salary from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%Junior%' and r.role_name like '%Python%';

18. Вывести имена и зарплаты Middle JS разработчиков

select e.employee_name , r.role_name, es.monthly_salary from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%Middle%' and r.role_name like '%JavaS%';

19. Вывести имена и зарплаты Senior Java разработчиков

select e.employee_name , r.role_name, es.monthly_salary from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%Senior%' and r.role_name like '%Java %';

20. Вывести зарплаты Junior QA инженеров

select role_name , monthly_salary from employees as e full join roles_employees as re on e.id = re.employee_id full join roles on re.role_id = roles.id join employees_salary as es on re.employee_id = es.employee_id where roles.role_name like '%Junior%' and roles.role_name like '%QA%';

21. Вывести среднюю зарплату всех Junior специалистов

select AVG (es.monthly_salary) as average_salary_Junior from employees as e full join roles_employees as re on e.id = re.employee_id full join roles on re.role_id = roles.id join employees_salary as es on re.employee_id = es.employee_id where roles.role_name like '%Junior%';

22. Вывести сумму зарплат JS разработчиков

select sum (es.monthly_salary) as JS_Salary from employees as e full join roles_employees as re on e.id = re.employee_id full join roles on re.role_id = roles.id join employees_salary as es on re.employee_id = es.employee_id where roles.role_name like '%JavaS%';

23. Вывести минимальную ЗП QA инженеров

select min (es.monthly_salary) as min_salary_QA from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id full join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%QA%’;

24. Вывести максимальную ЗП QA инженеров

select max (es.monthly_salary) as max_salary_QA from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id full join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%QA%';

25. Вывести количество QA инженеров

select count (e.employee_name) as count from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id full join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%QA%';

26. Вывести количество Middle специалистов.

select count (e.employee_name) as count_Middle from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id full join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%Middle%';

27. Вывести количество разработчиков

select count (e.employee_name) as count_developers from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id full join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%developer%';

28. Вывести фонд (сумму) зарплаты разработчиков.

select sum (es.monthly_salary) as sum_salary_developers from employees as e left join roles_employees as re on e.id = re.employee_id full join roles as r on re.role_id = r.id full join employees_salary as es on re.employee_id = es.employee_id where r.role_name like '%developer%';

29. Вывести имена, должности и ЗП всех специалистов по возрастанию

select e.employee_name , r.role_name, es.monthly_salary from employees as e left join roles_employees as re on e.id = re.employee_id join roles as r on re.role_id = r.id join employees_salary as es on re.employee_id = es.employee_id order by es.monthly_salary ;

30. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов у которых ЗП от 1700 до 2300

select e.employee_name , r.role_name, es.monthly_salary from employees as e left join roles_employees as re on e.id = re.employee_id join roles as r on re.role_id = r.id join employees_salary as es on re.employee_id = es.employee_id where es.monthly_salary >= 1700 and es.monthly_salary < 2300 order by es.monthly_salary ;

31. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов у которых ЗП меньше 2300

select e.employee_name , r.role_name, es.monthly_salary from employees as e left join roles_employees as re on e.id = re.employee_id join roles as r on re.role_id = r.id join employees_salary as es on re.employee_id = es.employee_id where es.monthly_salary < 2300 order by es.monthly_salary ;

32. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов у которых ЗП равна 1100, 1500, 2000

select e.employee_name , r.role_name, es.monthly_salary from employees as e left join roles_employees as re on e.id = re.employee_id join roles as r on re.role_id = r.id join employees_salary as es on re.employee_id = es.employee_id where es.monthly_salary in ('1100', '1500', '2000') order by es.monthly_salary;
