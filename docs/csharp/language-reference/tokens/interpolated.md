---
title: $ — интерполяция строк (справочник по C#)
description: Интерполяция строк предоставляет более понятный и удобный синтаксис для форматирования строковых выходных данных, чем традиционное составное форматирование строк.
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cabb40c9c449780c8c2a504aad3e53938e2ed957
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="---string-interpolation-c-reference"></a>$ — интерполяция строк (справочник по C#)

Специальный знак `$` идентифицирует строковый литерал как *интерполированную строку*. Интерполированное строковое выражение выглядит как строка шаблона, которая содержит *интерполированные выражения*. При разрешении интерполированной строки в результирующую элементы с интерполированными выражениями заменяются строковыми представлениями результатов выражений. Эта возможность доступна в C# 6 и более поздних версиях.

Интерполяция строк предоставляет более понятный и удобный синтаксис для создания форматированных строк по сравнению с функцией [составного форматирования строк](../../../standard/base-types/composite-formatting.md). В следующем примере обе этих функции используются для получения одинаковых выходных данных:

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> Между `$` и `"` в начале строки не может быть пробела. Это приводит к ошибке времени компиляции.

Структура элемента с интерполированным выражением выглядит следующим образом:

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

Элементы в квадратных скобках являются необязательными. Каждый из элементов описан в таблице ниже.

|Элемент|Описание:|
|-------------|-----------------|
|`interpolatedExpression`|Выражение, вычисляемое для получения форматируемого результата. Строковым представлением результата `null` является <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|Константное выражение, значение которого определяет минимальное число символов в строковом представлении результата интерполированного выражения. Если оно положительное, строковое представление выравнивается по правому краю, если отрицательное — по левому краю. Дополнительные сведения см. в разделе [Компонент выравнивания](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Стандартная или пользовательская строка форматирования, поддерживаемая типом результата выражения. Дополнительные сведения см. в разделе [Компонент строки форматирования](../../../standard/base-types/composite-formatting.md#format-string-component).|

В следующем примере используются необязательные компоненты форматирования, описанные выше:

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

Чтобы включить в текст, создаваемый интерполированной строкой, фигурную скобку ("{" или "}"), используйте две фигурные скобки — "{{" или "}}". Подробнее см. в разделе [Экранирование фигурных скобок](../../../standard/base-types/composite-formatting.md#escaping-braces).

Двоеточие (:) имеет особое значение в элемент интерполированного выражения. Чтобы использовать [условный оператор](../operators/conditional-operator.md) в интерполированном выражении, заключите это выражение в скобки.

В следующем примере показано, как включить фигурную скобку в результирующую строку, а также использовать условный оператор в интерполированном выражении:

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

В интерполированных строках Verbatim используется символ `$`, за которым следует символ `@`. Дополнительные сведения о строках Verbatim см. в разделе о [строках](../keywords/string.md).

> [!NOTE]
> В интерполированной строке Verbatim токен `$` должен находиться перед токеном `@`.

Существует три неявных преобразования из интерполированных строк.

1. Преобразование интерполированной строки в экземпляр <xref:System.String>, являющийся результатом разрешения интерполированной строки, где элементы интерполированного выражения заменяются на должным образом форматированные строковые представления их результатов. Это преобразование использует текущие значения языка и региональных параметров.

1. Преобразование интерполированной строки в экземпляр <xref:System.FormattableString>, представляющий строку составного формата, а также форматируемые результаты выражения. Это позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.FormattableString>. Для этого вызовите один из следующих методов:

      - Перегрузка <xref:System.FormattableString.ToString>, которая формирует результирующую строку для <xref:System.Globalization.CultureInfo.CurrentCulture>.
      - Метод <xref:System.FormattableString.Invariant%2A>, который формирует результирующую строку для <xref:System.Globalization.CultureInfo.InvariantCulture>.
      - Метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, который формирует результирующую строку для указанного языка и региональных параметров.

1. Преобразование интерполированной строки в экземпляр <xref:System.IFormattable>, который также позволяет создавать несколько результирующих строк с содержимым для конкретного языка из одного экземпляра <xref:System.IFormattable>.

В следующем примере используется неявное преобразование в <xref:System.FormattableString> для создания результирующих строк для конкретного языка:

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

Если вы не знакомы с интерполяцией строк, ознакомьтесь с кратким руководством [по интерполяции строк в C#](../../quick-starts/interpolated-strings.yml). Дополнительные сведения см. в [учебнике по интерполяции строк](../../tutorials/string-interpolation.md).

## <a name="see-also"></a>См. также  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [Составное форматирование](../../../standard/base-types/composite-formatting.md)  
 [Строки](../../../csharp/programming-guide/strings/index.md)  
 [Специальные символы в C#](../../../csharp/language-reference/tokens/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Справочник по C#](../../../csharp/language-reference/index.md)  