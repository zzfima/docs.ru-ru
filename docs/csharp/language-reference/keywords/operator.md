---
title: operator (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: d633a46e21f913aa8c05289dccfb63e71efd697e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267952"
---
# <a name="operator-c-reference"></a>operator (Справочник по C#)
Ключевое слово `operator` используется для перегрузки встроенного оператора или выполнения пользовательского преобразования в объявлении класса или структуры.  
  
## <a name="example"></a>Пример  
 Ниже приведен сильно упрощенный класс для дробных чисел. Он перегружает операторы `+` и `*` для выполнения сложения и умножения, а также предоставляет оператор преобразования, который преобразует тип `Fraction` в тип `double`.  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [implicit](../../../csharp/language-reference/keywords/implicit.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)  
 [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
