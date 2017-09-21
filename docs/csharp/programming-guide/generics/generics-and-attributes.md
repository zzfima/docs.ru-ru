---
title: "Универсальные шаблоны и атрибуты (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
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
ms.openlocfilehash: 5136ae928a3a4b6f8ec4d86100d695f958d55858
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-attributes-c-programming-guide"></a>Универсальные шаблоны и атрибуты (Руководство по программированию в C#)
Атрибуты можно применять к универсальным типам так же, как и к типам, не являющимся универсальными. Дополнительные сведения о применении атрибутов см. в разделе [Атрибуты](../../../csharp/programming-guide/concepts/attributes/index.md).  
  
 Настраиваемые атрибуты могут ссылаться только на открытые универсальные типы (универсальные типы, для которых не предоставлены аргументы типа) и закрытые сконструированные универсальные типы (типы, для всех параметров типа которых предоставлены аргументы).  
  
 Такой настраиваемый атрибут используется в следующих примерах:  
  
 [!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 Атрибут может ссылаться на открытый универсальный тип:  
  
 [!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 Укажите несколько параметров типа, используя соответствующее количество запятых. В этом примере `GenericClass2` имеет два параметра типа:  
  
 [!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 Атрибут может ссылаться на закрытый сконструированный универсальный тип:  
  
 [!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 Если атрибут ссылается на параметр универсального типа, возникнет ошибка времени компиляции:  
  
 [!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 Универсальный тип не может наследоваться от <xref:System.Attribute>:  
  
 [!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 Для получения сведений об универсальном типе или параметре типа во время выполнения можно использовать методы из <xref:System.Reflection>. Дополнительные сведения см. в разделе [Универсальные типы и отражение](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Атрибуты](https://msdn.microsoft.com/library/5x6cd29c)

