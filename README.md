## https://t.me/ml_iad24_bot
### Бот на вход принимает выбранный язык и фотографию с текстом, далее данное фото обрабатывается и с помощью модели tesseract выделяется текст. После обработки текст приходит пользователю 


<table border="0">
 <tr>
    <td><b style="font-size:30px">Telegram Bot </b></td>
    <td><b style="font-size:30px">Обработка Изображения  </b></td>
    <td><b style="font-size:30px">Telegram API </b></td>
    <td><b style="font-size:30px">OCR (Tesseract) </b></td>
 </tr>
 <tr>
    <td>Получение фото, Отправка сообщений </td>
    <td> Уменьшение размера, улучшение контраста, шумоподавление </td>                        
    <td> Отправка фото, получение файла </td>
    <td> Распознавание текста </td>
 </tr>
</table>

### UML Sequence Diagram

```plantuml
@startuml
actor User
participant Bot
participant "Telegram API" as API
participant "Tesseract OCR" as OCR
participant "File System" as FS

User -> Bot : Отправка фото
Bot -> API : Получить фото
API -> Bot : Отправить фото
Bot -> FS : Скачать фото
FS -> Bot : Фото сохранено
Bot -> OCR : Предобработка и распознавание текста
OCR -> Bot : Вернуть текст
Bot -> User : Отправить текст
@enduml

