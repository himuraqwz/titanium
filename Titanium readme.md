# 🏋️ Titanium — Fitness Club Management System

> Full-featured web application for managing a fitness club built with Laravel 11

![PHP](https://img.shields.io/badge/PHP-8.2-777BB4?logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-11-FF2D20?logo=laravel&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?logo=mysql&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

<!-- 
📸 СКРИНШОТЫ — замени плейсхолдеры на реальные скриншоты:
Положи скрины в папку /screenshots/ в корне репозитория
-->

![Dashboard Preview](screenshots/dashboard.png)

---

## 📋 О проекте

**Titanium** — автоматизированная информационная система для управления фитнес-клубом. Система позволяет клиентам самостоятельно покупать абонементы, записываться на тренировки и отслеживать посещения. Администраторы и тренеры управляют расписанием, контролируют статистику и работают с клиентской базой.

Проект построен на чистой архитектуре Laravel — без готовых админ-панелей, с кастомным UI в тёмном стиле.

---

## ✨ Функционал

### 👤 Клиент
- Регистрация и авторизация
- Личный кабинет с профилем
- Просмотр и покупка абонементов
- Заморозка абонемента
- Просмотр расписания тренировок
- Запись на тренировку
- История посещений и платежей

### 🔧 Администратор
- Управление клиентами (CRUD)
- Управление абонементами (CRUD)
- Управление расписанием (CRUD)
- Дашборд со статистикой
- Просмотр посещаемости и отчёты

### 🏃 Тренер
- Просмотр своего расписания
- Отметка посещений клиентов

---

## 🛠 Технологии

| Категория | Технологии |
|-----------|-----------|
| **Backend** | PHP 8.2, Laravel 11, Eloquent ORM |
| **База данных** | MySQL 8.0, миграции, нормализация |
| **Frontend** | Blade, HTML5, CSS3, JavaScript |
| **Архитектура** | MVC, Middleware, Policy/Gate, Form Request |
| **Инструменты** | Composer, Git, PhpStorm, XAMPP |

---

## 🗄 База данных

Реляционная БД из **8 нормализованных таблиц** с внешними ключами и индексами:

- `users` — пользователи с ролями (client / admin / trainer)
- `profiles` — расширенные профили
- `memberships` — типы абонементов
- `user_memberships` — купленные абонементы (статус, заморозка)
- `payments` — история платежей
- `trainings` — виды тренировок
- `schedules` — расписание занятий
- `bookings` — записи на тренировки

---

## 📸 Скриншоты

<!-- Замени на свои скриншоты -->

| Дашборд клиента | Покупка абонемента |
|:---:|:---:|
| ![Client Dashboard](screenshots/client-dashboard.png) | ![Memberships](screenshots/memberships.png) |

| Расписание | Админ-панель |
|:---:|:---:|
| ![Schedule](screenshots/schedule.png) | ![Admin](screenshots/admin-dashboard.png) |

---

## 🚀 Установка и запуск

```bash
# Клонировать репозиторий
git clone https://github.com/himuraqwz/titanium.git
cd titanium

# Установить зависимости
composer install
npm install

# Настроить окружение
cp .env.example .env
php artisan key:generate

# Настроить БД в .env
# DB_DATABASE=titanium_db
# DB_USERNAME=root
# DB_PASSWORD=

# Миграции и сидер
php artisan migrate --seed

# Запуск
php artisan serve
```

Открой `http://127.0.0.1:8000`

---

## 👤 Тестовые аккаунты

| Роль | Email | Пароль |
|------|-------|--------|
| Админ | admin@titanium.ru | admin123 |
| Клиент | client@titanium.ru | client123 |
| Тренер | trainer@titanium.ru | trainer123 |

---

## 📁 Структура проекта

```
titanium/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── Admin/        # Контроллеры админки
│   │   │   ├── Client/       # Контроллеры клиента
│   │   │   └── Auth/         # Аутентификация
│   │   ├── Middleware/        # RoleMiddleware
│   │   └── Requests/         # Form Request валидация
│   ├── Models/                # Eloquent модели
│   └── Policies/             # Policy для авторизации
├── database/
│   ├── migrations/            # 8 миграций
│   └── seeders/              # Тестовые данные
├── resources/views/
│   ├── admin/                # Views админки
│   ├── client/               # Views клиента
│   └── layouts/              # Layouts
└── public/css/               # Стили (DDX dark theme)
```

---

## 📄 Лицензия

MIT License — свободное использование.

---

**Автор:** [Виталий Кашуба](https://github.com/himuraqwz)
