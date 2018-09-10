---
title: Ввод XPathDocument в XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09f0301724e483def3bea9dfdf75a088ac09bb55
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085375"
---
# <a name="xpathdocument-input-to-xsltransform"></a>Ввод XPathDocument в XslTransform
Объект <xref:System.Xml.XPath.XPathDocument> является кэшем только для чтения, который предназначен для обработки документов с помощью <xref:System.Xml.Xsl.XslTransform>. Он структурно аналогичен модели XML DOM, но значительно оптимизирован для обработки XSLT и модели данных языка XPath с помощью функций оптимизации XPath в классе <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в версии [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] устарел. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 В следующем образце кода создается объект <xref:System.Xml.XPath.XPathDocument> в качестве входных данных для преобразования.  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a>См. также

- [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
