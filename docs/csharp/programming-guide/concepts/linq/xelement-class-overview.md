---
title: Общие сведения о классе XElement (C#)
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: 6a93dd4bdaf16fddff800b08b0f3146ecb63f9b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167898"
---
# <a name="xelement-class-overview-c"></a>Общие сведения о классе XElement (C#)
Класс <xref:System.Xml.Linq.XElement> - это один из фундаментальных классов в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Он обозначает элемент XML. Этот класс можно использовать для создания элементов, изменения содержимого элемента, добавления, изменения или удаления дочерних элементов, добавления к элементам атрибутов или сериализации содержимого элемента в текстовой форме. Можно также настроить взаимодействие с другими классами в <xref:System.Xml?displayProperty=nameWithType>, например <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
В этом разделе рассматриваются функциональные особенности класса <xref:System.Xml.Linq.XElement>.  
  
## <a name="constructing-xml-trees"></a>Создание XML-деревьев  
 Можно создавать XML-деревья несколькими способами.  
  
- Можно создать XML-дерево при помощи кода. Дополнительные сведения см. в разделе [Создание деревьев XML (C#)](./linq-to-xml-overview.md).  
  
- Можно выполнить синтаксический анализ XML из нескольких источников, в том числе из <xref:System.IO.TextReader>, текстовых файлов или веб-адреса (URL-адреса). Дополнительные сведения см. в разделе [Анализ XML (C#)](./how-to-parse-a-string.md).  
  
- Для распределения контента по дереву можно использовать <xref:System.Xml.XmlReader>. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
- Если установлен модуль, позволяющий заносить содержимое в средство <xref:System.Xml.XmlWriter>, то можно использовать метод <xref:System.Xml.Linq.XContainer.CreateWriter%2A>, чтобы создать модуль записи, передать его этому модулю, после чего использовать контент, записанный в систему <xref:System.Xml.XmlWriter>, чтобы заполнить XML-дерево.  
  
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
  
 Другим распространенным способом создания дерева XML является использование результатов запроса LINQ для заполнения дерева XML, как показано в следующем примере:  
  
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
  
## <a name="serializing-xml-trees"></a>Сериализация деревьев XML  
 Можно сериализовать XML-дерево в <xref:System.IO.File>, <xref:System.IO.TextWriter> или в <xref:System.Xml.XmlWriter>.  
  
 Дополнительные сведения см. в разделе [Сериализация XML-деревьев (C#)](./preserving-white-space-while-serializing.md).  
  
## <a name="retrieving-xml-data-via-axis-methods"></a>Получение XML-данных через методы оси  
 Можно воспользоваться методами оси для получения свойств, дочерних элементов, элементов-потомков и элементов-предков. При выполнении запросов LINQ используются методы оси и обеспечиваются гибкие и эффективные способы навигации по XML-дереву, а также его обработки.  
  
 Дополнительные сведения см. в разделе [Оси LINQ to XML (C#)](./linq-to-xml-axes-overview.md).  
  
## <a name="querying-xml-trees"></a>Выполнение запросов деревьям XML  
 Вы можете создавать запросы LINQ, которые извлекают данные из дерева XML.  
  
 Дополнительные сведения см. в разделе [Выполнение запросов к деревьям XML (C#)](./how-to-find-an-element-with-a-specific-attribute.md).  
  
## <a name="modifying-xml-trees"></a>Изменение деревьев XML  
 Один и тот же элемент можно изменить несколькими способами, в том числе изменив содержимое или атрибуты. Можно также удалить элемент из родительской структуры.  
  
 Дополнительные сведения см. в разделе [Изменение деревьев XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о программировании LINQ to XML (C#)](serializing-to-files-textwriters-and-xmlwriters.md)
