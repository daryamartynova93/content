---
title: "`alertdialog`"
description: "Роль, которая нужна для диалогового окна с важной информацией."
authors:
  - agarkov
related:
  - a11y/aria-roles
  - a11y/role-dialog
  - a11y/aria-modal
tags:
  - doka
---

## Кратко

[Роль окна](/a11y/aria-roles/#roli-okon) `alertdialog` нужна для диалогового окна с важной информацией. Обычно это модальные диалоговые оповещения. Они прерывают действия пользователей и показывают важные сообщения, которые можно принять или отклонить. Например, согласен ли пользователь удалить данные или подтверждение о переводе денег.

## Пример

Модальное диалоговое окно:

```html
<div
  role="alertdialog"
  aria-labelledby="label"
  aria-describedby="description"
  aria-modal="true"
>
  <h3 id="label">Ошибка!</h3>
  <p id="description">
    Что-то пошло не так. Пожалуйста, попробуйте ещё раз позже.
  </p>
  <button>Закрыть</button>
</div>
```

## Как пишется

Добавьте к тегу `role="alertdialog"`, лучше к [`<div>`](/html/div/) или [`<dialog>`](/html/dialog/). Благодаря этой роли пользователи вспомогательных технологий поймут, что содержимое такого элемента отделено от остального содержимого страницы и содержит важное сообщение.

Сделайте диалоговое окно модальным с помощью [`aria-modal`](/a11y/aria-modal/). Этот элемент прерывает работу, и пока он открыт, пользователи не могут взаимодействовать с остальным содержимым.

Добавьте внутрь окна хотя бы один элемент, на который можно сделать фокус. Обычно это кнопка с текстом «Хорошо» или «Принять». При открытии окна фокус должен быть на этом элементе.

Чтобы диалоговое окно стало доступным, нужно ещё:

- добавить правильную подпись;
- поработать над фокусом с клавиатуры;
- добавить нужные стили для самого окна и элементов вокруг.

Добавить подпись для диалогового окна можно с помощью [`aria-labelledby`](/a11y/aria-labelledby/), когда в окне есть видимый заголовок, или [`aria-label`](/a11y/aria-label/), если видимого заголовка нет. Используйте для тега с подписью `id` с таким же значением, как у `aria-labelledby`. Это свяжет диалоговое окно с заголовком.

У диалогового окна может быть и его расширенное описание. В этом случае используйте [`aria-describedby`](/a11y/aria-describedby/).

Если использовать HTML-тег `<dialog>`, то не придётся делать большинство из этих шагов.

## Как понять

`alertdialog` объединяет роли [`alert`](/a11y/role-alert/) и [`dialog`](/a11y/role-dialog/). Это тип диалогового сообщения, которое рассказывает о чём-то важном как `alert`, но при этом требует ответа пользователя.

Если у важного сообщения или предупреждения нет интерактивных элементов и это просто текст на странице, используйте роль `alert`.