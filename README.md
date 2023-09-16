# A-B-test

Ваша задача — провести оценку результатов A/B-теста. В вашем распоряжении есть датасет с действиями пользователей, техническое задание и несколько вспомогательных датасетов.

Цель проекта: на основании предоставленных датасетов с действиями пользователей оценить корректность проведения А/В теста и проанализировать его результаты.

Оцените корректность проведения теста. Проверьте:
- Соответствие данных требованиям технического задания. В случае нарушения требований оцените, насколько существенно негативное влияние на результаты теста. При проверке условий технического задания и фильтрации данных, контролируйте количество уникальных пользователей, принимающих участие в тесте – это поможет детальнее изучить влияние каждого условия на аудиторию теста.
- Время проведения теста. Убедитесь, что оно не совпадает с маркетинговыми и другими активностями.
- Аудиторию теста. Удостоверьтесь, что нет пересечений с конкурирующим тестом и нет пользователей, участвующих в двух группах теста одновременно. Проверьте равномерность распределения пользователей по группам и правильность их формирования.
- Проанализируйте результаты теста

Библиотеки: pandas, matplotlib, plotly, seaborn, numpy, math, scipy

Общий вывод

- Привлеченные клиенты больше распределялись в группу А, пиковые значения на привлечение клиентов приходятся для групп А и В на 21, 14, 7 декабря. Разница между этими датами составляет 7 дней. Наибольшее привлечение клиентов было в понедельник, суббота и воскресение следующие по количество привлеченных клиентов. На неделе привлечение клиентов было менее активное. В группу А больше клиентов было распределено чем в группу В.
- В тест recommender_system_test было определено 6 701 пользователь, из них в группе А - 3 824 человека, а в группе В - 2 877 человек. Соотношение количества участников группы А к группе В - 1.33. При исключении событий с лайфтамом больше 14 дней (анализируемый период) получилось, что в тесте участвуют 3675 пользователей, из них в группе А - 2747 пользователя, а в группе В - 928. Таким образом, требование технического задания (ожидаемое количество участников 6000) не соблюдено.
- В тестировани принимали участие только новые пользователи. Доля новых пользователей в из Европы - 15%. Требование соблюдено.
1602 участника приняли участие сразу в двух тестах. Количество пользователей, которые попали в оба теста одновременно и были распределены по группам А - 482. Количество пользователей, которые попали в оба теста одновременно и были распределены по группам В - 344. Соотношение количества участников попавших в оба теста группы А к группе В - 1.33. Различия в соотношении групп можно считать равными. Поэтому можно предположить, что влияние теста 2 скажется на обеих группах одинаково.
- Не обнаружено пересечение пользователей теста recommender_system_test, которые попали бы и в группу А и в группу В одновременно.
В тестировани принимали участие только новые пользователи. Доля новых пользователей в из Европы - 15%. Требование соблюдено.
- При анализе даты окончания проведения тестирования выявлено, что тест был остановлен 30.12.2020, вместо планируемого 04.01.2021 г. Таким образом, результаты теста являются не полными, т.к. по условия ТЗ мы должны оценить эффект от мероприятия по истечение 14 дней с момента регистрации.
После исключения событий, которые произошли в течение 14 дней количество участников тестирования составило 3 675 пользователей. Группа А превосходит группу В по количеству пользователей в 3 раза. Количество событий, которые проводились участниками теста в течение 14 дней - 24070
Даты проведения теста (с 7 по 30 декабря) пересекаются с мероприятием Christmas&New Year Promo, которое проходит в регионах EU, N.America с 25 декабря 2020 по 3 января 2021 гг. Пересечения составили с 25 по 30 декабря, но особого всплеска в этот период на графиках не наблюдется.

Исследовательский анализ:
- Группа А активнее группы В взаимодействует с сайтом.
- Максимум у обоих групп это 6 событий на пользователя.
- Имеются пользователи, которые совершают 18 и более событий, но это уже редкость.
- У группы А в среднем около 7 событий на 1 пользователя, когда у группы В 5,5 событий на 1 одного пользователя.
- Пик активности у группы А приходится на 21 декабря 2020 г., у группы В аналогично.

