# 🧮 C++ Calculator  
**Финальная версия проекта третьего спринта**

---

## 📌 Описание

Многофункциональный калькулятор на **C++ и Qt** с поддержкой нескольких числовых типов, шаблонной бизнес-логикой и разделением интерфейса и вычислений через контроллер.

Проект демонстрирует:

- шаблоны C++;
- архитектуру Controller + View;
- работу с разными числовыми типами;
- кастомный тип `Rational`;
- обработку ошибок;
- форматирование ввода и вывода;
- UI на Qt Widgets. 

---

## 🧱 Архитектура

<table width="100%">
  <tr>
    <td width="20%" valign="top"><b>Calculator&lt;T&gt;</b><br>Шаблонная бизнес-логика вычислений</td>
    <td width="20%" valign="top"><b>Controller&lt;T&gt;</b><br>Связь между UI и калькулятором</td>
    <td width="20%" valign="top"><b>MainWindow</b><br>Qt-интерфейс и обработка сигналов</td>
    <td width="20%" valign="top"><b>Rational</b><br>Кастомный тип рациональных чисел</td>
    <td width="20%" valign="top"><b>pow.h / enums.h</b><br>Степень, операции и управляющие клавиши</td>
  </tr>
</table>

---

## 🔢 Поддерживаемые числовые типы

<table width="100%">
  <tr>
    <td width="14.28%" valign="top"><b>double</b><br>Дробные числа, точка, степень</td>
    <td width="14.28%" valign="top"><b>float</b><br>Поведение как у double</td>
    <td width="14.28%" valign="top"><b>uint8_t</b><br>Малый целочисленный диапазон</td>
    <td width="14.28%" valign="top"><b>int</b><br>Целые числа</td>
    <td width="14.28%" valign="top"><b>int64_t</b><br>Большие целые числа</td>
    <td width="14.28%" valign="top"><b>size_t</b><br>Только неотрицательные значения</td>
    <td width="14.28%" valign="top"><b>Rational</b><br>Дроби вида numerator / denominator</td>
  </tr>
</table>

---

## ➕ Поддерживаемые операции

<table width="100%">
  <tr>
    <td width="20%" valign="top"><b>Сложение</b><br><code>Add</code></td>
    <td width="20%" valign="top"><b>Вычитание</b><br><code>Sub</code></td>
    <td width="20%" valign="top"><b>Умножение</b><br><code>Mul</code></td>
    <td width="20%" valign="top"><b>Деление</b><br><code>Div</code></td>
    <td width="20%" valign="top"><b>Степень</b><br><code>Pow</code></td>
  </tr>
</table>

---

## ⚠️ Обработка ошибок

<table width="100%">
  <tr>
    <td width="20%" valign="top"><b>Integer division by zero</b><br>Деление целого типа на ноль</td>
    <td width="20%" valign="top"><b>Integer negative power</b><br>Отрицательная степень для целых</td>
    <td width="20%" valign="top"><b>Zero power to zero</b><br>Неопределённость 0^0</td>
    <td width="20%" valign="top"><b>Fractional power is not supported</b><br>Дробная степень для Rational</td>
    <td width="20%" valign="top"><b>No saved value</b><br>Попытка загрузки пустой памяти</td>
  </tr>
</table>

---

## 🧠 Ключевые особенности

<table width="100%">
  <tr>
    <td width="25%" valign="top"><b>Шаблонный калькулятор</b><br>Один класс работает для разных типов через <code>template&lt;typename Number&gt;</code></td>
    <td width="25%" valign="top"><b>if constexpr</b><br>Разное поведение для float, int и Rational на этапе компиляции</td>
    <td width="25%" valign="top"><b>Controller</b><br>Обрабатывает кнопки, операции, память и синхронизацию с интерфейсом :contentReference[oaicite:1]{index=1}</td>
    <td width="25%" valign="top"><b>Форматирование UI</b><br>Приведение формулы и чисел к аккуратному виду в интерфейсе :contentReference[oaicite:2]{index=2}</td>
  </tr>
</table>

---

## 💾 Память калькулятора

