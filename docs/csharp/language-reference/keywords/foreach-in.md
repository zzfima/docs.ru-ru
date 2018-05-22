---
title: foreach, in (Справочник по C#)
ms.date: 10/11/2017
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: f00ae873e615f653d3e760f82b157a57fdaef6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="foreach-in-c-reference"></a>foreach, in (Справочник по C#)
Оператор `foreach` повторяет группу встроенных операторов для каждого элемента в массиве или коллекции объектов, которые реализуют интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Оператор `foreach` используется для итерации по коллекции для получения необходимых сведений, однако его нельзя использовать для добавления или удаления элементов из исходной коллекции во избежание непредвиденных побочных эффектов. Если требуется добавить или удалить элементы из исходной коллекции, используйте цикл [for](for.md).
  
 Внедренные операторы продолжают выполняться для каждого элемента массива или коллекции. После завершения итерации для всех элементов коллекции управление передается следующему оператору после блока `foreach`.
  
 В любой момент в блоке `foreach` вы можете прервать цикл с помощью ключевого слова [break](break.md) или перейти к следующей итерации с помощью ключевого слова [continue](continue.md).

 Из цикла `foreach` также можно выйти с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).

 Дополнительные сведения о ключевом слове `foreach` и примеры кода см. в следующих разделах:  

 [Использование оператора foreach с массивами](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [Практическое руководство. Доступ к классу коллекции с помощью оператора foreach](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a>Пример
 В коде ниже приведено три примера.

> [!TIP]
> Вы можете менять примеры, чтобы поэкспериментировать с синтаксисом и попробовать другие варианты использования, более похожие на ваш. Нажмите кнопку Run, чтобы выполнить код, а затем внесите изменения и нажмите кнопку еще раз.

-   типичный цикл `foreach`, который отображает содержимое массива целых чисел;

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   цикл [for](../../../csharp/language-reference/keywords/for.md), который делает то же самое;

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   цикл `foreach`, который ведет подсчет числа элементов в массиве.

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a>Спецификация языка C#
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также  

[Справочник по C#](../index.md)

[Руководство по программированию на C#](../../programming-guide/index.md)

[Ключевые слова в C#](index.md)

[Операторы итерации](iteration-statements.md)

[for](for.md)
