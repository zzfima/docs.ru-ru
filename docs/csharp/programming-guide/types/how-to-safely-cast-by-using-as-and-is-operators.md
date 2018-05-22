---
title: Практическое руководство. Безопасное приведение с помощью операторов as и is (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
ms.openlocfilehash: 6e02675a2a895add245d3c2e40305a0417fdf429
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a>Практическое руководство. Безопасное приведение с помощью операторов as и is (Руководство по программированию на C#)
В связи с полиморфизмом объектов переменная типа базового класса может содержать производный тип. Для доступа к методу производного типа необходимо привести значение обратно к производному типу. Тем не менее при попытке простого приведения в этих случаях существует риск возникновения исключения <xref:System.InvalidCastException>. Именно поэтому в языке C# реализованы операторы [is](../../../csharp/language-reference/keywords/is.md) и [as](../../../csharp/language-reference/keywords/as.md). С помощью этих операторов можно проверить возможность успешного выполнения приведения без возникновения исключения. В общем случае оператор `as` является более эффективным, поскольку для приведения, которое может быть выполнено успешно, он возвращает фактическое значение приведения. Оператор `is` возвращает только логическое значение. Таким образом, он может использоваться в тех случаях, когда нужно определить тип объекта и не требуется выполнять его фактическое приведение.  
  
## <a name="example"></a>Пример  
 В следующих примерах показано, как использовать операторы `is` и `as` для приведения из одного ссылочного типа к другому без риска возникновения исключения. В этом примере также демонстрируется использование оператора `as` с типами значений, допускающими значения NULL.  
  
 [!code-csharp[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Типы](../../../csharp/programming-guide/types/index.md)  
 [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)
