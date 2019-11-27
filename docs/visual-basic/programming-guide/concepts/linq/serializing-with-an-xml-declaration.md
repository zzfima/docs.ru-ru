---
title: Сериализация с использованием декларации XML
ms.date: 07/20/2015
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
ms.openlocfilehash: 96c95b4c94290016684721a194ca31a836a49740
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350635"
---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="61dfc-102">Сериализация с помощью XML-декларации (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61dfc-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="61dfc-103">В этом разделе описывается, как указывать, должна ли при сериализации формироваться XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="61dfc-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="61dfc-104">Формирование XML-декларации</span><span class="sxs-lookup"><span data-stu-id="61dfc-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="61dfc-105">При сериализации в <xref:System.IO.File> или <xref:System.IO.TextWriter> с помощью метода <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> или метода <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> формируется XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="61dfc-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="61dfc-106">При сериализации в <xref:System.Xml.XmlWriter> параметры модуля записи (заданные в объекте <xref:System.Xml.XmlWriterSettings>) определяют, будет ли сформирована XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="61dfc-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="61dfc-107">При сериализации в строку при помощи метода `ToString` итоговый XML-документ не будет содержать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="61dfc-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="61dfc-108">Сериализация с использованием декларации XML</span><span class="sxs-lookup"><span data-stu-id="61dfc-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="61dfc-109">Следующий пример создает <xref:System.Xml.Linq.XElement>, сохраняет документ в файл, а затем выводит файл на консоль.</span><span class="sxs-lookup"><span data-stu-id="61dfc-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="61dfc-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="61dfc-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="61dfc-111">Сериализация без XML-декларации</span><span class="sxs-lookup"><span data-stu-id="61dfc-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="61dfc-112">В следующем примере демонстрируется, как сохранять <xref:System.Xml.Linq.XElement> в <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="61dfc-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="61dfc-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="61dfc-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61dfc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="61dfc-114">See also</span></span>

- [<span data-ttu-id="61dfc-115">Сериализация деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61dfc-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
