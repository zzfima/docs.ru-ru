---
title: XPathNavigator в преобразованиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
ms.openlocfilehash: 240f9ca7a887a4a146437fdef46de776b299705a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709755"
---
# <a name="xpathnavigator-in-transformations"></a><span data-ttu-id="693cd-102">XPathNavigator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="693cd-102">XPathNavigator in Transformations</span></span>
<span data-ttu-id="693cd-103">Класс <xref:System.Xml.XPath.XPathNavigator> обеспечивает случайный доступ только для чтения и предназначен для использования в качестве входа в языке XSLT.</span><span class="sxs-lookup"><span data-stu-id="693cd-103">The <xref:System.Xml.XPath.XPathNavigator> class provides read-only random access to data and is designed for use as an input to Extensible Stylesheet Language for Transformations (XSLT).</span></span> <span data-ttu-id="693cd-104">Он реализован в <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument> и <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="693cd-104">It is implemented on the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, and <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="693cd-105">Класс <xref:System.Xml.XPath.XPathNavigator> основан на модели данных консорциума World Wide Web Consortium (W3C), описанной в разделе 5 рекомендаций по языку XPath.</span><span class="sxs-lookup"><span data-stu-id="693cd-105">The <xref:System.Xml.XPath.XPathNavigator> is based upon the World Wide Web Consortium (W3C) Data Model as described in section 5 of the XML Path Language (XPath) recommendation.</span></span>  
  
 <span data-ttu-id="693cd-106">Класс <xref:System.Xml.XPath.XPathNavigator> определяет модель курсора в любом хранилище и обеспечивает быстрые запросы XPath только для чтения к любому хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="693cd-106">The <xref:System.Xml.XPath.XPathNavigator> defines a cursor model over any store and provides fast, read-only XPath queries over any data store.</span></span> <span data-ttu-id="693cd-107"><xref:System.Xml.XPath.XPathNavigator> также является классом, который используется для перебора фрагментов результирующего дерева.</span><span class="sxs-lookup"><span data-stu-id="693cd-107">The <xref:System.Xml.XPath.XPathNavigator> is also the class to use for iterating over result tree fragments.</span></span>  
  
 <span data-ttu-id="693cd-108">API-интерфейс позволяет получить данные из текущего узла в хранилище и перейти в связанные узлы.</span><span class="sxs-lookup"><span data-stu-id="693cd-108">The API enables you to get information from the current node in the store and move to connected nodes.</span></span> <span data-ttu-id="693cd-109"><xref:System.Xml.XPath.XPathNavigator> — модель стиля курсора, которая просматривает хранилище с помощью набора методов **Move**.</span><span class="sxs-lookup"><span data-stu-id="693cd-109">The <xref:System.Xml.XPath.XPathNavigator> is a cursor style model that performs traversal over a store using a set of **Move** methods.</span></span> <span data-ttu-id="693cd-110"><xref:System.Xml.XPath.XPathNavigator> всегда размещается на узле.</span><span class="sxs-lookup"><span data-stu-id="693cd-110">The <xref:System.Xml.XPath.XPathNavigator> is always positioned on a node.</span></span> <span data-ttu-id="693cd-111">Любой неудачно примененный метод **Move** оставляет <xref:System.Xml.XPath.XPathNavigator> без изменений.</span><span class="sxs-lookup"><span data-stu-id="693cd-111">Any **Move** method that fails leaves the <xref:System.Xml.XPath.XPathNavigator> unchanged.</span></span>  
  
 <span data-ttu-id="693cd-112"><xref:System.Xml.XPath.XPathNavigator> является классом, который используется для перебора фрагментов результирующего дерева.</span><span class="sxs-lookup"><span data-stu-id="693cd-112">The <xref:System.Xml.XPath.XPathNavigator> is the class to use for iterating over result tree fragments.</span></span> <span data-ttu-id="693cd-113">Следующий образец кода создает фрагмент результирующего дерева в таблице стилей путем вызова функции с параметром `fragment`, который содержит XML.</span><span class="sxs-lookup"><span data-stu-id="693cd-113">The following code sample creates a result tree fragment within a style sheet by calling the function with the parameter, `fragment`, which contains XML.</span></span>  
  
## <a name="testxsl"></a><span data-ttu-id="693cd-114">test.xsl</span><span class="sxs-lookup"><span data-stu-id="693cd-114">test.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl ="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
  
<xsl:variable name="fragment">  
    <authorlist>  
       <author>Joe</author>  
    </authorlist>  
</xsl:variable>  
  
<msxsl:script language="C#" implements-prefix="user">  
<![CDATA[  
   string NodeFragment(XPathNavigator nav)  
   {  
      if (nav.HasChildren)  
        return nav.Value;  
      else  
        return "";  
   }  
]]>  
</msxsl:script>  
  
<xsl:template match="/">  
     <xsl:value-of select="user:NodeFragment($fragment)"/>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a><span data-ttu-id="693cd-115">test.xml</span><span class="sxs-lookup"><span data-stu-id="693cd-115">test.xml</span></span>  
  
```xml  
<root>Some text</root>  
```  
  
 <span data-ttu-id="693cd-116">Следующий код использует таблицу стилей **test.xsl** и входные данные **test.xml**.</span><span class="sxs-lookup"><span data-stu-id="693cd-116">The following code uses the **test.xsl** style sheet and **test.xml** input data.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
Public Class sample  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load("test.xsl")  
  
        Dim xd As New XPathDocument("test.xml")  
  
        Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
        xslt.Transform(xd, Nothing, strmTemp, Nothing)  
    End Sub 'Main  
End Class 'sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
using System.Xml.XPath;  
using System.Text;  
  
public class sample  
{  
    public static void Main()  
    {  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, null, strmTemp, null);  
    }  
}  
```  
  
## <a name="output"></a><span data-ttu-id="693cd-117">Вывод</span><span class="sxs-lookup"><span data-stu-id="693cd-117">Output</span></span>  
 <span data-ttu-id="693cd-118">Результат преобразования находится в файле **out.xml**:</span><span class="sxs-lookup"><span data-stu-id="693cd-118">The result of the transformation is found in the file **out.xml**:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a><span data-ttu-id="693cd-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="693cd-119">See also</span></span>

- [<span data-ttu-id="693cd-120">Реализация классом XslTransform XSLT-процессора</span><span class="sxs-lookup"><span data-stu-id="693cd-120">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
