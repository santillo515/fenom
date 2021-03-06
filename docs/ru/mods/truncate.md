Модификатор truncate
=================

Обрезает переменную до определенной длинны, по умолчанию - 80 символов.
В качестве необязательного второго параметра, вы можете передать строку текста, которая будет отображатся в конце обрезанной переменной. Символы этой строки не включаются в общую длинну обрезаемой строки. По умолчанию, truncate попытается обрезать строку в промежутке между словами. Если вы хотите обрезать строку строго на указаной длинне, передайте в третий необязательный параметр значение true.

```smarty
{$long_string|truncate:$length:$etc:$by_words:$middle}
```

* `$length`, обязателен. Определяет максимальную длинну обрезаемой строки.
* `$etc`, по умолчанию `...`. Текстовая строка, которая заменяет обрезанный текст. Её длинна НЕ включена в максимальную длинну обрезаемой строки.
* `$by_word`, по умолчанию **FALSE**. Определяет, обрезать ли строку в промежутке между словами (true) или строго на указаной длинне (false).
* `$middle`, по умолчанию **FALSE**. Определяет, нужно ли обрезать строку в конце (false) или в середине строки (true).

```smarty
{var $str = "very very long string"}

{$str|truncate:10:" read more..."} output: very very read more...
{$str|truncate:5:" ... ":true:true} output: very ... string
```

Модификатор работает с unicode без дополнительных расширений.