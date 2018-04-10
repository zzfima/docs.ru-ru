---
title: while (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 420b409689d877c3e1ac744e8d7a65500cf8f964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="while-c-reference"></a>while (Справочник по C#)
Оператор `while` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>Пример  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>Пример  
 Значение выражения `while` проверяется перед каждым выполнением цикла, поэтому цикл `while` выполняется ноль или несколько раз. Это отличает его от цикла [do](../../../csharp/language-reference/keywords/do.md), который выполняется от одного до нескольких раз.  
  
 Цикл `while` может быть завершен, если оператор [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md) передает управление за пределы цикла. Чтобы передать управление в следующую итерацию без выхода из цикла, используйте оператор [continue](../../../csharp/language-reference/keywords/continue.md). Обратите внимание на разницу в результатах трех предыдущих примеров, которые зависят от места увеличения `int n`. В приведенном ниже примере результат отсутствует.  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Оператор while (C++)](/cpp/cpp/while-statement-cpp)  
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)
