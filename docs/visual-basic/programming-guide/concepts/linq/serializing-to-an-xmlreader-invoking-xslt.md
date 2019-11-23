---
title: Сериализация в XmlReader (вызов XSLT)
ms.date: 07/20/2015
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
ms.openlocfilehash: 39ecbc1851764d221ac99c3e47c26bcbe84c9e46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349355"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a>Serializing to an XmlReader (Invoking XSLT) (Visual Basic)
При использовании средств взаимодействия <xref:System.Xml?displayProperty=nameWithType>, реализованных в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], можно применять <xref:System.Xml.Linq.XNode.CreateReader%2A> для создания <xref:System.Xml.XmlReader>. Модуль, считывающий из этого <xref:System.Xml.XmlReader>, считывает узлы XML-дерева и обрабатывает их соответствующим образом.  
  
## <a name="invoking-an-xslt-transformation"></a>Запуск преобразования XSLT  
 Кроме того, этот метод можно использовать для запуска преобразования XSLT. Можно сформировать XML-дерево, создать из этого дерева <xref:System.Xml.XmlReader>, создать новый документ и затем создать <xref:System.Xml.XmlWriter> для записи в новый документ. Далее можно запустить преобразование XSLT, передавая <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter>. После успешного завершения преобразования новое XML-дерево заполняется ее результатами.  
  
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

- [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
