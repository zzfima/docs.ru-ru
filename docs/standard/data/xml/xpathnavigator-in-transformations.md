---
title: XPathNavigator в преобразованиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76cfa51c7d434a6dfdcdc1e6852779decaa601e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xpathnavigator-in-transformations"></a>XPathNavigator в преобразованиях
Класс <xref:System.Xml.XPath.XPathNavigator> обеспечивает случайный доступ только для чтения и предназначен для использования в качестве входа в языке XSLT. Он реализован в <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument> и <xref:System.Xml.XmlDocument>. Класс <xref:System.Xml.XPath.XPathNavigator> основан на модели данных консорциума World Wide Web Consortium (W3C), описанной в разделе 5 рекомендаций по языку XPath.  
  
 Класс <xref:System.Xml.XPath.XPathNavigator> определяет модель курсора в любом хранилище и обеспечивает быстрые запросы XPath только для чтения к любому хранилищу данных. <xref:System.Xml.XPath.XPathNavigator> также является классом, который используется для перебора фрагментов результирующего дерева.  
  
 API-интерфейс позволяет получить данные из текущего узла в хранилище и перейти в связанные узлы. <xref:System.Xml.XPath.XPathNavigator> — модель стиля курсора, которая просматривает хранилище с помощью набора методов **Move**. <xref:System.Xml.XPath.XPathNavigator> всегда размещается на узле. Любой неудачно примененный метод **Move** оставляет <xref:System.Xml.XPath.XPathNavigator> без изменений.  
  
 <xref:System.Xml.XPath.XPathNavigator> является классом, который используется для перебора фрагментов результирующего дерева. Следующий образец кода создает фрагмент результирующего дерева в таблице стилей путем вызова функции с параметром `fragment`, который содержит XML.  
  
## <a name="testxsl"></a>test.xsl  
  
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
  
## <a name="testxml"></a>test.xml  
  
```xml  
<root>Some text</root>  
```  
  
 Следующий код использует таблицу стилей **test.xsl** и входные данные **test.xml**.  
  
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
  
## <a name="output"></a>Вывод  
 Результат преобразования находится в файле **out.xml**:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a>См. также  
 [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
