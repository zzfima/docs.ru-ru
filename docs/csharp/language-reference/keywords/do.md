---
title: "do (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
dev_langs:
- CSharp
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
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
ms.openlocfilehash: 58a9361c440bc1b17c5ab929ff7b45ba71ce50a4
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="do-c-reference"></a>do (Справочник по C#)
Оператор `do` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`. Тело цикла должно быть заключено в фигурные скобки `{}`, если оно не состоит из одного оператора. В этом случае фигурные скобки необязательны.  
  
## <a name="example"></a>Пример  
 В следующем примере операторы цикла `do-while` выполняются до тех пор, пока значение переменной `x` остается меньше 5.  
  
 [!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 В отличие от оператора [while](../../../csharp/language-reference/keywords/while.md), цикл `do-while` выполняется один раз до вычисления значения условного выражения.  
  
 В любой точке блока `do-while` можно разорвать цикл с помощью оператора [break](../../../csharp/language-reference/keywords/break.md). Можно перейти непосредственно к оператору оценки выражения `while`, воспользовавшись оператором [continue](../../../csharp/language-reference/keywords/continue.md). Если выражение `while` принимает значение true, выполнение продолжается с первого оператора цикла. Если выражение принимает значение false, выполнение продолжается в первом операторе после цикла `do-while`.  
  
 Из цикла `do-while` также можно выйти с помощью операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Оператор do-while (C++)](/cpp/cpp/do-while-statement-cpp)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)

