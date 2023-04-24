# Задача

В данном проекте я сделал модель, которая помогает извлекать нужный фрагмент текста по соответствующему запросу.  
  
Виды запросов  
- обеспечение исполнения контракта  
- обеспечение гарантийных обязательств  
  
Иначе говоря модель принимает 'текст документа' и 'запрос', а возвращает нужный фрагмент текста.

# Решение
Подходом к решению задачи я "вдохновился" главой из учебника <code>[huggingface QA](https://huggingface.co/learn/nlp-course/chapter7/7?fw=pt)</code>. Вся предобработка текста взята именно от туда. Модель выбирал из несольких вариантов: DeBERTaV3, XLM-RoBERTa, DistilBERT. Именно эти модели для задачи Question Answering на русском языке есть в открытом доступе. Я пробовал обучать все алгоритмы, все они выдавали примерно одинаковые метрики, поэтому я остановился на DistilBERT так как он меньше всех весит(500мб) и обучается намного быстрее, чем первые два варианта.  
  
Для более качественного решения можно также попробовать использовать SotA алгоритмы, предобучить их на русский язык, например, на датасете SQuAD от сбера, а затем "затюнить" под задачу на данном от заказчиков датасете.
