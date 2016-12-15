---
title: "Универсальные шаблоны и атрибуты (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "атрибуты [C#], с универсальными"
  - "универсальные шаблоны [C#], атрибуты"
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Универсальные шаблоны и атрибуты (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Атрибуты применяться к универсальным типам таким же образом, как и к нестандартным типам.  Дополнительные сведения о применении атрибутов см. в разделе [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Настраиваемым атрибутам разрешено ссылаться только на открытые универсальные типы \(универсальные типы, для которых не предоставлены аргументы типа\) и закрытые сконструированные универсальные типы \(которые предоставляют аргументы для всех параметров типа\).  
  
 В следующем примере используется этот настраиваемый атрибут:  
  
 [!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 Атрибут может ссылаться на открытый универсальный тип:  
  
 [!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 Укажите несколько параметров типа, используя соответствующее количество запятых.  В данном примере у `GenericClass2` имеется два параметра:  
  
 [!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 Атрибут может ссылаться на закрытый сконструированный универсальный тип:  
  
 [!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 Атрибут, ссылающийся на параметр универсального типа, приведет к ошибке времени компиляции:  
  
 [!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 Универсальный тип не может наследовать от <xref:System.Attribute>:  
  
 [!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 Для получения информации об универсальном типе или параметре типа во время выполнения можно использовать методы <xref:System.Reflection>.  Дополнительные сведения см. в разделе [Универсальные типы и отражение](../../../csharp/programming-guide/generics/generics-and-reflection.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Атрибуты](../Topic/Extending%20Metadata%20Using%20Attributes.md)