<table width="100%">
  <tr>
    <td width="33.33%" valign="top"><b>MS</b><br>Сохранить текущее значение</td>
    <td width="33.33%" valign="top"><b>MR</b><br>Загрузить сохранённое значение</td>
    <td width="33.33%" valign="top"><b>MC</b><br>Очистить память</td>
  </tr>
</table>

---

## 🎛️ Дополнительные элементы управления

<table width="100%">
  <tr>
    <td width="20%" valign="top"><b>±</b><br>Смена знака</td>
    <td width="20%" valign="top"><b>⌫</b><br>Удаление последнего символа</td>
    <td width="20%" valign="top"><b>Extra key</b><br><code>.</code> для float/double</td>
    <td width="20%" valign="top"><b>Extra key</b><br><code>/</code> для Rational</td>
    <td width="20%" valign="top"><b>Controller switch</b><br>Выбор типа через ComboBox</td>
  </tr>
</table>

---

## 🖼️ Интерфейс

Qt UI содержит:

- поле результата;
- поле формулы;
- индикатор памяти;
- цифровые кнопки;
- кнопки операций;
- кнопки памяти;
- кнопку backspace;
- переключатель типа числа;
- дополнительную кнопку для точки или дробной черты. 

---

## 📂 Структура проекта

<table width="100%">
  <tr>
    <td width="10%" valign="top"><b>main.cpp</b></td>
    <td width="20%" valign="top">Создание окна и подключение контроллеров разных типов</td>
    <td width="10%" valign="top"><b>calculator.h</b></td>
    <td width="20%" valign="top">Шаблонная логика вычислений</td>
    <td width="10%" valign="top"><b>controller.h</b></td>
    <td width="30%" valign="top">Связь UI и калькулятора, обработка операций и памяти</td>
  </tr>
  <tr>
    <td width="10%" valign="top"><b>mainwindow.h/.cpp</b></td>
    <td width="20%" valign="top">Интерфейс и работа с сигналами Qt</td>
    <td width="10%" valign="top"><b>mainwindow.ui</b></td>
    <td width="20%" valign="top">Разметка окна калькулятора</td>
    <td width="10%" valign="top"><b>rational.h</b></td>
    <td width="30%" valign="top">Рациональные числа и арифметика над ними</td>
  </tr>
  <tr>
    <td width="10%" valign="top"><b>pow.h</b></td>
    <td width="20%" valign="top">Возведение в степень для целых и Rational</td>
    <td width="10%" valign="top"><b>enums.h</b></td>
    <td width="20%" valign="top">Операции, контролы, типы контроллеров</td>
    <td width="10%" valign="top"><b>.pro</b></td>
    <td width="30%" valign="top">Qt project file и состав сборки</td>
  </tr>
</table>

---

## ▶️ Сборка и запуск

```bash
qmake
make
````

На Windows вместо `make` может использоваться:

```bash
nmake
```

Также проект можно открыть напрямую через **Qt Creator**. 

---

## 🎯 Чему учит проект

<table width="100%">
  <tr>
    <td width="20%" valign="top"><b>Templates</b><br>Шаблонные классы и универсальная логика</td>
    <td width="20%" valign="top"><b>Type traits</b><br><code>std::is_integral_v</code>, <code>std::is_same_v</code></td>
    <td width="20%" valign="top"><b>Qt Widgets</b><br>GUI, сигналы, слоты, UI-файл</td>
    <td width="20%" valign="top"><b>MVC / Controller pattern</b><br>Разделение интерфейса и вычислений</td>
    <td width="20%" valign="top"><b>Error handling</b><br>Обработка edge-case сценариев</td>
  </tr>
</table>

---

## 🚀 Возможные улучшения

<table width="100%">
  <tr>
    <td width="16.66%" valign="top">История операций</td>
    <td width="16.66%" valign="top">Сохранение состояния</td>
    <td width="16.66%" valign="top">Unit-тесты</td>
    <td width="16.66%" valign="top">Complex numbers</td>
    <td width="16.66%" valign="top">Темы оформления</td>
    <td width="16.66%" valign="top">MVVM-архитектура</td>
  </tr>
</table>

---

## 👨‍💻 Автор
Amanzhol

Учебный проект по **C++ / Qt / Templates / GUI architecture**
