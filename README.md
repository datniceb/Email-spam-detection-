 Email Spam Detection

 О проекте

Этот проект представляет собой модель машинного обучения для классификации электронных писем на спам и не-спам (ham). Модель использует алгоритм Multinomial Naive Bayes и обрабатывает текстовые данные с помощью CountVectorizer.

📊 Используемые данные

Набор данных: SMS Spam Collection Dataset

Источник: Kaggle (/kaggle/input/sms-spam-collection-dataset/spam.csv)
Размер: 5572 строки
Колонки: Category (ham/spam), Message (текст сообщения)
🛠️ Технологии и инструменты

Python 3.12.12
Pandas – обработка данных
Scikit-learn – машинное обучение
CountVectorizer – векторизация текста
MultinomialNB – наивный байесовский классификатор
Pipeline – объединение этапов обработки
🔄 Основные этапы проекта

1. Загрузка и подготовка данных

Загрузка CSV-файла с указанием кодировки latin-1
Переименование колонок для удобства
Удаление лишних колонок
Проверка на пропуски данных
2. Преобразование данных

Создание бинарной колонки Spam (1 – спам, 0 – не спам)
Разделение данных на обучающую и тестовую выборки (75%/25%)
3. Построение модели

Используется Pipeline, объединяющий:

CountVectorizer – преобразование текста в матрицу частот слов
MultinomialNB – мультиномиальный наивный байесовский классификатор
4. Обучение и оценка модели

Обучение на тренировочных данных
Прогнозирование на тестовых данных
Оценка точности модели: ~98.99%
🧪 Тестирование модели

Модель была протестирована на различных примерах сообщений:

python
test_messages = [
    "Hey, are we meeting tomorrow?",  # → НЕ СПАМ
    "WIN FREE IPHONE NOW!!!",  # → СПАМ
    "Can you call me?",  # → НЕ СПАМ
    "URGENT: Your account compromised",  # → СПАМ
    "Meeting moved to 3pm",  # → НЕ СПАМ
    "Congratulations you won $1000",  # → СПАМ
    "What's for dinner?",  # → НЕ СПАМ
    "TXT STOP to unsubscribe",  # → СПАМ
]
📈 Результаты

Точность модели на тестовых данных: 98.99%
Модель успешно различает обычные сообщения и спам
Pipeline позволяет легко масштабировать и дообучать модель
🚀 Как запустить проект

1. Клонировать репозиторий

bash
git clone <repository-url>
cd email-spam-detection
2. Установить зависимости

bash
pip install pandas scikit-learn numpy
3. Запустить ноутбук

bash
jupyter notebook email-spam-detection.ipynb
Или выполнить как скрипт:

bash
python -m nbconvert --to script email-spam-detection.ipynb
python email-spam-detection.py
📁 Структура проекта

text
email-spam-detection/
├── email-spam-detection.ipynb  # Основной ноутбук с кодом
├── README.md                   # Этот файл
└── requirements.txt            # Зависимости (если добавлены)
