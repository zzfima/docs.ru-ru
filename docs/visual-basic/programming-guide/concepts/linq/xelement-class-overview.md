---
title: Общие сведения о классе XElement
ms.date: 07/20/2015
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
ms.openlocfilehash: ff751a14abf9a9cb5d64e44e601c5d0ca6218c7d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349311"
---
# <a name="xelement-class-overview-visual-basic"></a>XElement Class Overview (Visual Basic)
Класс <xref:System.Xml.Linq.XElement> - это один из фундаментальных классов в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Он обозначает элемент XML. Этот класс можно использовать для создания элементов, изменения содержимого элемента, добавления, изменения или удаления дочерних элементов, добавления к элементам атрибутов или сериализации содержимого элемента в текстовой форме. Можно также настроить взаимодействие с другими классами в <xref:System.Xml?displayProperty=nameWithType>, например <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="xelement-functionality"></a>Функциональные особенности класса XElement  
 В этом разделе рассматриваются функциональные особенности класса <xref:System.Xml.Linq.XElement>.  
  
### <a name="constructing-xml-trees"></a>Создание XML-деревьев  
 Можно создавать XML-деревья несколькими способами.  
  
- Можно создать XML-дерево при помощи кода. For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
- Можно выполнить синтаксический анализ XML из нескольких источников, в том числе из <xref:System.IO.TextReader>, текстовых файлов или веб-адреса (URL-адреса). For more information, see [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).  
  
- Для распределения контента по дереву можно использовать <xref:System.Xml.XmlReader>. Для получения дополнительной информации см. <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
- Если установлен модуль, позволяющий заносить содержимое в средство <xref:System.Xml.XmlWriter>, то можно использовать метод <xref:System.Xml.Linq.XContainer.CreateWriter%2A>, чтобы создать модуль записи, передать его этому модулю, после чего использовать контент, записанный в систему <xref:System.Xml.XmlWriter>, чтобы заполнить XML-дерево.  
  
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
  
 Другим распространенным способом создания дерева XML является использование результатов запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] для заполнения дерева XML, как показано в следующем примере:  
  
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
 Можно сериализовать XML-дерево в <xref:System.IO.File>, <xref:System.IO.TextWriter> или в <xref:System.Xml.XmlWriter>.  
  
 For more information, see [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Получение XML-данных через методы оси  
 Можно воспользоваться методами оси для получения свойств, дочерних элементов, элементов-потомков и элементов-предков. При выполнении запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] используются методы оси и обеспечиваются гибкие и эффективные способы навигации по XML-дереву, а также его обработки.  
  
 For more information, see [LINQ to XML Axes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Выполнение запросов деревьям XML  
 Вы можете создавать запросы [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], которые извлекают данные из дерева XML.  
  
 For more information, see [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Изменение деревьев XML  
 Один и тот же элемент можно изменить несколькими способами, в том числе изменив содержимое или атрибуты. Можно также удалить элемент из родительской структуры.  
  
 For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>См. также

- [LINQ to XML Programming Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
