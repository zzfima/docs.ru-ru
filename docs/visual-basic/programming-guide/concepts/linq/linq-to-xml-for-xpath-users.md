---
title: "LINQ to XML для пользователей XPath (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 376e7d67edf1719dc1a020974b38e3600831d660
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ to XML для пользователей XPath (Visual Basic)
В данном ряде разделов показаны несколько выражений XPath и их эквиваленты [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Все примеры используют функциональность XPath в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] , доступные с помощью методов расширения в <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName> В этих примерах происходит выполнение и выражения XPath, и выражения [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Затем в каждом примере сравниваются результаты обоих запросов для проверки того, что выражение XPath является функционально эквивалентным запросу [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Так как оба типа запросов возвращают узлы из одного XML-дерева, сравнение результатов запросов выполняется с помощью ссылочного идентификатора.  
  
## <a name="in-this-section"></a>Содержание  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Сравнительные характеристики XPath и LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Содержит общие сведения о подобиях и различиях между XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].|  
|[Практическое руководство: поиск дочернего элемента (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|Сравнивает ось дочернего элемента XPath с [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XContainer.Element%2A>метод.</xref:System.Xml.Linq.XContainer.Element%2A><br /><br /> Связанным выражением XPath является `"DeliveryNotes"`.|  
|[Практическое руководство: поиск списка дочерних элементов (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Сравнивает ось дочернего элемента XPath [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A>оси.</xref:System.Xml.Linq.XContainer.Elements%2A><br /><br /> Связанное выражение XPath:`"./*"`|  
|[Практическое руководство: поиск корневого элемента (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|Сравнивает способы получения корневого элемента при помощи XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`"/PurchaseOrders"`|  
|[Практическое руководство: поиск элементов-потомков (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков с определенным именем при помощи XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`"//Name"`|  
|[Практическое руководство: фильтрацию по атрибуту (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков с указанным именем и атрибутом с заданным значением с помощью XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`".//Address[@Type='Shipping']"`|  
|[Практическое руководство: поиск связанных элементов (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|Сравнивает способы получения элемента по атрибуту, на который ссылается значение другого элемента, с помощью XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[Практическое руководство: поиск элементов в пространстве имен (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace.md)|Сравнивает использование класса XPath <xref:System.Xml.XmlNamespaceManager>класса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XName.Namespace%2A>Свойства <xref:System.Xml.Linq.XName>класс для работы с пространствами имен XML.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName.Namespace%2A> </xref:System.Xml.XmlNamespaceManager><br /><br /> Связанное выражение XPath:`"./aw:*"`|  
|[Практическое руководство: поиск предшествующего одноуровневого узла (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Сравнивает выражение XPath `preceding-sibling` ось [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] дочерних <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>оси.</xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName><br /><br /> Связанное выражение XPath:`"preceding-sibling::*"`|  
|[Практическое руководство: поиск потомков дочернего элемента (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков дочернего элемента с определенным именем при помощи XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`"./Paragraph//Text/text()"`|  
|[Практическое руководство: поиск объединения двух путей расположения (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath.md)|Сравнивает использование оператора объединения, `&#124;`, в XPath со <xref:System.Linq.Enumerable.Concat%2A>стандартного оператора запроса в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Linq.Enumerable.Concat%2A><br /><br /> Связанное выражение XPath:`"//Category&#124;//Price"`|  
|[Практическое руководство: поиск одноуровневых узлов (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Сравнивает способы нахождения с помощью XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] всех одноуровневых объектов узла с указанным именем.<br /><br /> Связанное выражение XPath:`"../Book"`|  
|[Практическое руководство: поиск атрибута родительского элемента (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Сравнивает способы перехода к родительскому элементу и поиска связанного атрибута с помощью XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`"../@id"`|  
|[Практическое руководство: найти атрибуты одноуровневых узлов с определенным именем (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name.md)|Сравнивает способы поиска определенных атрибутов одноуровневых объектов контекстного узла при помощи XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`"``../Book/@id``"`|  
|[Практическое руководство: поиск элементов с определенным атрибутом (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute.md)|Сравнивает способы получения всех элементов, содержащих определенный атрибут, с помощью XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`"./*[@Select]"`|  
|[Практическое руководство: поиск дочерних элементов по положению (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position.md)|Сравнивает способы поиска элемента на основе его относительного расположения с помощью XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`"Test[position() >= 2 and position() <= 4]"`|  
|[Практическое руководство: найти ближайший предшествующий одноуровневый элемент (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Сравнивает способы нахождения ближайшего предшествующего одноуровневого элемента узла с помощью XPath и [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Связанное выражение XPath:`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.XPath?displayProperty=fullName></xref:System.Xml.XPath?displayProperty=fullName>   
 [Выполнение запросов деревьям XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)   
 [Обработка XML-данных с помощью модели данных XPath](http://msdn.microsoft.com/library/536c6fce-1453-4654-9c72-bca54d47e081)
