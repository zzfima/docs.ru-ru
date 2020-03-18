---
title: Интерполяция строк в C#
description: Узнайте, как включить форматированные результаты выражения в строку результатов в C# с интерполяцией строк.
author: pkulikov
ms.technology: csharp-fundamentals
ms.date: 09/02/2019
ms.openlocfilehash: b901ae661ebd4af625d9f3c999b0eb50dda1990d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73039211"
---
# <a name="string-interpolation-in-c"></a>Интерполяция строк на C\#

В этом руководстве описано, как использовать [интерполяцию строк](../language-reference/tokens/interpolated.md) для форматирования и включения результатов выражения в строку результатов. В примерах предполагается, что вам знакомы основные принципы C# и форматирования типов .NET. Если вы не знакомы с интерполяцией строк или форматированием типов .NET, сначала ознакомьтесь с [интерактивным учебником по интерполяции строк](exploration/interpolated-strings.yml). Дополнительные сведения о форматировании типов в .NET см. в разделе [Типы форматирования в .NET](../../standard/base-types/formatting-types.md).

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a>Введение

Функция [интерполяции строк](../language-reference/tokens/interpolated.md) создана на основе функции [составного форматирования](../../standard/base-types/composite-formatting.md) и имеет более удобный синтаксис для включения форматированных результатов выражения в строку результатов.

Для определения строкового литерала в качестве интерполированной строки добавьте к началу символ `$`. Вы можете внедрить любое допустимое выражение C#, возвращающее значение в интерполированной строке. В следующем примере после вычисления выражения его результат преобразуется в строку и включается в строку результатов:

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

Как показано в примере, можно включить выражение в интерполированную строку, заключив его в фигурные скобки:

```csharp
{<interpolationExpression>}
```

Интерполированные строки поддерживают все возможности [составного форматирования строк](../../standard/base-types/composite-formatting.md). Это делает их более удобочитаемыми по сравнению с использованием метода <xref:System.String.Format%2A?displayProperty=nameWithType>.

## <a name="how-to-specify-a-format-string-for-an-interpolation-expression"></a>Как указать строку формата для выражения интерполяции

Задайте строку формата, которая поддерживается типом результата выражения, указав ее после выражения интерполяции через двоеточие:

```csharp
{<interpolationExpression>:<formatString>}
```

В следующем примере показано, как задать стандартные и настраиваемые строки формата для выражений, возвращающих дату и время или числовые результаты:

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

Дополнительные сведения см. в разделе [Компонент строки формата](../../standard/base-types/composite-formatting.md#format-string-component) в статье [Составное форматирование](../../standard/base-types/composite-formatting.md). Этот раздел содержит ссылки на разделы, описывающие стандартные и настраиваемые строки формата, поддерживаемые базовыми типами .NET.

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolation-expression"></a>Управление шириной поля и выравниванием в форматированных выражениях интерполяции

Задайте минимальную ширину поля и выравнивание форматированного результата выражения, указав константное выражение после выражения интерполяции через запятую:

```csharp
{<interpolationExpression>,<alignment>}
```

Если значение *alignment* положительное, форматированное выражение будет выровнено по правому краю, а если отрицательное — по левому.

Если вам нужно задать и выравнивание, и строку формата, начните с компонента выравнивания:

```csharp
{<interpolationExpression>,<alignment>:<formatString>}
```

В следующем примере показано, как задать выравнивание. Текстовые поля разграничены символом вертикальной черты ("|"):

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

В выходных данных в примере видно, что если длина форматированного результата выражения превышает заданную ширину поля, значение *alignment* игнорируется.

Дополнительные сведения см. в разделе [Компонент выравнивания](../../standard/base-types/composite-formatting.md#alignment-component) в статье [Составное форматирование](../../standard/base-types/composite-formatting.md).

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a>Как использовать escape-последовательности в интерполированной строке

Интерполированные строки поддерживают все escape-последовательности, которые могут использоваться в обычных строковых литералах. Дополнительные сведения см. в статье [Escape-последовательности строки](../programming-guide/strings/index.md#string-escape-sequences).

Для литеральной интерпретации escape-последовательности используйте строковый литерал [verbatim](../language-reference/tokens/verbatim.md). Интерполированная строка verbatim начинается с символа `$`, за которым следует символ `@`. Начиная с C# 8.0 маркеры `$` и `@` можно использовать в любом порядке: `$@"..."` и `@$"..."` являются допустимыми интерполированными строками verbatim.

В строке результатов указывайте двойную фигурную скобку "{{" или "}}". Дополнительные сведения см. в разделе [escape-скобки](../../standard/base-types/composite-formatting.md#escaping-braces) в статье [Составное форматирование](../../standard/base-types/composite-formatting.md).

В следующем примере показано, как включить фигурные скобки в строку результата и создать интерполированную строку verbatim:

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolation-expression"></a>Как использовать троичный условный оператор `?:` в выражении интерполяции

Двоеточие (:) имеет особое значение в элементе выражения интерполяции. Чтобы использовать [условный оператор](../language-reference/operators/conditional-operator.md) в выражении, заключите это выражение в скобки, как показано в следующем примере:

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a>Создание строки результата с интерполяцией для определенного языка и региональных параметров

По умолчанию в интерполированной строке используется текущий язык и региональные параметры, определяемые свойством <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> для всех операций форматирования. Используйте неявное преобразование интерполированной строки для экземпляра <xref:System.FormattableString?displayProperty=nameWithType> и вызовите метод <xref:System.FormattableString.ToString(System.IFormatProvider)>, чтобы создать строку результата с определенным языком и региональными параметрами. Следующий пример показывает, как это сделать:

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

Как показано в примере, можно использовать один экземпляр <xref:System.FormattableString> для создания нескольких строк результата для различных языков и региональных параметров.

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a>Как создать строку результата с помощью инвариантного языка и региональных параметров

Наряду с методом <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> можно использовать статический метод <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType>, чтобы разрешить интерполированную строку в строке результата для <xref:System.Globalization.CultureInfo.InvariantCulture>. Следующий пример показывает, как это сделать:

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a>Заключение

В этом руководстве описаны распространенные сценарии использования интерполяции строк. Дополнительные сведения об интерполяции строк см. в разделе [Интерполяция строк](../language-reference/tokens/interpolated.md). Дополнительные сведения о форматировании типов в .NET см. в разделах [Типы форматирования в .NET](../../standard/base-types/formatting-types.md) и [Составное форматирование](../../standard/base-types/composite-formatting.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [Строки](../programming-guide/strings/index.md)
