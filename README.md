## **Проект 7. Модель Прогнозирования Стоимости Жилья для Агентства Недвижимости**

## Оглавление
1. [Описание Проекта](README.md#описание-проекта)
2. [Краткая Информация о Данных](README.md#краткая-информация-о-даннык)
3. [Этапы Работы над Проектом](README.md#этапы-работы-над-проектом)
4. [Результат](README.md#результат)


### Описание Проекта

Разработать модель, которая позволила бы агентству недвижимости обойти конкурентов по скорости и качеству совершения сделок


:arrow_up:[to Table of Contents](README.md#оглавление)


### Краткая Информация о Данных

➔ **status** — sale status; \
➔ **private pool** and **PrivatePool** — availability of a private pool; \
➔ **propertyType** - property type; \
➔ **street** — property address; \
➔ **baths** — number of bathrooms; \
➔ **homeFacts** — property construction information (contains several types of information that affect property valuation); \
➔ **fireplace** — presence of a fireplace; \
➔ **city** — city; \
➔ **schools** — information about schools in the area; \
➔ **sqft** — square footage; \
➔ **zipcode** — postal code; \
➔ **beds** — number of bedrooms; \
➔ **state** — state; \
➔ **stories** — number of floors; \
➔ **mls-id** and **MlsId** — MLS (Multiple Listing Service) identifier; \
➔ **target** — the price of the real estate object (the target feature that needs to be predicted).

[Ссылка на данные](https://drive.google.com/file/d/11-ZNNIdcQ7TbT8Y0nsQ3Q0eiYQP__NIW/view)

:arrow_up:[to Table of Contents](README.md#оглавление)


### Этапы Работы над Проектом

1. Описательный Анализ Данных:
   - знакомство с данными

2. Преобразование Данных:
   - работа с пропусками и дубликатами
   - преобразование признаков:
      - status
      - private_pool
      - fireplace
      - and so on
   - создание признаков:
      - property age, property group
      - availability of fireplace, type of fireplace
      - availability of heating, type of heating, source of heat
      - availability of cooling, type of cooling, source of cool
      - and so on
   - кодировка признаков:
      - binary
      - label encoding

3. Разведывательный Анализ Данных:
   - Проверка на Мультиколлинеарность:
      - Spearman's Correlation для категориальных признаков
   - Визуализация Данных:
      - state
      - property group / type
      - and so on

4. Статистический Анализ Данных:
   - Проверка на Нормальность:
      - Shapiro-Wilk
      - Anderson-Darling
   - Проверка Равности Дисперсий:
      - Levene Test
      - Bartlett's Test
   - Статистические Тесты:
      - Kruskal-Wallis
      - Mann Whitney U-Test

5. Проектирование Признаков:
   - отбор признаков
      - Recursive Feature Elimination (RFE)
      - SelectKBest
   - шкалирование данных:
      - MinMax

6. Построение Модели
   - перебор гиперпараметров с помощью Optuna
   - обучение модели с помощью Linear Regression (and variations), Random Forest Regressor, Gradient Boosting Regressor
   - логирование параметров обучения
   - анализ модели


:arrow_up:[to Table of Contents](README.md#оглавление)


### Результат
В результате лучший результат показала модель Random Forest Regressor со стандартными числовыми признаками (не шкалированными) и бинарными:

**Mean Absolute Error (MAE) = ** \
**R-Squared = **


:arrow_up:[to Table of Contents](README.md#оглавление)
