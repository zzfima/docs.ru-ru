---
title: "Сериализация с помощью объявления XML (C#)"
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
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36ffb8ddd584785c660896ca77707d504638852f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="8cc8f-102">Сериализация с помощью объявления XML (C#)</span><span class="sxs-lookup"><span data-stu-id="8cc8f-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="8cc8f-103">В этом разделе описывается, как указывать, должна ли при сериализации формироваться XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="8cc8f-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="8cc8f-104">Формирование XML-декларации</span><span class="sxs-lookup"><span data-stu-id="8cc8f-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="8cc8f-105">При сериализации в <xref:System.IO.File> или <xref:System.IO.TextWriter> с помощью метода <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> или метода <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> формируется XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="8cc8f-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="8cc8f-106">При сериализации в <xref:System.Xml.XmlWriter> параметры модуля записи (заданные в объекте <xref:System.Xml.XmlWriterSettings>) определяют, будет ли сформирована XML-декларация.</span><span class="sxs-lookup"><span data-stu-id="8cc8f-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="8cc8f-107">При сериализации в строку при помощи метода `ToString` итоговый XML-документ не будет содержать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="8cc8f-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="8cc8f-108">Сериализация с использованием декларации XML</span><span class="sxs-lookup"><span data-stu-id="8cc8f-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="8cc8f-109">Следующий пример создает <xref:System.Xml.Linq.XElement>, сохраняет документ в файл, а затем выводит файл на консоль.</span><span class="sxs-lookup"><span data-stu-id="8cc8f-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="8cc8f-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8cc8f-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="8cc8f-111">Сериализация без XML-декларации</span><span class="sxs-lookup"><span data-stu-id="8cc8f-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="8cc8f-112">В следующем примере демонстрируется, как сохранять <xref:System.Xml.Linq.XElement> в <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="8cc8f-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
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
  
 <span data-ttu-id="8cc8f-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="8cc8f-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cc8f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8cc8f-114">See Also</span></span>  
 [<span data-ttu-id="8cc8f-115">Сериализация XML-деревьев (C#)</span><span class="sxs-lookup"><span data-stu-id="8cc8f-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)

