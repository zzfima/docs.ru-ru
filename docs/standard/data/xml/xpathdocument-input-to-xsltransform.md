---
title: Ввод XPathDocument в XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
ms.openlocfilehash: e19e0d18dc0f4aceb38bf006c3b9b80276455510
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709768"
---
# <a name="xpathdocument-input-to-xsltransform"></a>Ввод XPathDocument в XslTransform
Объект <xref:System.Xml.XPath.XPathDocument> является кэшем только для чтения, который предназначен для обработки документов с помощью <xref:System.Xml.Xsl.XslTransform>. Он структурно аналогичен модели XML DOM, но значительно оптимизирован для обработки XSLT и модели данных языка XPath с помощью функций оптимизации XPath в классе <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
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
  
## <a name="see-also"></a>См. также:

- [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
