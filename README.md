## Проект e-commerce. Анализ продаж
Руководство интернет-магазина предоставило несколько файлов с выгрузкой информации о продажах за период. Необходимо проанализировать совершенные покупки и ответить на следующие вопросы:
1.	Сколько пользователей, которые совершили покупку только один раз?  
2.	Сколько заказов в месяц в среднем не доставляется по разным причинам (вывести детализацию по причинам)?
3.	По каждому товару определить, в какой день недели товар чаще всего покупается. 
4.	Сколько у каждого из пользователей в среднем покупок в неделю (по месяцам)? 
5.	Когорты  
5.1.	Когортный анализ пользователей.  
5.2.	В период с января по декабрь выявите когорту с самым высоким retention на 3-й месяц.   
6.	Построить RFM-сегментацию пользователей, чтобы качественно оценить свою аудиторию. 


### Файлы:
1)	olist_customers_datase.csv — таблица с уникальными идентификаторами пользователей
	customer_id — позаказный идентификатор пользователя
	customer_unique_id —  уникальный идентификатор пользователя  (аналог номера паспорта)
	customer_zip_code_prefix —  почтовый индекс пользователя
	customer_city —  город доставки пользователя
	customer_state —  штат доставки пользователя

2)	olist_orders_dataset.csv —  таблица заказов
	order_id —  уникальный идентификатор заказа (номер чека)
	customer_id —  позаказный идентификатор пользователя
	order_status —  статус заказа
	order_purchase_timestamp —  время создания заказа
	order_approved_at —  время подтверждения оплаты заказа
	order_delivered_carrier_date —  время передачи заказа в логистическую службу
	order_delivered_customer_date —  время доставки заказа
	order_estimated_delivery_date —  обещанная дата доставки

<details>
<summary>3) olist_order_items_dataset.csv —  товарные позиции, входящие в заказы</summary>

| Поле               | Значение                                         |
|-------------------:|--------------------------------------------------|
| order_id           |уникальный идентификатор заказа (номер чека)      |
| order_item_id      |идентификатор товара внутри одного заказа         |
| product_id         |ид товара (аналог штрихкода)                      |
| seller_id          |ид производителя товара                           |
|shipping_limit_date |максимальная дата доставки продавцом для передачи заказа партнеру по логистике|
| price              |цена за единицу товара                            |
| freight_value      |вес товара                                        |
</details>

<details>
<summary> Уникальные статусы заказов в таблице olist_orders_dataset:</summary>

| Rank | Status                                   |
|-----:|------------------------------------------|
|     1| created —  создан                        |
|     2| approved —  подтверждён                  |
|     3| invoiced —  выставлен счёт               |
|     4| processing —  в процессе сборки заказа   |
|     5| shipped —  отгружен со склада            |
|     6| delivered —  доставлен пользователю      |
|     7| unavailable —  недоступен                | 
</details>

### План:
1)	Выгрузка и изучение имеющихся данных. 
2)	Выполнение операций с данными в рамках заданий проекта.

