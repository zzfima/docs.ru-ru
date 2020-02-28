---
title: Практическое руководство. Изменение содержимого строки (руководство по C#)
ms.date: 02/26/2018
helpviewer_keywords:
- strings [C#], modifying
ms.openlocfilehash: ecedd9a9027aa925c753f8e187d611b19d3db991
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543265"
---
# <a name="how-to-modify-string-contents-in-c"></a>Практическое руководство. Изменение содержимого строки в C\#

В этой статье демонстрируется несколько способов получения `string` путем изменения существующего объекта `string`. Все показанные методы возвращают результат изменений как новый объект `string`. Чтобы это было очевидно, во всех примерах результат сохраняется в новой переменной. Затем вы можете изучить исходный объект `string` и объект `string`, полученный в результате изменений при выполнении каждого примера.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

В статье приводится несколько методов. Вы можете заменять существующий текст. Вы можете искать шаблоны и заменять соответствующий текст другим. Вы можете рассматривать строку как последовательность символов. Вы также можете использовать удобные методы удаления пробелов. Выберите метод, наиболее подходящий для вашего сценария.

## <a name="replace-text"></a>Замена текста

Следующий код создает новую строку, заменяя существующий текст.

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#1)]

В коде выше демонстрируется *неизменяемое* свойство строк. В примере видно, что исходная строка `source` не изменяется. Метод <xref:System.String.Replace%2A?displayProperty=nameWithType> создает новый объект `string`, содержащий изменения.

Метод <xref:System.String.Replace%2A> может заменять строки или отдельные символы. В обоих случаях заменяется каждое вхождение искомого текста.  В следующем примере все символы ' ' заменяются на '\_':

[!code-csharp-interactive[replace characters](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#2)]

Исходная строка не изменяется. Возвращается новая строка с заменой.

## <a name="trim-white-space"></a>Усечение пробелов

Используйте методы <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType> и <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> для удаления всех начальных или конечных пробелов.  В приведенном ниже коде показан пример каждого метода. Исходная строка не изменяется. Эти методы возвращают новую строку с измененным содержимым.

[!code-csharp-interactive[trim white space](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#3)]

## <a name="remove-text"></a>Удаление текста

Вы можете удалять из строки текст с помощью метода <xref:System.String.Remove%2A?displayProperty=nameWithType>. Этот метод удаляет определенное число символов, начиная с указанного индекса. В следующем примере показано, как использовать <xref:System.String.IndexOf%2A?displayProperty=nameWithType> с <xref:System.String.Remove%2A> для удаления текста из строки:

[!code-csharp-interactive[remove text](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#4)]

## <a name="replace-matching-patterns"></a>Замена совпадающих шаблонов

Используйте [регулярные выражения](../../standard/base-types/regular-expressions.md) для замены текста, соответствующего шаблонам, на новый текст, который может быть определен шаблоном. В следующем примере используется класс <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> для поиска шаблона в исходной строке и замены его с правильным регистром. Метод <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> принимает в качестве одного из аргументов функцию, которая предоставляет логику замены. В примере эта функция (`LocalReplaceMatchCase`) является **локальной функцией** и объявляется внутри демонстрируемого метода. `LocalReplaceMatchCase` использует класс <xref:System.Text.StringBuilder?displayProperty=nameWithType>, чтобы создать замещающую строку с правильным регистром.

Регулярные выражения наиболее эффективны при поиске и замене текста, который соответствует шаблону, а не известного текста. Дополнительные сведения см. в статье [Практическое руководство. Поиск по строкам](search-strings.md). Шаблон поиска "the\s" ищет слово "the", за которым следует пробел. Эта часть шаблона гарантирует пропуск слова "there" в исходной строке. Дополнительные сведения об элементах языка регулярных выражений см. в разделе [Элементы языка регулярных выражений — краткий справочник](../../standard/base-types/regular-expression-language-quick-reference.md).

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#5)]

Метод <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> возвращает неизменяемую строку с содержимым в объекте <xref:System.Text.StringBuilder>.

## <a name="modifying-individual-characters"></a>Изменение отдельных символов

Вы можете создать из строки массив символов, изменить содержимое массива, а затем создать из измененного содержимого новую строку.

В примере ниже показано, как заменить набор символов в строке. Сначала используется метод <xref:System.String.ToCharArray?displayProperty=nameWithName> для создания массива символов. Для поиска начального индекса слова "fox" используется метод <xref:System.String.IndexOf%2A>. Следующие три символа заменяются другим словом. Наконец, из обновленного массива символов создается новая строка.

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#6)]

## <a name="programmatically-build-up-string-content"></a>Программная сборка содержимого строки

Поскольку строки являются неизменяемыми, в предыдущих примерах создаются временные строки или массивы символов. В высокопроизводительных сценариях может быть желательно избежать этих распределений куч. .NET Core предоставляет метод <xref:System.String.Create%2A?displayProperty=nameWithType>, позволяющий программно заполнять символьное содержимое строки с помощью обратного вызова, избегая промежуточного распределения строк.

[!code-csharp[using string.Create to programmatically build the string content for a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#7)]

Вы можете изменить строку в фиксированном блоке с использованием ненадежного кода, но **крайне** не рекомендует изменять содержимое строки после ее создания. Такая попытка приведет к непредсказуемым последствиям. Например, если кто-то развернет строку, имеющую то же содержимое, что и ваша строка, он получит копию вашей строки и наверняка не будет рассчитывать на то, что вы изменяете его строку.

Вы можете оценить эти примеры, просмотрев код в нашем [репозитории GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings). Или можете загрузить образцы [в ZIP-файле](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).

## <a name="see-also"></a>См. также

- [Регулярные выражения в .NET Framework](../../standard/base-types/regular-expressions.md)
- [Элементы языка регулярных выражений — краткий справочник](../../standard/base-types/regular-expression-language-quick-reference.md)
