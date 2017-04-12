---
title: "Общие сведения о классе XElement (Visual Basic) | Документы Microsoft"
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
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4b46f3cb5e0d59105fbc31424a0408c3421d9cac
ms.lasthandoff: 03/13/2017

---
# <a name="xelement-class-overview-visual-basic"></a>Общие сведения о классе XElement (Visual Basic)
<xref:System.Xml.Linq.XElement>Класс является одним из фундаментальных классов в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Xml.Linq.XElement> Он обозначает элемент XML. Этот класс можно использовать для создания элементов, изменения содержимого элемента, добавления, изменения или удаления дочерних элементов, добавления к элементам атрибутов или сериализации содержимого элемента в текстовой форме. Можно также настроить взаимодействие с другими классами в <xref:System.Xml?displayProperty=fullName>, такие как <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>и <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> </xref:System.Xml?displayProperty=fullName>  
  
## <a name="xelement-functionality"></a>Функциональные особенности класса XElement  
 В этом разделе описываются функциональные возможности, предоставляемые <xref:System.Xml.Linq.XElement>класса.</xref:System.Xml.Linq.XElement>  
  
### <a name="constructing-xml-trees"></a>Создание XML-деревьев  
 Можно создавать XML-деревья несколькими способами.  
  
-   Можно создать XML-дерево при помощи кода. Дополнительные сведения см. в разделе [Создание XML-деревьев (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
-   Можно выполнить синтаксический анализ XML из различных источников, включая <xref:System.IO.TextReader>, текстовые файлы или веб-адрес (URL).</xref:System.IO.TextReader> Дополнительные сведения см. в разделе [синтаксического анализа XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).  
  
-   Можно использовать <xref:System.Xml.XmlReader>для заполнения дерева.</xref:System.Xml.XmlReader> Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
-   Если у вас есть модуль, который можно записать содержимое на <xref:System.Xml.XmlWriter>, можно использовать <xref:System.Xml.Linq.XContainer.CreateWriter%2A>способ создать модуль записи, передать в модуль записи, а затем использовать содержимое, которое записывается в <xref:System.Xml.XmlWriter>для заполнения дерева XML.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> </xref:System.Xml.XmlWriter>  
  
 Однако наиболее распространенным является такой метод создания XML-дерева:  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 Другим распространенным способом для создания XML-дерева является использование результатов из [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запроса для заполнения дерева XML, как показано в следующем примере:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
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
 Можно сериализовать XML-дерева <xref:System.IO.File>, <xref:System.IO.TextWriter>, или <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File>  
  
 Дополнительные сведения см. в разделе [сериализации XML-деревьев (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Получение XML-данных через методы оси  
 Можно воспользоваться методами оси для получения свойств, дочерних элементов, элементов-потомков и элементов-предков. При выполнении запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] используются методы оси и обеспечиваются гибкие и эффективные способы навигации по XML-дереву, а также его обработки.  
  
 Дополнительные сведения см. в разделе [оси LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Выполнение запросов деревьям XML  
 Можно написать [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросов, извлекающих данные из XML-дерева.  
  
 Дополнительные сведения см. в разделе [запросы XML-деревьев (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Изменение деревьев XML  
 Один и тот же элемент можно изменить несколькими способами, в том числе изменив содержимое или атрибуты. Можно также удалить элемент из родительской структуры.  
  
 Дополнительные сведения см. в разделе [изменение деревьев XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML обзор программирования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
