---
title: "Сериализация в XmlReader (вызов XSLT) (C#) | Документы Майкрософт"
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
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
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
ms.openlocfilehash: 96fed09349264710dc8f0591a0022939e9a4181a
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-an-xmlreader-invoking-xslt-c"></a>Сериализация в XmlReader (вызов XSLT) (C#)
При использовании возможностей взаимодействия <xref:System.Xml?displayProperty=fullName> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], можно использовать <xref:System.Xml.Linq.XNode.CreateReader%2A> для создания <xref:System.Xml.XmlReader>. Модуль, считывающий из этого <xref:System.Xml.XmlReader>, считывает узлы XML-дерева и обрабатывает их соответствующим образом.  
  
## <a name="invoking-an-xslt-transformation"></a>Запуск преобразования XSLT  
 Кроме того, этот метод можно использовать для запуска преобразования XSLT. Можно создать XML-дерево, создать объект <xref:System.Xml.XmlReader> на основе XML-дерева, создать документ и создать объект <xref:System.Xml.XmlWriter> для записи в новый документ. Затем вызывается преобразование XSLT, и ему передаются объекты <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter>. После успешного завершения преобразования новое XML-дерево заполняется ее результатами.  
  
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
using (XmlWriter writer = newTree.CreateWriter()) {  
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
 [Сериализация XML-деревьев (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
