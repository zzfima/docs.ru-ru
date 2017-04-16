---
title: "XPathNodeIterator в преобразованиях | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 2bc6ddc6-674a-4f75-b264-abc35e4e5857
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# XPathNodeIterator в преобразованиях
Класс <xref:System.Xml.XPath.XPathNodeIterator> обеспечивает методы перебора набора узлов, созданного в результате выполнения запроса XPath или в результате преобразования фрагмента результирующего дерева в набор узлов с помощью метода node\-set.  Класс <xref:System.Xml.XPath.XPathNodeIterator> дает возможность перебирать узлы внутри этого набора узлов.  По получении набора узлов класс <xref:System.Xml.XPath.XPathNodeIterator> предоставляет однопроходные курсоры только для чтения к выделенному набору узлов.  Набор узлов создается в порядке расположения узлов в документе, поэтому вызов этого метода приводит к переходу на следующий узел документа.  Класс <xref:System.Xml.XPath.XPathNodeIterator> не выполняет построение дерева узлов для всех узлов набора.  Вместо этого он предоставляет окно данных размером в один узел, в котором при переходе от одного элемента дерева к другому отображается базовый узел, на который указывает итератор.  Методы и свойства класса <xref:System.Xml.XPath.XPathNodeIterator> дают возможность получать сведения из текущего узла.  Список имеющихся методов и свойств см. в разделе [Члены класса XPathNodeIterator](frlrfsystemxmlxpathxpathnodeiteratormemberstopic).  
  
 Поскольку <xref:System.Xml.XPath.XPathNodeIterator> перемещается по набору узлов, созданному в ходе выполнения запроса Xpath, и при этом движется только вперед, перемещение осуществляется с использованием метода <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A>.  При использовании этого метода возвращаемое значение имеет тип `Boolean`. Значение `true` возвращается при перемещении к следующему выделенному узлу, а значение `false` \- если выделенных узлов больше нет.  При возвращении значения `true` доступны свойства, перечисленные в следующем списке:  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.Current%2A>  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.CurrentPosition%2A>  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.Count%2A>  
  
 Если набор узлов просматривается впервые, для размещения <xref:System.Xml.XPath.XPathNodeIterator> на первом узле выделенного набора необходимо вызвать метод <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A>.  Это дает возможность написать цикл while.  
  
 Следующий пример кода показывает, как передавать объект <xref:System.Xml.XPath.XPathNodeIterator> объекту <xref:System.Xml.Xsl.XslTransform> в виде параметра в списке <xref:System.Xml.Xsl.XsltArgumentList>.  Входные данные для этого кода находятся в файле **books.xml**, а таблица стилей \- в файле **text.xsl**.  Файл **test.xml** представляет собой <xref:System.Xml.XPath.XPathDocument>.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
  
Public Class sample  
  
   Public Shared Sub Main()  
      Dim Doc As New XPathDocument("books.xml")  
      Dim nav As XPathNavigator = Doc.CreateNavigator()  
      Dim Iterator As XPathNodeIterator = nav.Select("/bookstore/book")  
  
      Dim arg As New XsltArgumentList()  
      arg.AddParam("param1", "", Iterator)  
  
      Dim xslt As New XslTransform()  
      xslt.Load("test.xsl")  
  
      Dim xd As New XPathDocument("test.xml")  
  
      Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
      xslt.Transform(xd, arg, strmTemp, Nothing)  
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
        XPathDocument Doc = new XPathDocument("books.xml");  
        XPathNavigator nav = Doc.CreateNavigator();  
        XPathNodeIterator Iterator = nav.Select("/bookstore/book");  
  
        XsltArgumentList arg = new XsltArgumentList();  
        arg.AddParam("param1", "", Iterator);  
  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, arg, strmTemp, null);  
    }  
}  
```  
  
## books.xml  
  
```  
<?xml version='1.0'?>  
<!-- This file represents a fragment of a book store inventory database. -->  
<bookstore specialty="novel">  
    <book style="autobiography">  
    <title>Seven Years in Trenton</title>  
        <author>  
            <first-name>Jay</first-name>  
            <last-name>Adams</last-name>  
            <award>Trenton Literary Review Honorable Mention</award>  
            <country>USA</country>  
        </author>  
        <price>12</price>  
    </book>  
    <book style="textbook">  
        <title>History of Trenton</title>  
        <author>  
            <first-name>Kim</first-name>  
            <last-name>Akers</last-name>  
            <publication>  
                Selected Short Stories of  
                <first-name>Scott</first-name>  
                <last-name>Bishop</last-name>  
                <country>US</country>  
            </publication>  
        </author>  
        <price>55</price>  
    </book>  
</bookstore>  
```  
  
## test.xsl  
  
```  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">  
  
<xsl:output method="xml" indent="yes"/>  
<xsl:param name="param1"/>  
  
<xsl:template match="/">  
    <out>  
        <xsl:for-each select="$param1/title">  
            <title><xsl:value-of select="."/></title>  
        </xsl:for-each>  
    </out>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## test.xml  
  
```  
<Title attr="Test">this is a test</Title>  
```  
  
## Выходные данные \(out.xml\)  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<out>  
  <title>Seven Years in Trenton</title>  
  <title>History of Trenton</title>  
</out>  
```  
  
## См. также  
 [Реализация классом XslTransform XSLT\-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)