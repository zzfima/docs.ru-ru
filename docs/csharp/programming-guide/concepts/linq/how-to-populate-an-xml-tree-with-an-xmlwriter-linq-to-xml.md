---
title: "Практическое руководство. Заполнение дерева XML с помощью XmlWriter (LINQ to XML) (C#) | Документы Майкрософт"
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
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
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
ms.openlocfilehash: 225aa8a39a973ba8d4f199ccfce68e2dc16d8aa2
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a>Практическое руководство. Заполнение дерева XML с помощью XmlWriter (LINQ to XML) (C#)
Одним из способов заполнения дерева XML является использование <xref:System.Xml.Linq.XContainer.CreateWriter%2A> для создания объекта <xref:System.Xml.XmlWriter>, а затем запись в <xref:System.Xml.XmlWriter>. Дерево XML заполняется всеми узлами, которые записаны в объект <xref:System.Xml.XmlWriter>.  
  
 Этот способ обычно используется при использовании [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] с другим классом, который ожидает записи в <xref:System.Xml.XmlWriter>, таким как <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="example"></a>Пример  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A> можно, например, использовать при вызове преобразования XSLT. В этом примере создается дерево XML, создается объект <xref:System.Xml.XmlReader> на основе дерева XML, создается документ, а затем объект <xref:System.Xml.XmlWriter> для записи в новый документ. Затем вызывается преобразование XSLT, и ему передаются объекты <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter>. После успешного завершения преобразования новое XML-дерево заполняется ее результатами.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>   
 <xref:System.Xml.XmlWriter>   
 <xref:System.Xml.Xsl.XslCompiledTransform>   
 [Создание деревьев XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
