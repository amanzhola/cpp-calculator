# 🧮 C++ Calculator  
**Финальная версия проекта третьего спринта**

---

## 📌 Описание

Многофункциональный калькулятор на **C++ + Qt**, поддерживающий различные числовые типы через шаблоны и реализующий архитектуру **MVC (Controller + View)**.

Проект демонстрирует:

- шаблонный программируемый калькулятор
- поддержку разных типов чисел
- работу с пользовательским интерфейсом Qt
- обработку ошибок и edge-case сценариев
- разделение логики и UI

---

## 🧱 Архитектура

<table width="100%">
  <tr>
    <td width="16.66%" valign="top"><b>🧠 Calculator&lt;T&gt;</b><br>Бизнес-логика вычислений</td>
    <td width="16.66%" valign="top"><b>🎮 Controller&lt;T&gt;</b><br>Связь между UI и калькулятором</td>
    <td width="16.66%" valign="top"><b>🖼️ MainWindow</b><br>Пользовательский интерфейс Qt</td>
    <td width="16.66%" valign="top"><b>🔢 Rational</b><br>Кастомный тип рациональных чисел</td>
    <td width="16.66%" valign="top"><b>⚙️ pow.h</b><br>Возведение в степень</td>
    <td width="16.66%" valign="top"><b>📊 enums.h</b><br>Операции и управляющие клавиши</td>
  </tr>
</table>

---

## ⚙️ Поддерживаемые типы

<table width="100%">
  <tr>
    <td width="14.28%" valign="top"><b>double</b><br>Полная поддержка дробей и степени</td>
    <td width="14.28%" valign="top"><b>float</b><br>Аналогично double</td>
    <td width="14.28%" valign="top"><b>int</b><br>Целые числа</td>
    <td width="14.28%" valign="top"><b>int64_t</b><br>Расширенный целочисленный диапазон</td>
    <td width="14.28%" valign="top"><b>uint8_t</b><br>Байт</td>
    <td width="14.28%" valign="top"><b>size_t</b><br>Только неотрицательные значения</td>
    <td width="14.28%" valign="top"><b>Rational</b><br>Рациональные числа</td>
  </tr>
</table>

👉 Переключение типов через UI (ComboBox)

---

## ➕ Поддерживаемые операции

<table width="100%">
  <tr>
    <td width="20%" valign="top"><b>➕ Сложение</b><br>✔</td>
    <td width="20%" valign="top"><b>➖ Вычитание</b><br>✔</td>
    <td width="20%" valign="top"><b>✖ Умножение</b><br>✔</td>
    <td width="20%" valign="top"><b>➗ Деление</b><br>✔ с проверками</td>
    <td width="20%" valign="top"><b>^ Степень</b><br>✔ зависит от типа</td>
  </tr>
</table>

---

## ⚠️ Обработка ошибок

Калькулятор возвращает ошибки через:

```cpp
std::optional<std::string>
````

Примеры:

* `Integer division by zero`
* `Integer negative power`
* `Zero power to zero`
* `Fractional power is not supported`
* `No saved value`
* `Unsupported number type`

---

## 🧠 Особенности реализации

<table width="100%">
  <tr>
    <td width="25%" valign="top"><b>Шаблонный Calculator&lt;T&gt;</b><br>Одна логика для нескольких числовых типов</td>
    <td width="25%" valign="top"><b>if constexpr</b><br>Разное поведение в зависимости от типа</td>
    <td width="25%" valign="top"><b>MVC</b><br>Контроллер отделён от интерфейса</td>
    <td width="25%" valign="top"><b>Extra Key</b><br>`.` для float/double, `/` для Rational</td>
  </tr>
</table>

---

## 🧩 Дополнительные функции

<table width="100%">
  <tr>
    <td width="16.66%" valign="top"><b>±</b><br>Смена знака</td>
    <td width="16.66%" valign="top"><b>⌫</b><br>Удаление последнего символа</td>
    <td width="16.66%" valign="top"><b>MS</b><br>Сохранение в память</td>
    <td width="16.66%" valign="top"><b>MR</b><br>Загрузка из памяти</td>
    <td width="16.66%" valign="top"><b>MC</b><br>Очистка памяти</td>
    <td width="16.66%" valign="top"><b>Форматирование</b><br>Scientific notation и удаление лишних нулей</td>
  </tr>
</table>

---

## 📂 Структура проекта

```bash
cpp-calculator/
│
├── main.cpp
├── mainwindow.cpp / .h
├── mainwindow.ui
│
├── calculator.h
├── controller.h
├── rational.h
├── pow.h
├── enums.h
│
└── .pro
```

---

## ▶️ Запуск

```bash
qmake
make
./app
```

или через Qt Creator

---

## 🎯 Чему учит проект

<table width="100%">
  <tr>
    <td width="16.66%" valign="top"><b>Templates</b><br>Шаблоны C++</td>
    <td width="16.66%" valign="top"><b>if constexpr</b><br>Типо-зависимая логика</td>
    <td width="16.66%" valign="top"><b>MVC</b><br>Разделение ответственности</td>Ф
    <td width="16.66%" valign="top"><b>Qt UI</b><br>GUI на Qt</td>
    <td width="16.66%" valign="top"><b>Error Handling</b><br>Обработка ошибок</td>
    <td width="16.66%" valign="top"><b>Custom Types</b><br>Рациональные числа</td>
  </tr>
</table>

---

## 🚀 Возможные улучшения

* история операций
* сохранение состояния
* поддержка complex чисел
* unit-тесты
* MVVM вместо MVC
* темная тема

---

## 👨‍💻 Автор
Amanzhol

C++ / Qt / Templates / MVC
