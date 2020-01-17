---
title: Практическое руководство. Сцепка нескольких строк (руководство по C#)
description: C# поддерживает различные способы сцепки строк. Узнайте, какие доступны варианты и как выбирать между ними.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: 9a0640a7ce73fa8454442cd301157bf5c265f9de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713901"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a>Практическое руководство. Сцепка нескольких строк (руководство по C#)

*Объединение* подразумевает добавление одной строки к концу другой. Вы можете сцеплять строки с помощью оператора `+`. Строковые литералы и константы сцепляются во время компиляции, а не во время выполнения. Строковые переменные сцепляются только во время выполнения.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Следующий пример показывает использование сцепки для разделения длинного строкового литерала на строки меньшего размера, чтобы повысить удобочитаемость исходного кода. Эти части объединяются в одну строку во время компиляции. Количество строк не влияет на производительность во время выполнения.  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  

Для сцепки строковых переменных вы можете использовать операторы `+` или `+=`, [интерполяцию строк](../language-reference/tokens/interpolated.md), а также методы <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> или <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>. Оператор `+` прост в использовании и позволяет получить интуитивно понятный код. Даже если в одном выражении используется несколько операторов `+`, содержимое строки копируется только один раз. В следующем коде показаны примеры использования операторов `+` и `+=` для сцепки строк:

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

В некоторых выражениях строки проще сцепить с помощью интерполяции, как показано в следующем коде:
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
> В операциях сцепки строк компилятор C# обрабатывает строки NULL так же, как пустые строки.

Другие методы сцепки строк: <xref:System.String.Format%2A?displayProperty=nameWithType>. Этот метод лучше использовать при создании строки из небольшого числа строк-компонентов.

В других случаях вы можете сцеплять строки во время цикла и не знать, сколько исходных строк вы сцепляете. При этом фактическое число исходных строк может быть довольно большим. Для этих сценариев предназначен класс <xref:System.Text.StringBuilder>. В следующем коде для сцепки строк используется метод <xref:System.Text.StringBuilder.Append%2A> класса <xref:System.Text.StringBuilder>.  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

См. дополнительные сведения о [причинах для выбора объединения строк или класса `StringBuilder` ](xref:System.Text.StringBuilder#StringAndSB).

Другой вариант объединения строк из коллекции — использовать метод <xref:System.String.Concat%2A?displayProperty=nameWithType>. Используйте метод <xref:System.String.Join%2A?displayProperty=nameWithType>, если исходные строки должны быть разделены разделителем. Следующий код объединяет массив слов с помощью обоих методов:

[!code-csharp-interactive[concatenation of string collection](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]

Другой вариант объединения строк из коллекции — использовать [LINQ](../programming-guide/concepts/linq/index.md) и метод <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>. Этот метод объединяет исходные строки с помощью лямбда-выражения. Лямбда-выражение добавляет каждую строку к существующему накоплению. Следующий пример показывает объединение массива слов путем добавления пробелов между словами.

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#6)]  

Вы можете оценить эти примеры, просмотрев код в нашем [репозитории GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings). Или можете загрузить образцы [в ZIP-файле](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).

## <a name="see-also"></a>См. также

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [Руководство по программированию на C#](../programming-guide/index.md)
- [Строки](../programming-guide/strings/index.md)
