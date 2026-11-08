# Anam's Bracelets

The storefront and JSON API are served by Django. SQLite stores the product catalog, orders, and order items. Use Django admin to manage products and update order statuses.

## Run locally

Open PowerShell in this folder and run:

```powershell
& "C:\Users\3 STAR\AppData\Local\Programs\Python\Python312\python.exe" -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
.venv\Scripts\python.exe manage.py migrate
.venv\Scripts\python.exe manage.py seed_products
.venv\Scripts\python.exe manage.py createsuperuser
.venv\Scripts\python.exe manage.py runserver
```

Open http://127.0.0.1:8000/ for the shop or http://127.0.0.1:8000/admin/ to manage products and orders.

Orders are cash-on-delivery requests; no card details or online payments are collected. Before public deployment, configure a strong `DJANGO_SECRET_KEY`, set `DJANGO_DEBUG=0`, configure `DJANGO_ALLOWED_HOSTS`, enable HTTPS, and use production-grade static-file hosting and a production database.
