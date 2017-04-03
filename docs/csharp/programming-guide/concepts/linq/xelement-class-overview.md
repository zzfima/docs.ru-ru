---
title: "Общие сведения о классе XElement (C#) | Документы Майкрософт"
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
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
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
ms.openlocfilehash: 193ae8193d73d57638835c96c3f7dfd28d320473
ms.lasthandoff: 03/13/2017

---
# <a name="xelement-class-overview-c"></a>Общие сведения о классе XElement (C#)
Класс <xref:System.Xml.Linq.XElement> — это один из фундаментальных классов в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Он обозначает элемент XML. Этот класс можно использовать для создания элементов, изменения содержимого элемента, добавления, изменения или удаления дочерних элементов, добавления к элементам атрибутов или сериализации содержимого элемента в текстовой форме. Можно также настроить взаимодействие с другими классами в <xref:System.Xml?displayProperty=fullName>, например <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="xelement-functionality"></a>Функциональные особенности класса XElement  
 В этом разделе рассматриваются функциональные особенности класса <xref:System.Xml.Linq.XElement>.  
  
### <a name="constructing-xml-trees"></a>Создание XML-деревьев  
 Можно создавать XML-деревья несколькими способами.  
  
-   Можно создать XML-дерево при помощи кода. Дополнительные сведения см. в разделе [Создание деревьев XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).  
  
-   Можно выполнить анализ XML из нескольких источников, в том числе из <xref:System.IO.TextReader>, текстовых файлов или веб-адреса (URL-адреса). Дополнительные сведения см. в разделе [Анализ XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md).  
  
-   Для заполнения дерева можно использовать <xref:System.Xml.XmlReader>. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
-   Если установлен модуль, позволяющий записывать содержимое в средство <xref:System.Xml.XmlWriter>, то можно использовать метод <xref:System.Xml.Linq.XContainer.CreateWriter%2A>, чтобы создать средство записи, передать его этому модулю, после чего использовать содержимое, записанное в <xref:System.Xml.XmlWriter>, для заполнения дерева XML.  
  
 Однако наиболее распространенным является такой метод создания XML-дерева:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Другим распространенным способом создания дерева XML является использование результатов запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] для заполнения дерева XML, как показано в следующем примере:  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a>Сериализация деревьев XML  
 Дерево XML можно сериализовать в <xref:System.IO.File>, <xref:System.IO.TextWriter> или <xref:System.Xml.XmlWriter>.  
  
 Дополнительные сведения см. в разделе [Сериализация XML-деревьев (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Получение XML-данных через методы оси  
 Можно воспользоваться методами оси для получения свойств, дочерних элементов, элементов-потомков и элементов-предков. При выполнении запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] используются методы оси и обеспечиваются гибкие и эффективные способы навигации по XML-дереву, а также его обработки.  
  
 Дополнительные сведения см. в разделе [Оси LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Выполнение запросов деревьям XML  
 Вы можете создавать запросы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], которые извлекают данные из дерева XML.  
  
 Дополнительные сведения см. в разделе [Выполнение запросов к деревьям XML (C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Изменение деревьев XML  
 Один и тот же элемент можно изменить несколькими способами, в том числе изменив содержимое или атрибуты. Можно также удалить элемент из родительской структуры.  
  
 Дополнительные сведения см. в разделе [Изменение деревьев XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о программировании LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
