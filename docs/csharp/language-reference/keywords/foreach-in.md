---
title: "foreach, in (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aa5408dbe214af2c21edd394f74fb8b675f2a099
ms.lasthandoff: 03/13/2017

---
# <a name="foreach-in-c-reference"></a>foreach, in (Справочник по C#)
Оператор `foreach` повторяет группу внедренных операторов для каждого элемента в массиве или коллекции объектов, которые реализуют интерфейс <xref:System.Collections.IEnumerable?displayProperty=fullName> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>. Оператор `foreach` используется для итерации по коллекции для получения необходимых сведений, однако его нельзя использовать для добавления или удаления элементов из исходной коллекции во избежание непредвиденных побочных эффектов. Если требуется добавить или удалить элементы из исходной коллекции, используйте цикл [for](../../../csharp/language-reference/keywords/for.md).  
  
 Внедренные операторы продолжают выполняться для каждого элемента массива или коллекции. После завершения итерации для всех элементов коллекции управление передается следующему оператору после блока `foreach`.  
  
 В любой момент в блоке `foreach` вы можете прервать цикл с помощью ключевого слова [break](../../../csharp/language-reference/keywords/break.md) или перейти к следующей итерации с помощью ключевого слова [continue](../../../csharp/language-reference/keywords/continue.md).  
  
 Из цикла `foreach` также можно выйти с помощью операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).  
  
 Дополнительные сведения о ключевом слове `foreach` и примеры кода см. в следующих разделах:  
  
 [Использование оператора foreach с массивами](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [Практическое руководство. Доступ к классу коллекции с помощью оператора foreach](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a>Пример  
 В коде ниже приведено три примера:  
  
-   типичный цикл `foreach`, который отображает содержимое массива целых чисел;  
  
-   цикл [for](../../../csharp/language-reference/keywords/for.md), который делает то же самое;  
  
-   цикл `foreach`, который ведет подсчет числа элементов в массиве.  
  
 [!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)   
 [for](../../../csharp/language-reference/keywords/for.md)
