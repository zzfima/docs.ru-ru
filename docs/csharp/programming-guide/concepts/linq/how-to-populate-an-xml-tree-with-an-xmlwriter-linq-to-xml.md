---
title: Заполнение дерева XML с помощью XmlWriter (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
ms.openlocfilehash: f48843af403f2ee0e6d2850deab009a143f55dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345773"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a>Заполнение дерева XML с помощью XmlWriter (LINQ to XML) (C#)
Одним из вариантов заполнения XML-дерева является использование <xref:System.Xml.Linq.XContainer.CreateWriter%2A> для создания объекта <xref:System.Xml.XmlWriter>, а затем запись в объект <xref:System.Xml.XmlWriter>. XML-дерево заполняется всеми узлами, которые записаны в объект <xref:System.Xml.XmlWriter>.  
  
 Обычно этот метод применяется при использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] с другим классом, который предназначен для записи в объект <xref:System.Xml.XmlWriter>, например <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="example"></a>Пример  
 Модуль <xref:System.Xml.Linq.XContainer.CreateWriter%2A> может использоваться при вызове преобразования XSLT. В этом примере создается XML-дерево, создается объект <xref:System.Xml.XmlReader> на основе XML-дерева, создается новый документ, а затем создается объект <xref:System.Xml.XmlWriter> для записи в новый документ. Затем вызывается преобразование XSLT, и ему передаются объекты <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter>. После успешного завершения преобразования новое XML-дерево заполняется ее результатами.  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
<xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
    <xsl:template match='/Parent'>  
        <Root>  
            <C1>  
            <xsl:value-of select='Child1'/>  
            </C1>  
            <C2>  
            <xsl:value-of select='Child2'/>  
            </C2>  
        </Root>  
    </xsl:template>  
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter())  
{  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [Создание деревьев XML (C#)](./linq-to-xml-overview.md)
