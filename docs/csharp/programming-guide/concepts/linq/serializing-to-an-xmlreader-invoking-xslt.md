---
title: Сериализация в XmlReader (вызов XSLT) (C#)
ms.date: 07/20/2015
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
ms.openlocfilehash: b079fe05fa8c230f644e011dcb62ec54f55cae60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "66487189"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-c"></a><span data-ttu-id="8cd80-102">Сериализация в XmlReader (вызов XSLT) (C#)</span><span class="sxs-lookup"><span data-stu-id="8cd80-102">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>
<span data-ttu-id="8cd80-103">При использовании средств взаимодействия <xref:System.Xml?displayProperty=nameWithType>, реализованных в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], можно применять <xref:System.Xml.Linq.XNode.CreateReader%2A> для создания <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8cd80-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="8cd80-104">Модуль, считывающий из этого <xref:System.Xml.XmlReader>, считывает узлы XML-дерева и обрабатывает их соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="8cd80-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="8cd80-105">Запуск преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="8cd80-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="8cd80-106">Кроме того, этот метод можно использовать для запуска преобразования XSLT.</span><span class="sxs-lookup"><span data-stu-id="8cd80-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="8cd80-107">Можно сформировать XML-дерево, создать из этого дерева <xref:System.Xml.XmlReader>, создать новый документ и затем создать <xref:System.Xml.XmlWriter> для записи в новый документ.</span><span class="sxs-lookup"><span data-stu-id="8cd80-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="8cd80-108">Далее можно запустить преобразование XSLT, передавая <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="8cd80-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="8cd80-109">После успешного завершения преобразования новое XML-дерево заполняется ее результатами.</span><span class="sxs-lookup"><span data-stu-id="8cd80-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="8cd80-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8cd80-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cd80-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8cd80-111">See also</span></span>

- [<span data-ttu-id="8cd80-112">Сериализация XML-деревьев (C#)</span><span class="sxs-lookup"><span data-stu-id="8cd80-112">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
