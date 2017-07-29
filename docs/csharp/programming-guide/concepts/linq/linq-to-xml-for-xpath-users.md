---
title: "LINQ to XML для пользователей XPath (C#)"
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
ms.assetid: 91774511-1dca-4f06-ac0b-913746f104fe
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4d350826d23e31463666ee4bd861867b6c40eb55
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-xml-for-xpath-users-c"></a>LINQ to XML для пользователей XPath (C#)
В данном ряде разделов показаны несколько выражений XPath и их эквиваленты [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Во всех примерах используются функции XPath, поддерживаемые технологией [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], доступ к которым предоставляется с помощью методов расширения в <xref:System.Xml.XPath.Extensions?displayProperty=fullName>. В этих примерах происходит выполнение и выражения XPath, и выражения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Затем в каждом примере сравниваются результаты обоих запросов для проверки того, что выражение XPath является функционально эквивалентным запросу [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Так как оба типа запросов возвращают узлы из одного XML-дерева, сравнение результатов запросов выполняется с помощью ссылочного идентификатора.  
  
## <a name="in-this-section"></a>Содержание  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Сравнительные характеристики XPath и LINQ to XML](../../../../csharp/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Содержит общие сведения о подобиях и различиях между XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Практическое руководство. Поиск дочернего элемента (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|Сравнивает ось дочернего элемента XPath с предусмотренным в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] методом <xref:System.Xml.Linq.XContainer.Element%2A>.<br /><br /> Связанным выражением XPath является `"DeliveryNotes"`.|  
|[Практическое руководство. Поиск списка дочерних элементов (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Сравнивает ось дочернего элемента XPath с предусмотренной в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XContainer.Elements%2A>.<br /><br /> Связанное выражение XPath:`"./*"`|  
|[Практическое руководство. Поиск корневого элемента (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|Сравнивает способы получения корневого элемента при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"/PurchaseOrders"`|  
|[Практическое руководство. Поиск элементов-потомков (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков с определенным именем при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"//Name"`|  
|[Практическое руководство. Фильтрация по атрибуту (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков с указанным именем и атрибутом с заданным значением с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`".//Address[@Type='Shipping']"`|  
|[Практическое руководство. Поиск связанных элементов (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|Сравнивает способы получения элемента по атрибуту, на который ссылается значение другого элемента, с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[Практическое руководство. Поиск элементов в пространстве имен (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace-xpath-linq-to-xml.md)|Сравнивает использование класса XPath <xref:System.Xml.XmlNamespaceManager> со свойством [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> класса <xref:System.Xml.Linq.XName> для работы с пространствами имен XML.<br /><br /> Связанное выражение XPath:`"./aw:*"`|  
|[Практическое руководство. Поиск предшествующих элементов того же уровня (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Сравнивает ось `preceding-sibling` XPath с дочерней по отношению к [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>.<br /><br /> Связанное выражение XPath:`"preceding-sibling::*"`|  
|[Практическое руководство. Поиск потомков дочернего элемента (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков дочернего элемента с определенным именем при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"./Paragraph//Text/text()"`|  
|[Практическое руководство. Поиск объединения двух путей расположения (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml.md)|Сравнивает использование оператора объединения `&#124;` в XPath со стандартным оператором запросов <xref:System.Linq.Enumerable.Concat%2A> в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"//Category&#124;//Price"`|  
|[Практическое руководство. Поиск одноуровневых узлов (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Сравнивает способы нахождения с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] всех одноуровневых объектов узла с указанным именем.<br /><br /> Связанное выражение XPath:`"../Book"`|  
|[Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Сравнивает способы перехода к родительскому элементу и поиска связанного атрибута с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"../@id"`|  
|[Практическое руководство. Поиск атрибутов элементов того же уровня с определенным именем (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml.md)|Сравнивает способы поиска определенных атрибутов одноуровневых объектов контекстного узла при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"``../Book/@id``"`|  
|[Практическое руководство. Поиск элементов с определенным атрибутом (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml.md)|Сравнивает способы получения всех элементов, содержащих определенный атрибут, с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"./*[@Select]"`|  
|[Практическое руководство. Поиск дочерних элементов по положению (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position-xpath-linq-to-xml.md)|Сравнивает способы поиска элемента на основе его относительного расположения с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"Test[position() >= 2 and position() <= 4]"`|  
|[Практическое руководство. Поиск ближайшего предшествующего элемента того же уровня (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Сравнивает способы нахождения ближайшего предшествующего одноуровневого элемента узла с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.XPath?displayProperty=fullName>   
 [Выполнение запросов к деревьям XML (C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)   
 [Обработка XML-данных с использованием модели данных XPath](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)

