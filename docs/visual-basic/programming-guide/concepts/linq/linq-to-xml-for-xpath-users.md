---
title: "LINQ to XML для пользователей XPath (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb0666ee1ae5626a4721ea597a53889e1acf8b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ to XML для пользователей XPath (Visual Basic)

В данном ряде разделов показаны несколько выражений XPath и их эквиваленты [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Во всех примерах используются функции XPath, поддерживаемые технологией [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], доступ к которым предоставляется с помощью методов расширения в <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>. В этих примерах происходит выполнение и выражения XPath, и выражения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Затем в каждом примере сравниваются результаты обоих запросов для проверки того, что выражение XPath является функционально эквивалентным запросу [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Так как оба типа запросов возвращают узлы из одного XML-дерева, сравнение результатов запросов выполняется с помощью ссылочного идентификатора.  
  
## <a name="in-this-section"></a>Содержание  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Сравнительные характеристики XPath и LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Содержит общие сведения о подобиях и различиях между XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Как: поиск дочернего элемента (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|Сравнивает ось дочернего элемента XPath с предусмотренным в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] методом <xref:System.Xml.Linq.XContainer.Element%2A>.<br /><br /> Связанным выражением XPath является `"DeliveryNotes"`.|  
|[Как: поиск списка дочерних элементов (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Сравнивает ось дочернего элемента XPath с предусмотренной в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XContainer.Elements%2A>.<br /><br /> Связанное выражение XPath:`"./*"`|  
|[Как: поиск корневого элемента (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|Сравнивает способы получения корневого элемента при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"/PurchaseOrders"`|  
|[Как: поиск элементов-потомков (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков с определенным именем при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"//Name"`|  
|[Как: фильтрация по атрибуту (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков с указанным именем и атрибутом с заданным значением с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`".//Address[@Type='Shipping']"`|  
|[Как: поиск связанных элементов (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|Сравнивает способы получения элемента по атрибуту, на который ссылается значение другого элемента, с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[Как: поиск элементов в пространстве имен (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace.md)|Сравнивает использование класса XPath <xref:System.Xml.XmlNamespaceManager> со свойством [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> класса <xref:System.Xml.Linq.XName> для работы с пространствами имен XML.<br /><br /> Связанное выражение XPath:`"./aw:*"`|  
|[Как: поиск предшествующего одноуровневого узла (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Сравнивает ось `preceding-sibling` XPath с дочерней по отношению к [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] осью <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>.<br /><br /> Связанное выражение XPath:`"preceding-sibling::*"`|  
|[Как: поиск потомков дочернего элемента (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Сравнивает способы получения элементов-потомков дочернего элемента с определенным именем при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"./Paragraph//Text/text()"`|  
|[Как: поиск объединения двух путей расположения (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath.md)|Сравнивает использование оператора объединения <code>&#124;</code> в XPath со стандартным оператором запросов <xref:System.Linq.Enumerable.Concat%2A> в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:<code>"//Category&#124;//Price"</code>|  
|[Как: поиск одноуровневых узлов (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Сравнивает способы нахождения с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] всех одноуровневых объектов узла с указанным именем.<br /><br /> Связанное выражение XPath:`"../Book"`|  
|[Как: поиск атрибута родительского элемента (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Сравнивает способы перехода к родительскому элементу и поиска связанного атрибута с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"../@id"`|  
|[Как: поиск атрибутов одноуровневых узлов с определенным именем (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name.md)|Сравнивает способы поиска определенных атрибутов одноуровневых объектов контекстного узла при помощи XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"``../Book/@id``"`|  
|[Как: поиск элементов с определенным атрибутом (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute.md)|Сравнивает способы получения всех элементов, содержащих определенный атрибут, с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"./*[@Select]"`|  
|[Как: поиск дочерних элементов по положению (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position.md)|Сравнивает способы поиска элемента на основе его относительного расположения с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"Test[position() >= 2 and position() <= 4]"`|  
|[Как: найти ближайший предшествующий одноуровневый элемент (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Сравнивает способы нахождения ближайшего предшествующего одноуровневого элемента узла с помощью XPath и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> Связанное выражение XPath:`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.XPath?displayProperty=nameWithType>  
 [Выполнение запросов деревьям XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)  
 [Обработка XML-данных с использованием модели данных XPath](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
