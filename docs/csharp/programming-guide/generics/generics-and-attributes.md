---
title: Руководство по программированию на C#. Универсальные шаблоны и атрибуты
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 99a24a7069145dfad5ce6c9c91f2a8653eb9a224
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589637"
---
# <a name="generics-and-attributes-c-programming-guide"></a>Универсальные шаблоны и атрибуты (Руководство по программированию в C#)
Атрибуты можно применять к универсальным типам так же, как и к типам, не являющимся универсальными. Дополнительные сведения о применении атрибутов см. в разделе [Атрибуты](../concepts/attributes/index.md).  
  
 Настраиваемые атрибуты могут ссылаться только на открытые универсальные типы (универсальные типы, для которых не предоставлены аргументы типа) и закрытые сконструированные универсальные типы (типы, для всех параметров типа которых предоставлены аргументы).  
  
 Такой настраиваемый атрибут используется в следующих примерах:  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 Атрибут может ссылаться на открытый универсальный тип:  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 Укажите несколько параметров типа, используя соответствующее количество запятых. В этом примере `GenericClass2` имеет два параметра типа:  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 Атрибут может ссылаться на закрытый сконструированный универсальный тип:  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 Если атрибут ссылается на параметр универсального типа, возникнет ошибка времени компиляции:  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 Универсальный тип не может наследоваться от <xref:System.Attribute>:  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 Для получения сведений об универсальном типе или параметре типа во время выполнения можно использовать методы из <xref:System.Reflection>. Дополнительные сведения см. в разделе [Универсальные типы и отражение](./generics-and-reflection.md)  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Универсальные шаблоны](./index.md)
- [Атрибуты](../../../standard/attributes/index.md)
