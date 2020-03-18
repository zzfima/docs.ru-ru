---
title: $ — интерполяция строк — справочные материалы по C#
description: Интерполяция строк предоставляет более понятный и удобный синтаксис для форматирования строковых выходных данных, чем традиционное составное форматирование строк.
ms.date: 09/02/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.openlocfilehash: 97bc606569b83bd14cd3b32495deb8e529747e9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76980123"
---
# <a name="---string-interpolation-c-reference"></a>$ — интерполяция строк (справочные материалы по C#)

Специальный знак `$` идентифицирует строковый литерал как *интерполированную строку*. Интерполированная строка — это строковый литерал, который может содержать *выражения интерполяции*. При разрешении интерполированной строки в результирующую элементы с выражениями интерполяции заменяются строковыми представлениями результатов выражений. Эта функция доступна начиная с C# 6.

Интерполяция строк предоставляет более понятный и удобный синтаксис для создания форматированных строк по сравнению с функцией [составного форматирования строк](../../../standard/base-types/composite-formatting.md). В следующем примере обе этих функции используются для получения одинаковых выходных данных:

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a>Структура интерполированной строки

Для определения строкового литерала в качестве интерполированной строки добавьте к началу символ `$`. Между `$` и `"` в начале строкового литерала не может быть пробела.

Структура элемента с выражением интерполяции выглядит следующим образом:

```csharp
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

Элементы в квадратных скобках являются необязательными. Каждый из элементов описан в таблице ниже:

|Элемент|Описание:|
|-------------|-----------------|
|`interpolationExpression`|Выражение, создающее форматируемый результат. Строковое представление `null` является <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|Константное выражение, значение которого определяет минимальное количество символов в строковом представлении результата выражения. Если оно положительное, строковое представление выравнивается по правому краю, если отрицательное — по левому краю. Дополнительные сведения см. в разделе [Компонент выравнивания](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Строка форматирования, поддерживаемая типом результата выражения. Дополнительные сведения см. в разделе [Компонент строки форматирования](../../../standard/base-types/composite-formatting.md#format-string-component).|

В следующем примере используются необязательные компоненты форматирования, описанные выше:

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a>Специальные символы

Чтобы включить в текст, создаваемый интерполированной строкой, фигурную скобку "{" или "}", используйте две фигурные скобки — "{{" или "}}". Подробнее см. в разделе [Экранирование фигурных скобок](../../../standard/base-types/composite-formatting.md#escaping-braces).

Двоеточие (:) имеет особое значение в элементе выражения интерполяции. Чтобы использовать [условный оператор](../operators/conditional-operator.md) в выражении интерполяции, заключите это выражение в скобки.

В следующем примере показано, как включить фигурную скобку в результирующую строку, а также использовать условный оператор в выражении интерполяции:

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

Интерполированная строка verbatim начинается с символа `$`, за которым следует символ `@`. Дополнительные сведения о буквальных строках см. в разделах о [строках](../builtin-types/reference-types.md) и [буквальном идентификаторе](verbatim.md)).

> [!NOTE]
> Начиная с C# 8.0 маркеры `$` и `@` можно использовать в любом порядке: `$@"..."` и `@$"..."` являются допустимыми интерполированными строками verbatim. В более ранних версиях C# маркер`$` должен располагаться перед маркером `@`.

## <a name="implicit-conversions-and-how-to-specify-iformatprovider-implementation"></a>Неявные преобразования и указание реализации `IFormatProvider`

Существует три неявных преобразования из интерполированных строк.

1. Преобразование интерполированной строки в экземпляр <xref:System.String>, являющийся результатом разрешения интерполированной строки, где элементы выражения интерполяции заменяются на должным образом форматированные строковые представления их результатов. Это преобразование использует <xref:System.Globalization.CultureInfo.CurrentCulture> для форматирования результатов выражений.

1. Преобразование интерполированной строки в экземпляр <xref:System.FormattableString>, представляющий строку составного формата, а также форматируемые результаты выражения. Это позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.FormattableString>. Для этого вызовите один из следующих методов:

      - Перегрузка <xref:System.FormattableString.ToString>, которая формирует результирующую строку для <xref:System.Globalization.CultureInfo.CurrentCulture>.
      - Метод <xref:System.FormattableString.Invariant%2A>, который формирует результирующую строку для <xref:System.Globalization.CultureInfo.InvariantCulture>.
      - Метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, который формирует результирующую строку для указанного языка и региональных параметров.

    Также можно использовать метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, чтобы предоставить пользовательские реализации интерфейса <xref:System.IFormatProvider>, который поддерживает настраиваемое форматирование. Дополнительные сведения см. в статье [Типы форматирования в .NET](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter), разделе [Настраиваемое форматирование с использованием интерфейса ICustomFormatter](../../../standard/base-types/formatting-types.md).

1. Преобразование интерполированной строки в экземпляр <xref:System.IFormattable>, который также позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.IFormattable>.

В следующем примере используется неявное преобразование в <xref:System.FormattableString> для создания результирующих строк для конкретного языка:

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a>Дополнительные ресурсы

Если вы не знакомы с интерполяцией строк, ознакомьтесь с интерактивным руководством [по интерполяции строк в C#](../../tutorials/exploration/interpolated-strings.yml). Вы также можете изучить другой учебник, [Интерполяция строк в C# ](../../tutorials/string-interpolation.md), в котором показано, как использовать интерполированные строки для форматирования.

## <a name="compilation-of-interpolated-strings"></a>Компиляция интерполированных строк

Если интерполированная строка имеет тип `string`, обычно она преобразуется в вызов метода <xref:System.String.Format%2A?displayProperty=nameWithType>. Компилятор может заменить <xref:System.String.Format%2A?displayProperty=nameWithType> на <xref:System.String.Concat%2A?displayProperty=nameWithType>, если проанализированное поведение будет эквивалентно объединению.

Если интерполированная строка имеет тип <xref:System.IFormattable> или <xref:System.FormattableString>, компилятор создает вызов метода <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType>.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Интерполированные строки](~/_csharplang/spec/expressions.md#interpolated-strings)[спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также раздел

- [справочник по C#](../index.md)
- [Специальные символы C#](index.md)
- [Строки](../../programming-guide/strings/index.md)
- [Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md)
- [Составное форматирование](../../../standard/base-types/composite-formatting.md)
- <xref:System.String.Format%2A?displayProperty=nameWithType>
