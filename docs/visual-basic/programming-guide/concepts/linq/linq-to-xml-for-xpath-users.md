---
title: LINQ to XML для пользователей XPath
ms.date: 07/20/2015
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
ms.openlocfilehash: 4d5749e72acc8b051db2180b751051696ae04d57
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345471"
---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ to XML for XPath Users (Visual Basic)

В данном ряде разделов показаны несколько выражений XPath и их эквиваленты [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Во всех примерах используются функции XPath, поддерживаемые технологией [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], доступ к которым предоставляется с помощью методов расширения в <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>. В этих примерах происходит выполнение и выражения XPath, и выражения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Затем в каждом примере сравниваются результаты обоих запросов для проверки того, что выражение XPath является функционально эквивалентным запросу [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Так как оба типа запросов возвращают узлы из одного XML-дерева, сравнение результатов запросов выполняется с помощью ссылочного идентификатора.  
  
## <a name="in-this-section"></a>Содержание  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Сравнительные характеристики XPath и LINQ to XML](../../../../csharp/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Содержит общие сведения о подобиях и различиях между XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[How to: Find a Child Element (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|Сравнивает ось дочернего элемента XPath с предусмотренным в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] методом <xref:System.Xml.Linq.XContainer.Element%2A>.<br /><br /> Связанным выражением XPath является `"DeliveryNotes"`.|  
|[How to: Find a List of Child Elements (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Сравнивает ось дочернего элемента XPath с предусмотренной в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XContainer.Elements%2A>.<br /><br /> Связанное выражение XPath:`"./*"`|  
|[How to: Find the Root Element (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|Сравнивает способы получения корневого элемента при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"/PurchaseOrders"`|  
|[How to: Find Descendant Elements (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков с определенным именем при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"//Name"`|  
|[How to: Filter on an Attribute (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков с указанным именем и атрибутом с заданным значением с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"./Address[@Type='Shipping']"`|  
|[How to: Find Related Elements (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|Сравнивает способы получения элемента по атрибуту, на который ссылается значение другого элемента, с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"./Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[How to: Find Elements in a Namespace (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace.md)|Сравнивает использование класса XPath <xref:System.Xml.XmlNamespaceManager> со свойством [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> класса <xref:System.Xml.Linq.XName> для работы с пространствами имен XML.<br /><br /> Связанное выражение XPath:`"./aw:*"`|  
|[How to: Find Preceding Siblings (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Сравнивает ось `preceding-sibling` XPath с дочерней по отношению к [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>.<br /><br /> Связанное выражение XPath:`"preceding-sibling::*"`|  
|[How to: Find Descendants of a Child Element (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков дочернего элемента с определенным именем при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"./Paragraph//Text/text()"`|  
|[How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath.md)|Сравнивает использование оператора объединения <code>&#124;</code> в XPath со стандартным оператором запросов <xref:System.Linq.Enumerable.Concat%2A> в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:<code>"//Category&#124;//Price"</code>|  
|[How to: Find Sibling Nodes (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Сравнивает способы нахождения с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] всех одноуровневых объектов узла с указанным именем.<br /><br /> Связанное выражение XPath:`"../Book"`|  
|[How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Сравнивает способы перехода к родительскому элементу и поиска связанного атрибута с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"../@id"`|  
|[How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name.md)|Сравнивает способы поиска определенных атрибутов одноуровневых объектов контекстного узла при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"../Book/@id"`|  
|[How to: Find Elements with a Specific Attribute (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute.md)|Сравнивает способы получения всех элементов, содержащих определенный атрибут, с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"./*[@Select]"`|  
|[How to: Find Child Elements Based on Position (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position.md)|Сравнивает способы поиска элемента на основе его относительного расположения с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"Test[position() >= 2 and position() <= 4]"`|  
|[How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Сравнивает способы нахождения ближайшего предшествующего одноуровневого элемента узла с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.XPath?displayProperty=nameWithType>
- [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
- [Обработка XML-данных с использованием модели данных XPath](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
