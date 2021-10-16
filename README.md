# НЕ ДОДЕЛАНО!! НЕ ПЫТАЕТЕЙСЬ УСТАНОВИТЬ. 
![Лого](https://cdn.glitch.me/8685b903-90ff-4ff9-bf0c-7a995b173fee%2FF4677E91-21D8-4883-B324-1CCAB4DF5D20.png?v=1634052098051)
[![Сайт](IMG_20211016_110201.jpg)](https://astraroblox.xyz/?from=github)
# Установка
> ```console
> npm install astraapi
> ```
> **!!** Если ваш сайт на хостинге например [Glitch](https://glitch.com) или [Repl](https://replit.com), добавьте в ваш package.json эту строку в dependencies: «"astraapi": "^1.0.0"». Пример:
 ```json
{
  "name": "СайтОплата",
  "version": "0.0.1",
  "description": "Крутой сайт.",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {
    "astraapi": "^1.0.0"
  },
  "engines": {
    "node": "12.x"
  }
```
## Добавление в код, использование модуля и ключа:
> ```js
> const Astra = require('astraapi') // Использовать модуль
> const Key = process.env.KEY // Ключ, спрятанный в .ENV, если хотите использовать локально, пропишите вместо этого: 'ВАШ_КЛЮЧ' 
> const AstraAPI = Astra.Connect(Key) // Подключение к ключу
> ```
> **!!** Перед использовании функции, обезательяно напишите AstraApi. Пример в Express.JS:
```js
app.get('/донат100', function(req, res) => {
const Astra = require('astraapi')
const Key = process.env.KEY
const AstraAPI = Astra.Connect(Key)
const Link = AstraAPI.createPayment(100, "Донат") // Создаёт ссылку для оплаты.
res.redirect(Link) // Переадресация
});
```
## Всё функции
> ### createPayment
> ```js
> AstraAPI.createPayment(сумма, "Комментарий", индификатор)
> ```
> #### Примерный ответ:
> ```console
> https://o.astraroblox.xyz/testoplata?amount=сумма&comment=комментарий&domain=название
> ```
> #### Описание:
> Создать ссылку для оплаты счета.
