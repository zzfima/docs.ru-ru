---
title: "Практическое руководство. Реализация определенных пользователем преобразований между структурами (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
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
ms.openlocfilehash: cc8856bb3bf8943c1b6648f7d81447a3e59b9489
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>Практическое руководство. Реализация определенных пользователем преобразований между структурами (Руководство по программированию на C#)
В этом примере определяются две структуры (`RomanNumeral` и `BinaryNumeral`) и демонстрируются преобразования между ними.  
  
## <a name="example"></a>Пример  
 [!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
-   В предыдущем примере инструкция:  
  
     [!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     выполняет преобразование из `RomanNumeral` в `BinaryNumeral`. Поскольку прямого преобразования из `RomanNumeral` в `BinaryNumeral` не существует, используется приведение для преобразования из `RomanNumeral` в `int` и еще одно приведение для преобразования из `int` в `BinaryNumeral`.  
  
-   Кроме того, инструкция  
  
     [!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     выполняет преобразование из `BinaryNumeral` в `RomanNumeral`. Поскольку `RomanNumeral` определяет неявное преобразование из `BinaryNumeral`, приведение не требуется.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

