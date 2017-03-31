---
title: "Оси LINQ to XML (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 3f7d54ff-b608-43a1-9e2d-e70668b72df8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 696a9057d5eb9d2a8c3a263c02571a0913af89f3
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-axes-c"></a>Оси LINQ to XML (C#)
После создания XML-дерева или загрузки XML-документа в XML-дерево можно опросить его для поиска элементов и атрибутов и извлечения их значений.  
  
 Перед составлением каких-либо запросов необходимо понять назначение осей [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Существуют два вида методов оси. Во-первых, это методы, которые вызываются для одного объекта <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> или <xref:System.Xml.Linq.XNode>. Эти методы работают с одним объектом и возвращают коллекцию объектов <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> или <xref:System.Xml.Linq.XNode>. Во-вторых, существуют методы расширения, работающие с коллекциями и возвращающие коллекции. В этих методах расширения создается перечисление исходной коллекции, вызывается соответствующий метод оси применительно к каждому элементу коллекции и осуществляется объединение результатов.  
  
## <a name="in-this-section"></a>Содержание  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Общие сведения об осях LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Определяет оси и содержит описание того, как они используются в контексте запросов [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].|  
|[Практическое руководство. Извлечение коллекции элементов (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Представляет метод <xref:System.Xml.Linq.XContainer.Elements%2A>. Этот метод получает коллекцию дочерних элементов того или иного элемента.|  
|[Практическое руководство. Извлечение значений элемента (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Показывает способ получения значений элементов.|  
|[Практическое руководство. Фильтрация по именам элементов (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Показывает способ фильтрации по именам элементов при использовании осей.|  
|[Практическое руководство. Связанные вызовы метода оси (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Показывает, как соединять в цепочку вызовы для методов осей.|  
|[Практическое руководство. Извлечение одного дочернего элемента (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Показывает способ получения одного дочернего элемента того или иного элемента по имени тега дочернего элемента.|  
|[Практическое руководство. Извлечение коллекции атрибутов (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Представляет метод <xref:System.Xml.Linq.XElement.Attributes%2A>. Этот метод извлекает атрибуты того или иного элемента.|  
|[Практическое руководство. Извлечение одного атрибута (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Показывает способ получения одного атрибута элемента по имени атрибута.|  
|[Практическое руководство. Получение значения атрибута (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Показывает способ получения значений атрибутов.|  
|[Практическое руководство. Извлечение поверхностного значения элемента (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Показывает способ получения поверхностного значения элемента.|  
  
## <a name="see-also"></a>См. также  
 [Методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [Руководство по программированию (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
