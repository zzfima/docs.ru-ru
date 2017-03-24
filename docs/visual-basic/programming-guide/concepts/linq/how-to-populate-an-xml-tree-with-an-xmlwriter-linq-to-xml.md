---
title: "Практическое руководство: заполнение дерева XML с помощью XmlWriter (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 5792a0eb-94ee-440d-b601-58cca8c0ee0b
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dfd10ec04e7293d90929d6f629201868028819ad
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a>Практическое руководство: заполнение дерева XML с помощью XmlWriter (LINQ to XML) (Visual Basic)
Один способ заполнения XML-дерева является использование <xref:System.Xml.Linq.XContainer.CreateWriter%2A>для создания <xref:System.Xml.XmlWriter>, а затем записать <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> XML-дерево заполняется все узлы, написанные на <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter>  
  
 Этот метод обычно используется при использовании [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] с другим классом, который предназначен для записи в <xref:System.Xml.XmlWriter>, например <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter>  
  
## <a name="example"></a>Пример  
 Можно использовать для <xref:System.Xml.Linq.XContainer.CreateWriter%2A>при вызове преобразования XSLT.</xref:System.Xml.Linq.XContainer.CreateWriter%2A> В этом примере создается XML-дерево, создается <xref:System.Xml.XmlReader>из XML-дерева, создается новый документ, а затем создает <xref:System.Xml.XmlWriter>для записи в новый документ.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> Затем он вызывает преобразование XSLT, передавая <xref:System.Xml.XmlReader>и <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> После успешного завершения преобразования новое XML-дерево заполняется ее результатами.  
  
```vb  
Dim xslMarkup As XDocument = _  
    <?xml version='1.0'?>   
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
    </xsl:stylesheet>  
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A></xref:System.Xml.Linq.XContainer.CreateWriter%2A>   
 <xref:System.Xml.XmlWriter></xref:System.Xml.XmlWriter>   
 <xref:System.Xml.Xsl.XslCompiledTransform></xref:System.Xml.Xsl.XslCompiledTransform>   
 [Создание деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
