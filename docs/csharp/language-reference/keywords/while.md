---
title: "while (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
dev_langs:
- CSharp
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ed531c83dba02b38576bf8354b1ff92f075048bc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="while-c-reference"></a>while (Справочник по C#)
Оператор `while` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`.  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>Пример  
 Значение выражения `while` проверяется перед каждым выполнением цикла, поэтому цикл `while` выполняется ноль или несколько раз. Это отличает его от цикла [do](../../../csharp/language-reference/keywords/do.md), который выполняется от одного до нескольких раз.  
  
 Цикл `while` может быть завершен, если оператор [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md) передает управление за пределы цикла. Чтобы передать управление в следующую итерацию без выхода из цикла, используйте оператор [continue](../../../csharp/language-reference/keywords/continue.md). Обратите внимание на разницу в результатах трех предыдущих примеров, которые зависят от места увеличения `int n`. В приведенном ниже примере результат отсутствует.  
  
 [!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Оператор while (C++)](/cpp/cpp/while-statement-cpp)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)

