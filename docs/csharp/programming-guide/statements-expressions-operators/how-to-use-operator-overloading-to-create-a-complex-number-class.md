---
title: Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
ms.openlocfilehash: d746355dac1b99690a5a94c829bd35598c6c8be8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328868"
---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a>Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел (Руководство по программированию в C#)
В этом примере показывается, как использовать перегрузку оператора для создания класса комплексных чисел `Complex`, определяющего сложение комплексных чисел. Программа выводит мнимую и реальную части чисел, а также результат сложения, используя переопределение метода `ToString`.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)  
 [Почему перегруженные операторы всегда являются статическими в C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
