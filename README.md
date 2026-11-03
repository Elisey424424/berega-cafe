# Сайт кафе «Берега»

Статический сайт: один файл `index.html` (стили, скрипты и фотографии внутри). Сборка не нужна.
Страницы переключаются адресом после решётки: `#menu`, `#reviews`, `#menu-card`, `#location`, поэтому дополнительных настроек сервера не требуется.

## Публикация на Vercel через GitHub

1. Зарегистрируйтесь на github.com (если нет аккаунта).
2. Нажмите **+ → New repository**, назовите `berega-cafe`, оставьте Public или выберите Private, нажмите **Create repository**.
3. В пустом репозитории нажмите **uploading an existing file**, перетащите `index.html`, `vercel.json` и `README.md`, затем **Commit changes**.
4. Зайдите на vercel.com, нажмите **Sign Up → Continue with GitHub** и разрешите доступ.
5. Нажмите **Add New… → Project**, найдите `berega-cafe`, нажмите **Import**.
6. В настройках оставьте Framework Preset: **Other**. Build Command и Output Directory не заполняйте. Нажмите **Deploy**.
7. Через 20–60 секунд Vercel покажет адрес вида `https://berega-cafe-xxxx.vercel.app`. Это и есть публичная HTTPS-ссылка.
8. Адрес можно сократить: **Settings → Domains → Edit** у адреса `.vercel.app` (если имя свободно).

Любое изменение файла в GitHub автоматически обновляет сайт.

### Быстрый вариант без GitHub
В папке проекта выполните `npx vercel` и ответьте на вопросы, затем `npx vercel --prod`.

## Свой домен (например, berega-cafe.ru)

1. Проверьте, свободен ли домен, у регистратора (reg.ru, nic.ru, reg.com и др.) и купите его.
2. В Vercel: **Project → Settings → Domains → Add**, введите `berega-cafe.ru` (и `www.berega-cafe.ru`).
3. Vercel покажет нужные DNS-записи. Обычно это запись **A** для `@` со значением `76.76.21.21` и запись **CNAME** для `www` на `cname.vercel-dns.com`. Используйте значения, которые показывает ваша панель Vercel.
4. Добавьте их в DNS-настройках у регистратора. Изменения применяются от нескольких минут до нескольких часов.
5. HTTPS-сертификат Vercel выпустит автоматически.

## Что редактировать
- Ссылка на отзывы: переменная `REVIEW_URL` в скрипте.
- Меню и цены: массив `MENU`.
- Отзывы (когда будут): массив `REVIEWS`: `{name, rating, text, date}`.
