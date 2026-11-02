# WordPress E-Commerce Starter Platform


---

## 🛠 Технологический стек & Архитектура
* **Инфраструктура:** Docker Compose (контейнеры MySQL 8.0, WordPress Latest, phpMyAdmin)
* **Ядро темы:** Блочная тема (Full Site Editing), сгенерированная на базе генератора FSE
* **Кастомный функционал:** Разделение на Core-плагин (PHP/Хуки) и Blocks-плагин (React/JSX блоки для Gutenberg)


---

## 📁 Структура проекта

```text
startProject/
├── .srv/                     # Системные файлы Docker (база данных и логи) [В ИГНОРЕ]
│   └── custom.ini            # Кастомная конфигурация PHP (Memory Limit, Upload Max Size)
├── mu-plugins/               # Must-Use плагины (неотключаемый критический функционал)
│   
├── plugins/                  # Кастомные и системные плагины проекта
│   ├── core-game-store/      # Главный плагин функционала (Регистрация Custom Post Types, Ajax)
│   └── blocks-game-store/    # Плагин кастомных React-блоков для Gutenberg (Шапка, Hero, и т.д.)
│       ├── src/              # Исходный код блоков на React (JSX)
│       └── build/            # Скомпилированный код блоков, готовый для WP [В ИГНОРЕ]
├── themes/
│   └── custom/           # Кастомная блочная FSE тема (Templates, Parts, Global Styles)

├── docker-compose.yml        # Манифест инфраструктуры Docker
├── .gitignore                # Правила исключения мусора из репозитория
└── README.md                 # Документация проекта
```

---

## 🚀 Быстрый старт (Первый запуск)

### Требования к системе:
1. Установленный **Docker Desktop** (на Windows убедитесь, что включен WSL2 бекенд для высокой скорости работы).
2. Установленный **Node.js** (для сборки React-блоков).
3. Установленный **Git**.

### Пошаговый запуск:
1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com
   cd startProject
   ```
2. Запустите Docker-контейнеры:
   ```bash
   docker-compose up -d
   ```
3. Установите зависимости и запустите компилятор блоков (в папке плагина):
   ```bash
   cd plugins/blocks-game-store
   npm install
   npm run start
   ```
4. Откройте сайт в браузере:
   * **WordPress локально:** `http://localhost:8000`
   * **phpMyAdmin:** `http://localhost:8181` (Логин: `root`, Пароль: `wordpress_secure_root`)

---

## 📖 Полезные ресурсы
* 📺 **Видео-курс по разработке проекта:** [Смотреть первую часть на YouTube](https://www.youtube.com/watch?v=c8nob2rQ9To)
* 🛠 **FSE Генератор тем:** [Block Theme Generator](https://fullsiteediting.com/block-theme-generator/)
