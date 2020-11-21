# Определение скважины для разработки

## Постановка задачи

Для нефтедобывающей компании нужно решить, где бурить новую скважину.

Предоставлены пробы нефти в трёх регионах: в каждом 10 000 месторождений, где измерили качество нефти и объём её запасов. Требуется:
* построить модель машинного обучения, которая поможет определить регион, где добыча принесёт наибольшую прибыль
* проанализировать возможную прибыль и риски техникой *Bootstrap*

**Шаги для выбора локации:**
- в избранном регионе находятся месторождения, для каждого определяют значения признаков;
- строится модель и оценивается объём запасов;
- выбирается месторождения с самым высокими оценками значений;
- прибыль равна суммарной прибыли отобранных месторождений.

**Условия задачи:**
* для обучения модели использовать линейную регрессию
* при разведке региона исследуют 500 точек, из которых выбирают 200 лучших для расчёта прибыли
* бюджет на разработку скважин в регионе — 10 млрд рублей
* один баррель сырья приносит 450 рублей дохода. Доход с каждой единицы продукта составляет 450 тыс. рублей, поскольку объём указан в тысячах баррелей
* после оценки рисков нужно оставить лишь те регионы, в которых вероятность убытков меньше 2.5%. Среди них выбирают регион с наибольшей средней прибылью


## Описание данных

Данные предоставлены для 3 районов: 0, 1 и 2. Для каждого района предоставлены признаки:

* _id_ - идентификатор скважины
* _f0, f1, f2_ - характеристики (значимые признаки) 
* _product_ - объём запасов в скважине (тыс. баррелей)