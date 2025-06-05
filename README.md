
### 1. Запуск Лабораторної №7 RabbitMQ через Docker
Спочатку перейти в директорію:
```bash
cd D:\lab7
```
Запустити докер:
```bash
docker compose up
```

* Інтерфейс RabbitMQ доступний за адресою: [http://localhost:15672](http://localhost:15672)
* Дані для входу:

  * **Логін:** `user`
  * **Пароль:** `password`

---

### 2. Aктивація віртуального середовища

```bash
source venv/Scripts/activate
```

### 3. Встановлення необхідних залежностей

```bash
pip install -r requirements.txt
```

---

## 🚀 Запуск проєкту

Запускай два окремі термінали — для кожного з ботів.

---

### Термінал 1 — запуск **sender_bot.py** (бот: `EventPublisherBot`)

```bash
source venv/Scripts/activate
```
```bash
python sender_bot.py
```

---

### Термінал 2 — запуск **receiver_bot.py** (бот: `EventListenerBot`)

```bash
source venv/Scripts/activate
```
```bash
python receiver_bot.py
```

---

## 🧪 Перевірка роботи системи

1. Відкрий Telegram та знайди бота **EventPublisherBot**.
2. Надішли йому будь-яке повідомлення.
3. У чаті з **EventListenerBot** має з'явитися відповідь у вигляді:

```
Користувач <Ім’я> надіслав: <текст повідомлення>
```

> Щоб отримати `chat_id` для вставлення у `message_receiver.py`, спочатку запусти `fetch_chat_id.py` і надішли повідомлення боту.

---

## 📁 Структура проєкту

```
lab7-event-architecture/
├── docker-compose.yml
├── requirements.txt
├── message_sender.py      # бот-відправник
├── message_receiver.py    # бот-отримувач
├── fetch_chat_id.py       # допоміжний бот для отримання chat_id
└── README.md
```

---

## 🧹 Завершення роботи

### Зупинка RabbitMQ

```bash
docker compose down
```

