---
title: "operator (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
dev_langs:
- CSharp
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: 19
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
ms.openlocfilehash: 76d403493861e9c587672412cd2989c419b8717a
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="operator-c-reference"></a>operator (Справочник по C#)
Ключевое слово `operator` используется для перегрузки встроенного оператора или выполнения пользовательского преобразования в объявлении класса или структуры.  
  
## <a name="example"></a>Пример  
 Ниже приведен сильно упрощенный класс для дробных чисел. Он перегружает операторы + и * для выполнения сложения и умножения, а также предоставляет оператор преобразования, который преобразует тип Fraction в тип double.  
  
 [!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [implicit](../../../csharp/language-reference/keywords/implicit.md)   
 [explicit](../../../csharp/language-reference/keywords/explicit.md)   
 [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

