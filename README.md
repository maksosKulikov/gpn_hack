### DS в нефтяном ретейле
Краткое описание моего решения:
1) Предобработка данных (файл data_preprocess.ipynb). Данные содержат множество орфографических ошибок. Избавляюсь от них с помощью yandexgpt. Сырые и предобработанные данные переношу в csv файл.
2) Обработка данных и обучение модели (файл solution.ipynb). Из данных я удаляю всё, кроме кириллицы, добавляю биграммы и триграммы, привожу слова к нормальной форме, удаляю стоп-слова. После этого обучаю LDA и BERTopic. BERTopic дал лучшее решение. Каждой тематике с помощью yandexgpt присуждаю название. Для каждого объекта данных определяю тематику и добавляю номер тематики и её название в csv файл.

По итогу мы имеем в csv файле мы имеем 4 признака - сырые данные, предобработанные данные (в которых исправлены орфографические ошибки), номер тематики для каждого объекта, название тематики для каждого объекта.
Моё решение хорошо тем, что даёт много информации для дальнейшего анализа. Можно достать из "csv" файла какую-либо тематику и подробно разобраться в том какая проблемма есть у компании или какие преимущества люди видят в ней.

Обученная модель - https://disk.yandex.ru/d/PPqQ4DYHTM7ZPQ

Что я бы ещё сделал, но не успел: Нужна работа с результатами, так как некоторые тематики схожи между собой. Нужна более детальная настройка BERTopic и больший анализ результатов.
Для предобработки текста попробывал бы использовать другие gpt и сравнить качество результатов.
Не успел сделать pipeline для новых данных: необходимо принимать новый текст, добавлять его в "csv" файл, предобработать его с помощью yandexgpt, добавить предобработанный текст в csv файл. Проделать ту обработку над данными, которые прописаны в файле solution.ipynb, загрузить модель bertopic, сделать предсказание для обработанных данных и добавить номер тематики и название тематики в таблицу csv.
