---
title: "implicit (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c893c7a9afbdc6f715010d537e9ccaf66c5785c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-c-reference"></a>implicit (Справочник по C#)
Ключевое слово `implicit` служит для объявления неявного оператора преобразования пользовательского типа. Этот оператор обеспечивает неявное преобразование между пользовательским типом и другим типом, если при преобразовании исключается утрата данных.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 Неявное преобразование позволяет устранить ненужные операции приведения и повышает удобочитаемость исходного кода. Однако поскольку при неявных преобразованиях разработчикам не требуется явным образом приводить один тип к другому, нужно осторожно применять неявные преобразования, чтобы обеспечить правильные результаты. В общем случае операторы неявного преобразования не должны создавать исключений и не должны терять данные, чтобы их можно было безопасно использовать. Если оператор преобразования не соответствует таким условиям, его нужно пометить словом `explicit`. Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)  
 [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)  
 [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
