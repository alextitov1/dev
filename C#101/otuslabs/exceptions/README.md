# Калькулятор и обработка ошибок

## Цель:
Цель домашнего задания - закрепить знания о механизме работы с исключениями, полученным в ходе вебинара. Студенты научатся писать код, обрабатывающий исключения познакомятся с различными примерами встроенных исключений.

Описание/Пошаговая инструкция выполнения домашнего задания:
Основное задание
Нужно написать программу-калькулятор, которая обрабатывает простое выражение и выводит на следующей строке его результат.
При этом она должна корректно отрабатывать различные исключительные ситуации и ошибки.
Сама программа для ввода данных должна содержаться в функции Calculate(), то есть программа будет иметь вид

```C#
static void Main()
{
Calculate();
}
static void Calculate()
{
// А тут уже код программы
}
```
Выражение может быть сложением, вычитанием, умножением, делением двух целых чисел (тип int).
Формат выражения ЧИСЛО-ОПЕРАНД ОПЕРАТОР ЧИСЛО-ОПЕРАНД
В выражении между оператором и числам должен быть пробел.
После ввода выражения и нажатия ENTER на следующей строке выводится ответ в формате
ответ: результат выражения
Примеры выражений и вывода ответа.

```
100 + 200
ответ: 300
400 - 50
ответ: 350
8 * 7
ответ: 56
9 / 3
ответ: 3
```
Ввод выражений допускается до тех пор, пока пользователь не введет слово "стоп"
При преобразовании строк в числа не использовать функцию TryParse(), только Parse()
В программе должны быть следующие функции:

* Функция сложения чисел: принимает на вход два числа и выводит результат сложения:

`void Sum(int a, int b);`

* Функция вычитания чисел: принимает на вход два числа и выводит результат вычитания:

`void Sub(int a, int b);`

* Функция умножения чисел: принимает на вход два числа и выводит результат умножения

`void Mul(int a, int b);`
* Функция деления чисел: принимает на вход два числа и выводит результат деления

`void Div(int a, int b);`

Эти функции никакого текста, кроме Ответ:  выводить не должны
Функции Sum, Sub, Mul и Div внутри могут вызывать исключения, но обрабатываться они должны на уровне функции Calculate.

## Особенности работы программы
* Каждый вид исключения обрабатывается отдельным catch
* Пробрасываемые исключения не должны содержать сообщения, которые мы выводим в консоль, что выводить мы определяем по типу исключений
вся доп. информация информация

ИСКЛЮЧЕНИЯ, КОТОРЫЕ МОГУТ ВОЗНИКНУТЬ В ОБРАБОТЧИКЕ ВХОДНОГО ВЫРАЖЕНИЯ

### Кейс 1
Если у выражения нет оператора , выбросить исключение и вывести сообщение белым на красном фоне: Укажите в выражении оператор: +, -, *, / 

Например:

10 4

`Укажите в выражении оператор: +, -, *, /`

### Кейс 2
Если оператор не соответствует +, -, * или / , выбросить исключение и вывести сообщение сообщение белым на зеленом фоне: Я пока не умею работать с оператором оператор Например
10 % 4
Я пока не умею работать с оператором %

### Кейс 3
Если выражение не проходит по шаблону (нету оператора или его больше одного, нет пробелов между числами и оператором), выбросить исключение и вывести сообщение белым на красном фоне:
Выражение некорректное, попробуйте написать в формате
a + b
a * b
a - b
a / b

### Кейс 4
Если какой-то операнд не является числом, выбросить исключение и вывести сообщение белым на красном фоне: Операнд операнд не является числом Например
13c4 + 5
Операнд 13c4 не является числом
ИСКЛЮЧЕНИЯ, КОТОРЫЕ МОГУТ ВОЗНИКНУТЬ ВНУТРИ ФУНКЦИЙ Sum, Sub, Mul, Div

### Кейс 5
При делении на 0, выбросить исключение и вывести сообщение белый текст на фиолетовом фоне
Деление на ноль

### Кейс 6
Если при вычислении выражения получился ответ 13, вывести ответ как обычно но после этого выбросить исключение и вывести белый текст на зеленом фоне
вы получили ответ 13!
Остальные ошибки

### Кейс 7 - Все остальные исключения
Во всех остальных ошибках - вывести текст
Я не смог обработать ошибку
И завершить работу программы

### Доп. задание 1
При написании своих исключений Для кейсов 1-5 попробуйте передавать аргумент для вывода текста как отдельном поле собственного исключения, так и в поле Data (для разных исключений - разный способ)

### Доп. задание 2
В случае возникновения исключений из Кейс 7 пробросить его дальше и обработать в main, выведя текст
В калькуляторе произошла ошибка: текст ошибки

### Задание со звездочкой
Если результат выражения в целом типе не помещается в тип int (например 2000000000000 * 10), выбросить исключение и вывести сообщение белым на синем фоне
Результат выражения вышел за границы int

## Критерии оценки:
6 баллов - за выполнение условий домашнего задания, программа находит решение/решения уравнения согласно пунктам 1-6
1 балл - программа обрабатывает случай, когда введенное значение не вмещается в тип int - отдельный обработчик с выводом значения на зеленом фоне с указанием, в каком диапазоне значений можно вводить данные
1 балл - за доп. задание.
2 балла - за задание со звездочкой
Для зачета нужно набрать 6 баллов

Рекомендуем сдать до: 02.06.2022