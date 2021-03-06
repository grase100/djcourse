# Мова візуалізації


Візуалізація - це представлення інформації, даних, фактів у візуальній формі. Водночас, візуалізація є  мовою, в якій  використовуються геометричні об'єкти - точка, лінія, частина поверхні, або візуальні канали - колір, довжина, орієнтація, розмір. Фвктично - це продовження звичайної мови, тому що тексти - її частина.

Водночас, як і будь яка мова, її елементи можна комбінувати багатьма способами. Проте, не всі комбінації мають сенс. До того ж, різні типи даних вимагають різних способів їх представлення мовою візуалізації - для них потрібно використовувати різні способи візуального кодування. 

З одного боку може здатися, що це ускладнює задачу інформаційного дизайнера. Насправді, якщо знати мову візуалізації та правила, у який спосіб краще представляти ті чи інші дані, це сильно полегшує роботу - тому що обмежує кількість  варіантів

Отже, саме цим ми зараз і займемося: подивимося, які типи даних існують, і як їх кодувати за домомогою цієї мови у найбільш ефективний спосіб.

## Типи даних
Ми використаємо найпростішу схему класифікації. За нею, дані поділяються на три типи:
* Кількісні - все, що можна порахувати
* Впорядковані (якісні) дані, те що можна розташувати у якомусь порядку - дні тижня, градації шкали оцінювання (від "дуже погано" до "дуже добре" )
* Категорійні - невпорядковані якісні дані. Практично все, що не відноситься до перших двох типів - назви країн, назви з будь яких наборів, різноманітні типи, тощо


## Елементи мови. Мітки та канали

Мітки - це базові графічні елементи(найпростіші геометричні об'єкти)
* Точка
* Лінія
* Площина (на 2D поверхні)
* Об'ємне тіло (в 3D)
* ...

Канали - це спосіб, у який ми можемо показати наші позначки. Тобто, ми можемо контролювати як буде виглядати позначка, за допомогою таких візуальних каналів, як
* Позиція
* Розмір
* Форма
* Орієнтація
* Відтінок, насиченість, яскравість (кольору)
* ... 



## Послідовність дій
Отже, для візуалізації ваших даних, перше що необхідно зробити, це порахувати кількість змінних (наприклад, скільки колонок є у вашій таблиці з даними), та визначити для кожної із цих змінних, до якого типу даних вона відноситься: до кількісних, впорядкованих чи категорійних. Після цього, для кожної змінної ми можемо вибрати мітку та візуальний канал, який найкраще для неї підійде.





## Приклад 1, дані
Країна|Показник
---|---
Парагвай|3
Зімбабве|5
Мексика|6



## Приклад 1, можливе кодування
Змінна|Тип даних|Візуальні канали 
---|---|---
Країна|категорії|Орієнтація, Колір, Форма, Текстура, X(або Y)
Показник|кількісні|Орієнтація, Розмір, Значення, X(або Y) 




 
1. Форма + Значення (намалювати, виглядає, як головоломка)

![](https://www.targetprocess.com/content/uploads/2012/09/example1_shape_value.jpg)


2. Колір + Розмір кола(трохи краще, нагадати про площу, а не радіус) 
![](https://www.targetprocess.com/content/uploads/2012/09/example1_color_size.jpg)

3. Колір + Y (ще краще, але що робити з легендою?)
4. Y + X (майже ідеально, бо немає легенди. підписи на графіку значно краще легенди)
![](https://www.targetprocess.com/content/uploads/2015/07/example1_y.jpg)





### Складніший приклад

Тип задачі|Приоритет|Кількість зусиль, бали|Час, дні 
---|---|---|---
Характеристика|Обов'язково|	30|	40
Характеристика|Добре мати|	20|	40
Характеристика|Непогано мати|	15|	20
Помилка|Виправити негайно|	2|	2
Помилка|Виправити колись|	2|	8
Помилка|Виправити вчасно|	5|	12
Побажання користувача|	Обов'язково|	8|	10
Побажання користувача|	Непогано мати|	5|	7
Побажання користувача|	Добре мати|	8|	7


Більше 500 варіантів комбінацій, якщо використовувати всі візуальні канали. Я виберу лише ті, які вважаю прийнятними у цьому випадку:

Змінна|Тип даних|Візуальний канал
---|---|---
Тип задачі|категорійні|відтінок кольору
Приоритет|впорядковані|насиченість кольору
Кількість зусиль|кількісні|X
Час|кількісні|Y

![](https://www.targetprocess.com/content/uploads/2015/07/example_cycle_time.jpg)

(аналіз графіка)


Після наших прикладів, ви напевно вже зрозуміли, що не всі візуальні канали можна використовувати для всіх типів даних. Для початку,  давайте розіб'єм  всі візуальні канали на дві частини: ті які можна використовувати для кодування категорійних (у першому випадку), або кількісних(та впорядкованих) даних (у другому випадку)

![channels](https://www.targetprocess.com/content/uploads/2012/09/retinal_data.jpg)



### Канали для відповіді на питання "Що?" (категорійні дані)

* Форма
* Місце розташування
* Колір (відтінок)

### Канали для відповіді "Наскільки багато?" (кількісні), або наскільки сильно? (впорядковані)  
* Довжина (1D)
* Площа (2D)
* Об'єм (3D)
* Нахил
* Позиція
* Колір (Яскравість)
  
### Приклади
1. Усайн Болд
![](https://www.targetprocess.com/content/uploads/2015/07/ex_100m.jpg)


2. Графік типу "чупа-чупс"
![](http://texty.org.ua/action/file/download?file_guid=67996)

3. Результати олімпіади

![](https://www.targetprocess.com/content/uploads/2015/07/ex_medals.png)


4. New York, stop and frisk

![](https://static01.nyt.com/packages/images/newsgraphics/2012/0816-force/0815-force.png)


Сьогодні ми познайомилися з елементами мови візуалізації, про те що таке мітки(позначки), та візуальні канали.  Також ми поговорили про те, які типи даних існують, і які візуальні канали більше пасують для різних типів даних.
















