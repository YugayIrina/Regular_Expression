Домашнее задание к лекции 5. «Regular expressions»
Иногда при знакомстве мы записываем контакты в адресную книгу кое-как, с мыслью, что когда-нибудь потом всё обязательно поправим. Копируем данные из интернета или из смс. Добавляем людей в разных мессенджерах. В результате получается адресная книга, в которой невозможно кого-то найти: мешает множество дублей и разная запись одних и тех же имен.

Кейс основан на реальных данных из https://www.nalog.ru/opendata/, https://www.minfin.ru/ru/opendata/.

Ваша задача: починить адресную книгу, используя регулярные выражения.
Структура данных будет всегда:
lastname,firstname,surname,organization,position,phone,email
Предполагается, что телефон и e-mail у человека может быть только один.

Необходимо:

Поместить Фамилию, Имя и Отчество человека в поля lastname, firstname и surname соответственно. В записной книжке изначально может быть Ф + ИО, ФИО, а может быть сразу правильно: Ф+И+О.
Привести все телефоны в формат +7(999)999-99-99. Если есть добавочный номер, формат будет такой: +7(999)999-99-99 доб.9999.
Объединить все дублирующиеся записи о человеке в одну.
from pprint import pprint
## Читаем адресную книгу в формате CSV в список contacts_list:
import csv
with open("phonebook_raw.csv") as f:
  rows = csv.reader(f, delimiter=",")
  contacts_list = list(rows)
pprint(contacts_list)

## 1. Выполните пункты 1-3 задания.
## Ваш код

## 2. Сохраните получившиеся данные в другой файл.
## Код для записи файла в формате CSV:
with open("phonebook.csv", "w") as f:
  datawriter = csv.writer(f, delimiter=',')
  
## Вместо contacts_list подставьте свой список:
  datawriter.writerows(contacts_list)
Домашнее задание сдавайте ссылкой на репозиторий BitBucket или GitHub.

Мы не сможем проверить, если вы пришлёте:

архивы,
скриншоты кода,
теоретический рассказ о возникших проблемах.
