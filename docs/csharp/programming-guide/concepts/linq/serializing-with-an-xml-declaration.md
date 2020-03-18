---
title: Сериализация с помощью объявления XML (C#)
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 4533d69f2b0bee68b4adee6e18fe28dde18078ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "66483479"
---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="89004-102">Сериализация с помощью объявления XML (C#)</span><span class="sxs-lookup"><span data-stu-id="89004-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="89004-103">В этом разделе описывается, как указывать, должна ли при сериализации формироваться XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="89004-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="89004-104">Формирование XML-декларации</span><span class="sxs-lookup"><span data-stu-id="89004-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="89004-105">При сериализации в <xref:System.IO.File> или <xref:System.IO.TextWriter> с помощью метода <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> или метода <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> формируется XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="89004-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="89004-106">При сериализации в <xref:System.Xml.XmlWriter> параметры модуля записи (заданные в объекте <xref:System.Xml.XmlWriterSettings>) определяют, будет ли сформирована XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="89004-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="89004-107">При сериализации в строку при помощи метода `ToString` итоговый XML-документ не будет содержать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="89004-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="89004-108">Сериализация с использованием декларации XML</span><span class="sxs-lookup"><span data-stu-id="89004-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="89004-109">Следующий пример создает <xref:System.Xml.Linq.XElement>, сохраняет документ в файл, а затем выводит файл на консоль.</span><span class="sxs-lookup"><span data-stu-id="89004-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="89004-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="89004-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="89004-111">Сериализация без XML-декларации</span><span class="sxs-lookup"><span data-stu-id="89004-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="89004-112">В следующем примере демонстрируется, как сохранять <xref:System.Xml.Linq.XElement> в <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="89004-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="89004-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="89004-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89004-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="89004-114">See also</span></span>

- [<span data-ttu-id="89004-115">Сериализация XML-деревьев (C#)</span><span class="sxs-lookup"><span data-stu-id="89004-115">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
