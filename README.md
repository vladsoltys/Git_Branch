# GitHub. HW_2
**Studied on the course:**

> Creating of branches, moving across branches, merging branches on the local and remote repository
```
(git branch, git checkout, git merge, git push, git pull)
```

## Git_Branch_commands

> - On the GitHub create remote repository "Git_Branch_terminal"

> - In the gitbush terminal in the folder "my_repositories" make git clone (https://github.com/vladsoltys/Git_Branch_terminal.git) 
   *(folder "my_repositories" in turn contains folders JSON/  TXT/  XML/)
   
> - Enter the local repository "Git_Branch_terminal" (cd Git_Branch_terminal)

> 1. На локальном репозитории сделать ветки для:
  - Postman
  ```
  git branch Postman
  ```
  - Jmeter
  ```
  git branch Jmeter
  ```
  - CheckLists 
  ```
  git branch CheckLists
  ```
  - Bag Reports 
  ```
  git branch Bag_Reports
  ```
  - SQL
  ```
  git branch SQL
  ```
  - Charles 
  ```
  git branch Charles
  ```
  - Mobile testing 
  ```
  git branch Mobile_testing
  ```
> 2. Запушить все ветки на внешний репозиторий 
  ```
  git push -u origin --all
  ```
> 3. В ветке Bag Reports сделать текстовый документ со структурой баг репорта 
  ```
  git checkout Bag_Reports --> cd .. --> cp TXT/bug_report.txt Git_Branch_terminal/
  ```
> 4. Запушить структуру багрепорта на внешний репозиторий
  ```
  cd Git_Branch_terminal/ --> git add . --> git commit -m "add bug_report" --> git push -u origin Bag_Reports
  ```
> 5. Вмержить ветку Bag Reports в Main 
  ```
  git checkout main -->  git merge Bag_Reports
  ```
> 6. Запушить main на внешний репозиторий. 
  ```
  git push
  ```
> 7. В ветке CheckLists набросать структуру чек листа. 
  ```
  git checkout CheckLists --> vim check_list_age.txt
  ```
**(Чек-лист тестирования поля "Возраст")**
| Проверка |Пример | Результат|
|-----------------------------------|-------------------------------|-------------------------------------------|
| Больше 18 лет| 25 | Успешная регистрация |
| Ровно 18 лет| 18| Успешная регистрация |
| Меньше 18 лет| 16|Ошибка: «Возраст должен быть 18 лет или выше»|
| **Дробные значения**|**-**|**-**|
| Через точку| 21.5| Успешная регистрация|
|Через запятую| 21,5| Успешная регистрация |
|**Пограничные значения**|**-**|**-**|		
|Граница слева от 18 | 17 |Ошибка: «Возраст должен быть 18 лет или выше»|
|Граница слева, дробное число | 17.999999999999999999 | Ошибка: «Возраст должен быть 18 лет или выше»
|Граница справа от 18* | 18.00000000000000001 | Успешная регистрация|
|Ноль / Один|**-**|**-**|		
|Ноль | 0 | Ошибка: «Возраст должен быть 18 лет или выше»|
|Пустое поле| - | Ошибка: «Поле обязательное для заполнения»|
|Единица | 1 | Ошибка: «Возраст должен быть 18 лет или выше»
|**Большие числа** |**-**|**-**|
|Поиск технологической границы | 999999999999999999999 | Ошибка: «Некорректное значение возраста»|
|Поиск тех. границы меньше нуля	| -999999999999999999999 | Ошибка: «Некорректное значение возраста»|
|**Нечисловые значения** |**-**|**-**|		
|Число, записанное как строка | Пять | Ошибка: «Введите число»|
|Точно не число | Тест | Ошибка: «Введите число»|
|Лидирующий ноль | 025 | Успешная регистрация, возраст распознал как 25|
|Пробел перед числом | _(пробел)_ 25 | Успешная регистрация, возраст распознал как 25|
|Пробел внутри числа | 2 _(пробел)_ 5 |	Ошибка: «Возраст должен быть 18 лет или выше»|
|До пробела больше 18 лет | 25 _(пробел)_ 6 | Успешная регистрация, возраст распознал как 25|
|После пробела текст | 25 _(пробел)_ тест | Успешная регистрация, возраст распознал как 25|
|До пробела текст | тест _(пробел)_ 25 | Успешная регистрация, возраст распознал как 25|
|Запись через е	| 1.2e+2 | Ошибка: «Введите число»|
|Boolean значение | TRUE | Ошибка: «Введите число»|
|Строка Infinity | Infinity | Ошибка: «Введите число»|
|Строка NaN | NaN | Ошибка: «Введите число»|

```
esc :wq
```
> 8. Запушить структуру на внешний репозиторий 
  ```
  git add . --> git commit -m "add checklist" --> git push -u origin CheckLists
  ```
> 9. На внешнем репозитории сделать Pull Request ветки CheckLists в main
  ```
  on the remote repository: "Compare & pull request"--> "Create pull request" --> "Merge pull repository" --> "Confirm merge"
  ```
> 10. Синхронизировать Внешнюю и Локальную ветки Main 
  ```
  git checkout main --> git pull
  ```
