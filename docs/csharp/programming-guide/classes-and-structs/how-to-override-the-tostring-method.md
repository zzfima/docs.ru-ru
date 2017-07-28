---
title: "Практическое руководство. Переопределение метода ToString (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 2dde281d439a07d7736949294772a57e926eb587
ms.contentlocale: ru-ru
ms.lasthandoff: 03/24/2017

---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Практическое руководство. Переопределение метода ToString (Руководство по программированию на C#)
Каждый класс или структура в языке C# неявно наследует класс <xref:System.Object>. Поэтому каждый объект в языке C# получает метод <xref:System.Object.ToString%2A>, который возвращает строковое представление данного объекта. Например, все переменные типа `int` имеют метод `ToString`, который позволяет им возвращать их содержимое в виде строки:  
  
 [!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 При создании пользовательского класса или структуры необходимо переопределить метод <xref:System.Object.ToString%2A>, чтобы передать информацию о типе клиентскому коду.  
  
 Дополнительные сведения об использовании строк форматирования и других типов пользовательского форматирования с методом `ToString` см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).  
  
> [!IMPORTANT]
>  При принятии решения относительно того, какая информация должна будет предоставляться посредством этого метода, подумайте, будет ли создаваемый класс или структура когда-либо использоваться ненадежным кодом. Постарайтесь не предоставлять информацию, которая может быть использована вредоносным кодом.  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a>Переопределение метода ToString в классе или структуре  
  
1.  Объявите метод `ToString` со следующими модификаторами и типом возвращаемого значения:  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  Реализуйте этот метод таким образом, чтобы он возвращал строку.  
  
     В приведенном ниже примере возвращается не только имя класса, но и специфические данные для конкретного экземпляра класса.  
  
     [!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     Метод `ToString` можно проверить с помощью показанного ниже кода.  
  
     [!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IFormattable>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [string](../../../csharp/language-reference/keywords/string.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [Типы форматирования](../../../standard/base-types/formatting-types.md)
