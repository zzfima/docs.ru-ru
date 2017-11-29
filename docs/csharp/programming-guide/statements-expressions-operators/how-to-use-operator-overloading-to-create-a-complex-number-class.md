---
title: "Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2053684a9b20c3ec8f4d8ac275832516b3f2c265
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a>Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел (Руководство по программированию в C#)
В этом примере показывается, как использовать перегрузку оператора для создания класса комплексных чисел `Complex`, определяющего сложение комплексных чисел. Программа выводит мнимую и реальную части чисел, а также результат сложения, используя переопределение метода `ToString`.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)  
 [Почему перегруженные операторы всегда являются статическими в C#?](http://go.microsoft.com/fwlink/?LinkId=112383)
