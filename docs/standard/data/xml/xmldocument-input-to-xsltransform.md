---
title: "Ввод XmlDocument в XslTransform"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3900432a08bb525df75b15cf83956f3b92d96e00
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="xmldocument-input-to-xsltransform"></a>Ввод XmlDocument в XslTransform
Класс <xref:System.Xml.XmlDocument> представляет возможности изменения XML-документа. Если нужно изменить XML-документ перед передачей методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>, загрузите XML-документ в объект <xref:System.Xml.XmlDocument>, измените его и отправьте в объект <xref:System.Xml.Xsl.XslTransform>.  
  
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в версии [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] устарел. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Класс <xref:System.Xml.XmlDocument> реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable>, поэтому документ можно передать в метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> после изменения.  
  
 Из-за возможности изменения объекта <xref:System.Xml.XmlDocument> при использовании класса <xref:System.Xml.XmlDocument> в качестве входных данных преобразования быстродействие ниже, чем при использовании класса <xref:System.Xml.XPath.XPathDocument> для XSLT-преобразований, так как класс <xref:System.Xml.XPath.XPathDocument> оптимизирован для запросов XPath благодаря внутреннему хранению.  
  
## <a name="example"></a>Пример  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.XmlDocument>  
 [XSLT-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [XPathNavigator в преобразованиях](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [XPathNodeIterator в преобразованиях](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [Ввод XPathDocument в XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [Ввод XmlDataDocument в XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
