---
title: Практическое руководство. Заполнение дерева XML с помощью XmlWriter (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 5792a0eb-94ee-440d-b601-58cca8c0ee0b
ms.openlocfilehash: ec44f6e21453a1333f842030bae0c4f80dedb9c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333773"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a><span data-ttu-id="31de7-102">Как заполнить дерево XML с помощью XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31de7-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="31de7-103">Одним из вариантов заполнения XML-дерева является использование <xref:System.Xml.Linq.XContainer.CreateWriter%2A> для создания объекта <xref:System.Xml.XmlWriter>, а затем запись в объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="31de7-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="31de7-104">XML-дерево заполняется всеми узлами, которые записаны в объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="31de7-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="31de7-105">Обычно этот метод применяется при использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] с другим классом, который предназначен для записи в объект <xref:System.Xml.XmlWriter>, например <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="31de7-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31de7-106">Пример</span><span class="sxs-lookup"><span data-stu-id="31de7-106">Example</span></span>  
 <span data-ttu-id="31de7-107">Модуль <xref:System.Xml.Linq.XContainer.CreateWriter%2A> может использоваться при вызове преобразования XSLT.</span><span class="sxs-lookup"><span data-stu-id="31de7-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="31de7-108">В этом примере создается XML-дерево, создается объект <xref:System.Xml.XmlReader> на основе XML-дерева, создается новый документ, а затем создается объект <xref:System.Xml.XmlWriter> для записи в новый документ.</span><span class="sxs-lookup"><span data-stu-id="31de7-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="31de7-109">Затем вызывается преобразование XSLT, и ему передаются объекты <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="31de7-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="31de7-110">После успешного завершения преобразования новое XML-дерево заполняется ее результатами.</span><span class="sxs-lookup"><span data-stu-id="31de7-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="31de7-111">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="31de7-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="31de7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="31de7-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="31de7-113">Создание деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31de7-113">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
