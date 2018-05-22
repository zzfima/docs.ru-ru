---
title: $ — интерполяция строк (справочник по C#)
description: Интерполяция строк предоставляет более понятный и удобный синтаксис для форматирования строковых выходных данных, чем традиционное составное форматирование строк.
ms.date: 03/26/2018
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: 407ca9e4744ea9be45867a08e87c502821226472
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2018
---
# <a name="---string-interpolation-c-reference"></a>$ — интерполяция строк (справочник по C#)

Специальный знак `$` идентифицирует строковый литерал как *интерполированную строку*. Интерполированная строка — это строковый литерал, который может содержать *интерполированные выражения*. При разрешении интерполированной строки в результирующую элементы с интерполированными выражениями заменяются строковыми представлениями результатов выражений. Эта возможность доступна в C# 6 и более поздних версиях.

Интерполяция строк предоставляет более понятный и удобный синтаксис для создания форматированных строк по сравнению с функцией [составного форматирования строк](../../../standard/base-types/composite-formatting.md). В следующем примере обе этих функции используются для получения одинаковых выходных данных:

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a>Структура интерполированной строки

Для определения строкового литерала в качестве интерполированной строки добавьте к началу символ `$`. Между `$` и `"` в начале строкового литерала не может быть пробела. Это приводит к ошибке времени компиляции.

Структура элемента с интерполированным выражением выглядит следующим образом:

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

Элементы в квадратных скобках являются необязательными. Каждый из элементов описан в таблице ниже:

|Элемент|Описание:|
|-------------|-----------------|
|`interpolatedExpression`|Выражение, создающее форматируемый результат. Строковым представлением результата `null` является <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|Константное выражение, значение которого определяет минимальное число символов в строковом представлении результата интерполированного выражения. Если оно положительное, строковое представление выравнивается по правому краю, если отрицательное — по левому краю. Дополнительные сведения см. в разделе [Компонент выравнивания](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Строка форматирования, поддерживаемая типом результата выражения. Дополнительные сведения см. в разделе [Компонент строки форматирования](../../../standard/base-types/composite-formatting.md#format-string-component).|

В следующем примере используются необязательные компоненты форматирования, описанные выше:

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a>Специальные символы

Чтобы включить в текст, создаваемый интерполированной строкой, фигурную скобку "{" или "}", используйте две фигурные скобки — "{{" или "}}". Подробнее см. в разделе [Экранирование фигурных скобок](../../../standard/base-types/composite-formatting.md#escaping-braces).

Двоеточие (:) имеет особое значение в элементе интерполированного выражения. Чтобы использовать [условный оператор](../operators/conditional-operator.md) в интерполированном выражении, заключите это выражение в скобки.

В следующем примере показано, как включить фигурную скобку в результирующую строку, а также использовать условный оператор в интерполированном выражении:

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

В интерполированных строках verbatim используется символ `$`, за которым следует символ `@`. Дополнительные сведения о строках Verbatim см. в разделе о [строках](../keywords/string.md) и [идентификаторе verbatim](verbatim.md).

> [!NOTE]
> В интерполированной строке Verbatim токен `$` должен находиться перед токеном `@`.

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a>Неявные преобразования и указание реализации `IFormatProvider`

Существует три неявных преобразования из интерполированных строк.

1. Преобразование интерполированной строки в экземпляр <xref:System.String>, являющийся результатом разрешения интерполированной строки, где элементы интерполированного выражения заменяются на должным образом форматированные строковые представления их результатов. Это преобразование использует текущие значения языка и региональных параметров.

1. Преобразование интерполированной строки в экземпляр <xref:System.FormattableString>, представляющий строку составного формата, а также форматируемые результаты выражения. Это позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.FormattableString>. Для этого вызовите один из следующих методов:

      - Перегрузка <xref:System.FormattableString.ToString>, которая формирует результирующую строку для <xref:System.Globalization.CultureInfo.CurrentCulture>.
      - Метод <xref:System.FormattableString.Invariant%2A>, который формирует результирующую строку для <xref:System.Globalization.CultureInfo.InvariantCulture>.
      - Метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, который формирует результирующую строку для указанного языка и региональных параметров.

    Также можно использовать метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, чтобы предоставить пользовательские реализации интерфейса <xref:System.IFormatProvider>, который поддерживает настраиваемое форматирование. Дополнительные сведения см. в разделе [Настраиваемое форматирование с использованием интерфейса ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).

1. Преобразование интерполированной строки в экземпляр <xref:System.IFormattable>, который также позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.IFormattable>.

В следующем примере используется неявное преобразование в <xref:System.FormattableString> для создания результирующих строк для конкретного языка:

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a>Дополнительные ресурсы

Если вы не знакомы с интерполяцией строк, ознакомьтесь с кратким руководством [по интерполяции строк в C#](../../quick-starts/interpolated-strings.yml). Дополнительные сведения см. в руководстве [Интерполяция строк в C#](../../tutorials/string-interpolation.md).

## <a name="see-also"></a>См. также  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [Составное форматирование](../../../standard/base-types/composite-formatting.md)  
 [Строки](../../programming-guide/strings/index.md)  
 [Руководство по программированию на C#](../../programming-guide/index.md)  
 [Специальные символы в C#](index.md)  
 [Справочник по C#](../index.md)  