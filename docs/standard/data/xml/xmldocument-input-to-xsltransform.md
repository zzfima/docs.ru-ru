---
title: "Ввод XmlDocument в XslTransform | Microsoft Docs"
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
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Ввод XmlDocument в XslTransform
Класс <xref:System.Xml.XmlDocument> представляет возможности изменения XML\-документа. Если нужно изменить XML\-документ перед передачей методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>, загрузите XML\-документ в объект <xref:System.Xml.XmlDocument>, измените его и отправьте в объект <xref:System.Xml.Xsl.XslTransform>.  
  
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в версии [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] устарел. Можно выполнять XSLT\-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. Дополнительные сведения см. в разделах [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Класс <xref:System.Xml.XmlDocument> реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable>, поэтому документ можно передать в метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> после изменения.  
  
 Из\-за возможности изменения объекта <xref:System.Xml.XmlDocument> при использовании класса <xref:System.Xml.XmlDocument> в качестве входных данных преобразования быстродействие ниже, чем при использовании класса <xref:System.Xml.XPath.XPathDocument> для XSLT\-преобразований, так как класс <xref:System.Xml.XPath.XPathDocument> оптимизирован для запросов XPath благодаря внутреннему хранению.  
  
## Пример  
 В следующем примере кода показано, как можно предоставить объект <xref:System.Xml.XmlDocument> объекту <xref:System.Xml.Xsl.XslTransform> и передать вывод в объект <xref:System.Xml.XmlReader>.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## См. также  
 <xref:System.Xml.XmlDocument>   
 [XSLT\-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)   
 [Реализация классом XslTransform XSLT\-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)   
 [XPathNavigator в преобразованиях](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)   
 [XPathNodeIterator в преобразованиях](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)   
 [Ввод XPathDocument в XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)   
 [Ввод XmlDataDocument в XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)