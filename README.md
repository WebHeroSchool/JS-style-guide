# JS Style Guide
## 1. Фигурные скобки
Пишутся на той же строке, так называемый «египетский» стиль. Перед скобкой – пробел.
![](https://learn.javascript.ru/article/coding-style/figure-bracket-style@2x.png)
## 2. Длина строки
Максимальную длину строки согласовывают в команде. Как правило, это либо *80*, либо *120* символов, в зависимости от того, какие мониторы у разработчиков.
Более длинные строки необходимо разбивать для улучшения читаемости.
## 3. Горизонтальные отступы
Как правило, используются именно пробелы, т.к. они позволяют сделать более гибкие «конфигурации отступов», чем символ «Tab». Например, выровнять аргументы относительно открывающей скобки:
```
show("Строки" +
     " выровнены" +
     " строго" +
     " одна под другой");
```
## 4. Вертикальные отступы
Вертикальный отступ, для лучшей разбивки кода – перевод строки. Используется, чтобы разделить логические блоки внутри одной функции. В примере разделены инициализация переменных, главный цикл и возвращение результата:
```
function pow(x, n) {
  var result = 1;
  //              <--
  for (var i = 0; i < n; i++) {
    result *= x;
  }
  //              <--
  return result;
}
```
Вставляйте дополнительный перевод строки туда, где это сделает код более читаемым. Не должно быть более 9 строк кода подряд без вертикального отступа.
## 5. Именование
Общее правило:
Имя переменной – существительное.
Имя функции – глагол или начинается с глагола. Бывает, что имена для краткости делают существительными, но глаголы понятнее.
Для имён используется английский язык (не транслит) и верблюжья нотация.
## 6. Пишите короткие функции, решающие одну задачу
Функции легче поддерживать, они становятся гораздо более понятными, читабельными, если они направлены на решение лишь какой-то одной задачи. Если мы сталкиваемся с ошибкой, то, при использовании маленьких функций, найти источник этой ошибки становится гораздо легче. Кроме того, улучшаются возможности по повторному использованию кода.
## 7. Используйте идеи инкапсуляции и модульности
Группируйте связанные переменные и функции для того, чтобы сделать ваш код понятнее и улучшить его с точки зрения его повторного использования.
![](https://cdn-images-1.medium.com/max/1600/1*HX7KCnfRx65cV1P17ieeyQ.png)
## 8. Массивы
Для создания массива используйте квадратные скобки. Не создавайте массивы через конструктор new Array.
```
// плохо
var items = new Array();

// хорошо
var items = [];
```
## 9. Уровни вложенности
Уровней вложенности должно быть немного.
Например, проверки в циклах можно делать через «continue», чтобы не было дополнительного уровня if(..) { ... }:

Вместо:
```
for (var i = 0; i < 10; i++) {
  if (i подходит) {
    ... // <- уровень вложенности 2
  }
}
```
Используйте:
```
for (var i = 0; i < 10; i++) {
  if (i не подходит) continue;
  ...  // <- уровень вложенности 1
}
```
## 10. Точка с запятой
Точки с запятой нужно ставить, даже если их, казалось бы, можно пропустить. Есть языки, в которых точка с запятой не обязательна, и её там никто не ставит. В JavaScript перевод строки её заменяет, но лишь частично, поэтому лучше её ставить.