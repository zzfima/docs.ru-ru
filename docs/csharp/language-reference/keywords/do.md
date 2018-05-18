---
title: do (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5599f079e29fd094c4d6a6a75afba89fb562a166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="do-c-reference"></a>do (Справочник по C#)
Оператор `do` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`. Тело цикла должно быть заключено в фигурные скобки `{}`, если оно не состоит из одного оператора. В этом случае фигурные скобки необязательны.  
  
## <a name="example"></a>Пример  
 В следующем примере операторы цикла `do-while` выполняются до тех пор, пока значение переменной `x` остается меньше 5.  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 В отличие от оператора [while](../../../csharp/language-reference/keywords/while.md), цикл `do-while` выполняется один раз до вычисления значения условного выражения.  
  
 В любой точке блока `do-while` можно разорвать цикл с помощью оператора [break](../../../csharp/language-reference/keywords/break.md). Можно перейти непосредственно к оператору оценки выражения `while`, воспользовавшись оператором [continue](../../../csharp/language-reference/keywords/continue.md). Если выражение `while` принимает значение true, выполнение продолжается с первого оператора цикла. Если выражение принимает значение false, выполнение продолжается в первом операторе после цикла `do-while`.  
  
 Из цикла `do-while` также можно выйти с помощью операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Оператор do-while (C)](/cpp/cpp/do-while-statement-cpp)  
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)
