HR Test Application
===================

Задание
-------
Реализовать интерфейс просмотра списка вакансий с возможностью фильтра по отделам и языку. Каждая вакансия определена
следующими свойствами: отдел, название вакансии и ее описание. Отдел является отдельным объектом, представлен
идентификатором и названием. При этом название вакансии и её описание могут быть переведены на несколько языков
(ru, fr, it, ...). Интерфейс должен содержать фильтр по отделу и языку, а также список подходящих вакансий. Если нет
перевода на выбранный язык, то вакансия отображается на языке по умолчанию(en).

Для реализации использовать Zend Framework 2.x, Doctrine 2 и composer. Результат необходимо выложить на Github.com.

Реализация
----------

В наличии:

- Формы добавления/редактирования всех основных объектов: Язык, Департамент, Вакансия, Перевод. Формы проходят валидацию на
допустимые значения, в случае неудачи запись в БД не производится, пользователю показываются какие поля заполнены неправильно.

- Интерфейсы просмотра списков объектов, все те же языки, департаменты, вакансии, развернутая вакансия со списком переводов
на отдельной странице.

- Формы удаления объектов.

- Фильтрация вакансий.

- Приложение сделано на базе Zend Skeleton Application

- В качестве слоя доступа к данным используется Doctrine 2

Branch: master. SQL dumps in "data/sql-dump/v1"

Другой вариант развития событий
-------------------------------

Название и описание вакансии на языке по умолчанию в ветке "master" содержится в самом объекте вакансии (i.e. в таблице вакансий).
Имеет смысл все описания вакансий, в том числе и на языке по умолчанию, вынести в таблицу переводов (обект перевода).

Именно это и начато в ветке: alt-translation, но, к сожалению пока до конца не закончено, а именно:
- алогритм выборки работает (SQL запроc) и View Helper переделаны под данную модель
- Создание вакансии сразу создает и сохраняет объект перевода на базовом языке

TODO:
- Одновременно с редактированием заявки сохранять отредактированный перевод на языке по умолчанию
- Убрать дублирование (объект вакансии и перевода). Вакансия по прежнему содержит заголовок и описание.

Branch: alt-translation. SQL dumps in "data/sql-dump/v1"

Комментарии к коду лучше смотреть в ветке alt-translation, там их больше