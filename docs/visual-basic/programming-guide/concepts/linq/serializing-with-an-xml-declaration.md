---
title: "Сериализация с использованием декларации XML (Visual Basic) | Документы Microsoft"
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
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 50707da956df593f176764bed94adfc6aec3dfa5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="dda36-102">Сериализация с использованием декларации XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dda36-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="dda36-103">В этом разделе описывается, как указывать, должна ли при сериализации формироваться XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="dda36-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="dda36-104">Формирование XML-декларации</span><span class="sxs-lookup"><span data-stu-id="dda36-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="dda36-105">Сериализация в <xref:System.IO.File>или <xref:System.IO.TextWriter>с помощью <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>метода или <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>метод создает XML-декларация.</xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="dda36-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="dda36-106">При сериализации <xref:System.Xml.XmlWriter>, параметры модуля записи (указанного в <xref:System.Xml.XmlWriterSettings>объекта) определить, создаются ли XML-декларация.</xref:System.Xml.XmlWriterSettings> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="dda36-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="dda36-107">При сериализации в строку при помощи метода `ToString` итоговый XML-документ не будет содержать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="dda36-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="dda36-108">Сериализация с использованием декларации XML</span><span class="sxs-lookup"><span data-stu-id="dda36-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="dda36-109">В следующем примере создается <xref:System.Xml.Linq.XElement>, сохраняет документ в файл, а затем выводит файл на консоль:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="dda36-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="dda36-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="dda36-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="dda36-111">Сериализация без XML-декларации</span><span class="sxs-lookup"><span data-stu-id="dda36-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="dda36-112">Следующий пример демонстрирует способы сохранения <xref:System.Xml.Linq.XElement>на <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="dda36-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
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
  
 <span data-ttu-id="dda36-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="dda36-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dda36-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dda36-114">See Also</span></span>  
 [<span data-ttu-id="dda36-115">Сериализация деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dda36-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
