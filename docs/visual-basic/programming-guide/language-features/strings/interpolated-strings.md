---
title: Интерполированные строки
ms.date: 10/31/2017
ms.openlocfilehash: d1220f3804d571f6da229dc5dfa099a22ab1478d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344328"
---
# <a name="interpolated-strings-visual-basic-reference"></a>Interpolated Strings (Visual Basic Reference)

Используется для создания строк.  Интерполированное строковое выражение выглядит как строка шаблона, которая содержит *интерполированные выражения*.  Интерполированная строка возвращает строку, которая заменяет содержащиеся в ней интерполированные выражения строковыми представлениями. This feature is available in Visual Basic 14 and later versions.

Аргументы интерполированной строки понять проще, чем [строку составного формата](../../../../standard/base-types/composite-formatting.md#composite-format-string).  Например, интерполированная строка

```vb
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```

содержит два интерполированных выражения "{name}" и "{hours:hh}". Эквивалентная строка составного формата имеет следующий вид:

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours)
```

Структура интерполированной строки выглядит следующим образом:

```vb
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."
```

Здесь:

- *field-width* — это целое число со знаком, указывающее количество символов в поле. Если оно является положительным, поле выравнивается по правому краю, если оно отрицательное — по левому краю.

- *format-string* — это строка формата, соответствующая типу форматируемого объекта. For example, for a <xref:System.DateTime> value, it could be a [standard date and time format string](../../../../standard/base-types/standard-date-and-time-format-strings.md) such as "D" or "d".

> [!IMPORTANT]
> Между `$` и `"` в начале строки не может быть пробела. Doing so causes a compiler error.

Интерполированную строку можно использовать везде, где допустимо применять строковый литерал.  Интерполированная строка вычисляется каждый раз, когда выполняется код с интерполированной строкой. Это позволяет разделить определение и вычисление интерполированной строки.

Чтобы включить в интерполированную строку фигурные скобки ("{" или "}"), используйте две фигурные скобки — "{{" или "}}".  Дополнительные сведения см в разделе «Неявные преобразования».

Если интерполированная строка содержит другие символы со специальным значением в интерполированной строке, например, знак кавычки ("), двоеточие (:) или запятая (,), их необходимо экранировать, если они встречаются в обычном тексте, или они должны быть включены в выражение, разделенное круглыми скобками, если они являются языковыми элементами, включенными в интерполированное выражение. В следующем примере показано экранирование кавычек, чтобы включить их в результирующую строку, и использование скобок для разделения выражения `(age == 1 ? "" : "s")`, чтобы двоеточие не интерпретировалось как начало строки формата.

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]

## <a name="implicit-conversions"></a>Неявные преобразования

Существует три преобразования неявных типов из интерполированных строк.

1. Преобразование интерполированной строки в <xref:System.String>. В следующем примере возвращается строка, интерполированные строковые выражения которой были заменены их строковыми представлениями. Пример:

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]

   Это окончательный результат интерпретации строк. Все вхождения двойных фигурных скобок ("{{" и "}}") преобразуются в одиночную фигурную скобку.

2. Преобразование интерполированной строки в переменную <xref:System.IFormattable>, которая позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.IFormattable>. Это полезно для включения правильных форматов чисел и дат для отдельных языков.  Все вхождения двойных фигурных скобок ("{{" и "}}") остаются двойными фигурными скобками до тех пор, пока строка не будет отформатирована путем явного или неявного вызова метода <xref:System.Object.ToString>.  All contained interpolation expressions are converted to {0}, {1}, and so on.

   В следующем примере используется отражение для отображения членов, а также значений поля и свойства переменной <xref:System.IFormattable>, созданной из интерполированной строки. Кроме того, переменная <xref:System.IFormattable> передается в метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>.

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]

   Обратите внимание, что интерполированную строку можно проверить только с помощью отражения. Если она передается методу форматирования строк, например <xref:System.Console.WriteLine(System.String)>, элементы формата разрешаются и возвращается результирующая строка.

3. Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string. Проверка строки составного формата и способа ее отрисовки в виде результирующей строки может, например, обеспечивать защиту от атак путем внедрения кода, если выполнялось построение запроса. A <xref:System.FormattableString> also includes:

      - Перегрузка <xref:System.FormattableString.ToString>, которая формирует результирующую строку для <xref:System.Globalization.CultureInfo.CurrentCulture>.

      - A <xref:System.FormattableString.Invariant%2A> method that produces a string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.

      - Метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, который формирует результирующую строку для указанного языка и региональных параметров.

    All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format.  All contained interpolation expressions are converted to {0}, {1}, and so on.

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]

## <a name="see-also"></a>См. также

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- [Справочник по языку Visual Basic](index.md)
