---
title: while (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 23c5ca3bb7dc401a894a6c3918fbaec9a9306153
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
