# goit-rdb-hw-04
**Виконавець:** Мазуренко Микола

## Датасет
**Olist Brazilian E-commerce Public Dataset**

Офіційне джерело: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

Використано повний багатотабличний Olist dataset без додаткового семплювання. Він містить приблизно 100 тисяч замовлень за 2016-2018 роки. Точні row counts усіх використаних таблиць notebook показує у smoke-test.

## Отримання файлів
Notebook завантажує dataset через:

```python
dataset_dir = kagglehub.dataset_download('olistbr/brazilian-ecommerce')
```

Потрібні CSV знаходяться рекурсивно за назвою файлу, тому код не залежить від внутрішньої структури Kaggle cache.

## Використані таблиці
Raw: `olist_customers_raw`, `olist_orders_raw`, `olist_order_items_raw`, `olist_products_raw`, `olist_sellers_raw`, `olist_order_reviews_raw`.

Typed: `olist_customers`, `olist_orders`, `olist_order_items`, `olist_products`, `olist_sellers`, `olist_order_reviews`.

Додаткові: `olist_customer_dim`, `customer_segments`, `seller_score`, `seller_alerts`.

`olist_order_reviews` використовує технічний `review_row_id` як primary key. Джерельний `review_id` не використовується як безумовний єдиний PK.

## Запуск
1. Відкрийте `notebooks/HW_Topic_4_Olist_UA.ipynb` у Google Colab.
2. За потреби використайте Python 3.12 для сумісності з `pgserver`.
3. Виконайте `Runtime -> Restart session -> Run all`.