Анализ воронки продаж:
- Больше всего пользователей "теряется" после регистрации, в группе А и В, при этом в группе В % доходимости клиентов до события "просмотр карточек товаров" ниже, чем у группы А.
- С события "просмотр карточек товаров" до события "просмотр корзины" доходит 46% польщователей группы А и 49% группы В.
- Конверсия пользователей из события "просмотр корзины" в "покупку" у группы А выше и составляет 106%, такой показатель можно объяснить возможным наличием ускоренной покупки прямо из просмотра карточки товаров. У группы В аналогичный показатель составляет 100,4%, что меньше на 5,6% по сравнению с группой А.
- Средняя сумма покупок у группы А на протяжении всего теста - 23,22 доллара, при этом медианное значение суммы покупки - 4,99 доллара. Из-за наличия аномального значения в размере 499,99 долларов среднее значение значительно превосходит мелианное.
- У группы В аналогичный показатель как и у группы А - средняя сумма покупок - 23,22 доллара, при этом медианное значение суммы покупки - 4,99 доллара. Из-за наличия аномального значения в размере 499,99 долларов среднее значение значительно превосходит медианное.
- При анализе среднего количества событий в день на пользователя наибольшую активность провляет группа А по сравнению с группой В практически на всем протяжении теста. Это можно объяснить тем, что большинство людей заранее подходят к выбору подарков на новый год, чтобы подгадать с временем доставки и не рисковать, что подарок может не успеть прийти к Новому году.

Группа А начиная с 13 декабря 2020 года. увеличила свою среднюю активность с 2 до 2,3 событий в день и на протяжении всего анализируемого периода сохраняла этот показатель.

У группы В наблюдается пик активности в период с 16 по 17 декабря 2020 г.. Начиная с 16 декабря у группы В отмечается ежедневное падение среднего количества событий на пользователя с 17 декабря.

Конверсия из регистрации в покупку у группы В до 13 декабря выше, так же отмечался всплеск 16 декабря. Начиная с 17 декабря конверсия пользователей в покупку у группы А выше.

В целом на протяжении всего анализируемого периода группа А делала покупки на бОльшую сумму, исключения составляет 13 декабря 2020 г., когда группа В купила на большую сумму по сравнению с группой А.

Всплеск активности покупок так же наблюдается 21 декабря 2020 г., ранее мы определили, что в это дату было наибольшее число активности в двух группах. Второй всплеск активности у группы В наблюдается 27 декабря 2020 г. после запуска маркетинговой акции. Не исключено, что она в совокупности с проводимым тестом могла сказаться на активности пользователей и смотивировала покупать более дорогие товары.

У группы А наблюдается 3 всплекса активности покупок на большие суммы - 16 декабря, 21 декабря, 24 декабря. Причем начиная с 24 декабря наблюдался ежедневный спад по суммам покупок пользователями. Можно предположить, что действительно маркетинговая акция в совокупности с новой рекомендательной системой могли сказаться на результатах группы В, но это всего лишь предположение, т.к. слишком мал период для анализа.

Покупки на 499,99 долларов довольно редки, не смотря на это группа А демонстрирует наибольшую частоту таких чеков, по сравнению с группой В.

Интерпретация результатов А/В теста:

Считаю проведение теста некорректным в связи со следующими обнаруженными ошибками:
- в связи с неоднородным заполнением выборок A и B на всем протяжении времени,
- имеются пользователи, которые участвовали одновременно в двух тестах, хоть их и распределение условно равномерно между группами, но не стоит исключать и влияние этого теста на результаты,
- имеется пересечение с маркетинговым мероприятием и проведение теста совпало с предпраздничным периодом, который в свою очередь в любом случае мотивирует клиентов делать покупки,
- тест остановлен ранее заявленного времени (30 декабря 2020), а это в свою очередь повлекло сокращения пользователей в тесте, в связи с необходимостью отследить даты регистрации в тесте и отобрать только тех, кто смог совершить действия в течение 14 дней,
- не все набранные клиенты смогли осуществить целевые действия во время теста, в связи с раньшим окончанием наблюдений.
- Если доверять результатам анализа, то новая рекомендательная система хуже старой. Это показывают и графики активности, конверсии и покупок.

Конверсия из регистрации в покупку у группы В была выше только до 13 декабря выше и отмечался всплеск 16 декабря. Начиная с 17 декабря конверсия пользователей в покупку у группы А выше.

Статистическая проверка

При проверке статистическим методом разницу долей группы А и В по 4 событиям видно, что по всем четырем событиям отсутствует отличие посещений на 10% в пользу группы В.

Уже при исследовании было видно, что контрольная группа активнее и больше, чем тестовая, причем не только по целевым показателям конверсии, но в том числе и по суммам покупок.

Рекомендации:

Проведенный тест не показал никаких положительных результатов, таким образом, можно предположить, что новая новая платёжная воронка не улучшила показатели, а наоборот ухудшила.

Но связи с довольно грубыми нарушениями при проведении теста результат анализа может быть не корректным и, возможно, эффект есть от внедрения, поэтому рекомендуется повторить тест с учетом всех предыдущих ошибок и с полным соответствием ТЗ. После проведения повторного тестирования необходимо снова проанализировать результаты.
