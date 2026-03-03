# Next.js Dashboard Tutorial Notes

## Розділ 1. Початок роботи

### 1. Встановлення pnpm
Встановила pnpm глобально через npm.

Команда:
npm install -g pnpm

У консолі відобразилось повідомлення:
- changed 1 package in 3s  
- 1 package is looking for funding  

Помилок не було, встановлення пройшло успішно.
![Install pnpm](./screenshots/photo_2026-03-02_16-06-13.jpg)


### 2. Створення проєкту
Створила проєкт через create-next-app з прикладом dashboard.

Команда:
npx create-next-app@latest nextjs-dashboard --example "https://github.com/vercel/next-learn/tree/main/dashboard/starter-example" --use-pnpm


Під час створення:
- було встановлено 202 пакети
- автоматично ініціалізовано Git репозиторій
- згенеровано route types
- використовується Next.js 16.0.10

Процес завершився повідомленням:
`Success! Created nextjs-dashboard`

![Create app](./screenshots/photo_2026-03-02_16-35-14.jpg)


### 3. Запуск dev-сервера
Перейшла в папку проєкту:
cd nextjs-dashboard

Виконала:
pnpm dev

Сервер запустився успішно:
- Next.js 16.0.10 (Turbopack)
- Local: http://localhost:3000
- Ready in 874ms

У консолі відображаються HTTP-запити:
- GET / 200
- GET /login 404

Це означає, що головна сторінка працює, а маршрут `/login` поки що не знайдений.

![Dev server](./screenshots/photo_2026-03-02_16-06-19.jpg)

### 4. Перевірка роботи в браузері
Відкрила http://localhost:3000 у браузері.

Головна сторінка відобразилась коректно.

![Browser view](./screenshots/photo_2026-03-02_16-05-57.jpg)

## Розділ 2. CSS-стилізація

### 1. Додавання глобальних стилів

Перейшла до файлу:

`/app/layout.tsx`

І додала імпорт глобальних стилів.
Тепер головна сторінка відображається зі стилями.

![Global styles](./screenshots/photo_2026-03-02_20-28-12.jpg)

### 2. Використання Tailwind у page.tsx

У файлі `/app/page.tsx` вже використовуються класи Tailwind:

- flex
- min-h-screen
- p-6
- bg-blue-500
- rounded-lg

Це означає, що стилізація відбувається без окремих CSS-файлів для компонентів.

### 3. Додавання власного Tailwind-елемента

Я додала перед елементом `<p>` у `/app/page.tsx` наступний код:

```jsx
<div
  className="relative w-0 h-0 border-l-[15px] border-r-[15px] border-b-[26px] border-l-transparent border-r-transparent border-b-black"
/>
```

Після збереження змін на сторінці з’явився чорний трикутник.
Це приклад створення фігури лише за допомогою Tailwind-класів.

![Tailwind triangle](./screenshots/photo_2026-03-02_20-28-17.jpg)


## Розділ 3. Оптимізація шрифтів та зображень

### 1. Додавання основного шрифту

У папці `/app/ui` створила новий файл:

`fonts.ts`

Імпортувала шрифт Inter з модуля `next/font/google` та вказала підмножину `latin`.

### 2. Додавання додаткового шрифту

Додала шрифт Lusitana з вагами 400 і 700 у fonts.ts.

### 3. Додавання зображень через next/image

Імпортувала компонент Image у /app/page.tsx:

```jsx
import Image from 'next/image';
```

Додала зображення для desktop та mobile

Головна сторінка відобразилась коректно.

![Browser view](./screenshots/photo_2026-03-03_11-35-47.jpg)