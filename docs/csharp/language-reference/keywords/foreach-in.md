---
title: "foreach, in (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "foreach"
  - "foreach_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "foreach - ключевое слово [C#]"
  - "foreach - оператор [C#]"
  - "in - ключевое слово [C#]"
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# foreach, in (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `foreach` повторяет группу вложенных операторов для каждого элемента массива или коллекции объектов, реализующих интерфейс <xref:System.Collections.IEnumerable?displayProperty=fullName> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>.  Оператор `foreach` используется для итерации коллекции с целью получения необходимой информации, однако его не следует использовать для добавления или удаления элементов исходной коллекции во избежание непредвиденных побочных эффектов.  Если нужно добавить или удалить элементы исходной коллекции, следует использовать цикл [for](../../../csharp/language-reference/keywords/for.md).  
  
 Внедренные операторы продолжают выполняться для каждого элемента массива или коллекции.  После завершения итерации всех элементов коллекции управление переходит к следующему оператору после блока `foreach`.  
  
 В любой точке блока `foreach` можно разорвать цикл с помощью ключевого слова [break](../../../csharp/language-reference/keywords/break.md) или перейти к следующей итерации в цикле с помощью ключевого слова [continue](../../../csharp/language-reference/keywords/continue.md).  
  
 Цикл `foreach` также можно разорвать посредством операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).  
  
 Дополнительные сведения о ключевом слове `foreach` и примеры кода приведены в следующих разделах:  
  
 [Использование оператора foreach с массивами](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [Практическое руководство. Доступ к классу коллекции с помощью оператора foreach](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## Пример  
 Следующий код показывает три примера.  
  
-   Типичный цикл `foreach`, который отображает содержимое массива целых чисел  
  
-   цикл [for](../../../csharp/language-reference/keywords/for.md), который делает то же самое  
  
-   цикл `foreach`, который ведет подсчет количества элементов в массиве  
  
 [!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)   
 [for](../../../csharp/language-reference/keywords/for.md)