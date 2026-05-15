---
## Front matter
lang: ru-RU
title: Индивидуальный проект. Этап 5
subtitle: Добавление записей о персональных проектах и публикация новых материалов на персональном сайте
author:
  - Игнатенко Д. Б.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 15 мая 2026

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
mainfont: Times New Roman
sansfont: Arial
monofont: Courier New
header-includes:
  - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

- Игнатенко Денис Беньяминович
- Студент группы НПИбд-01-25
- Российский университет дружбы народов
- [1032252476@rudn.ru](mailto:1032252476@rudn.ru)

:::
::: {.column width="30%"}

![](./image/photo.jpg)

:::
::::::::::::::

# Цель работы

Обновить персональный сайт, добавив запись о персональном проекте, а также опубликовать пост по прошедшей неделе и тематический материал о языках научного программирования.

# Задание

- Создать запись для персонального проекта
- Создать пост по прошедшей неделе
- Создать тематический пост `Языки научного программирования`
- Проверить отображение материалов на сайте
- Подготовить изменения к публикации

# Выполнение проекта

## Добавление персонального проекта

Создаю новую запись проекта в `content/projects/personal-website-rudn/index.md` и описываю назначение персонального сайта.

![Создание записи проекта](image/1.png){#fig:001 width=60%}

![Заполнение записи проекта](image/2.png){#fig:002 width=60%}

## Создание weekly post

Добавляю weekly post о концерте 4 мая 2026 года в главном корпусе РУДН.

![Создание weekly post](image/3.png){#fig:003 width=60%}

![Заполнение weekly post](image/4.png){#fig:004 width=60%}

## Создание тематического post

Создаю пост `Языки научного программирования` и заполняю его материалом о `Python`, `R`, `Julia`, `MATLAB` и `Fortran`.

![Создание тематического post](image/5.png){#fig:005 width=60%}

![Заполнение тематического post](image/6.png){#fig:006 width=60%}

## Обновление раздела Projects

Корректирую текст страницы `content/projects/_index.md`, чтобы раздел был ориентирован на мои реальные проекты.

![Обновление страницы Projects](image/7.png){#fig:007 width=60%}

## Проверка на сайте

Запускаю `hugo server` и проверяю отображение новых материалов в браузере.

![Запуск hugo server](image/8.png){#fig:008 width=55%}

![Проект на сайте](image/9.png){#fig:009 width=55%}

![Weekly post на сайте](image/10.png){#fig:010 width=55%}

![Тематический post на сайте](image/11.png){#fig:011 width=55%}

![Итоговая проверка новых материалов](image/12.png){#fig:012 width=55%}

## Публикация

Подготавливаю изменения к публикации через Git:

```bash
git add .
git commit -m "stage 5: add project and posts"
git push
```

# Выводы

- На сайт добавлена запись о персональном проекте
- Созданы два новых поста
- Отображение материалов проверено локально
- Изменения подготовлены к публикации через GitHub Pages
