---
title: "Компиляция схемы XmlSchemaCollection"
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
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a>Компиляция схемы XmlSchemaCollection
**XmlSchemaCollection** кэша или библиотеки, где хранятся и проверки схемы языка XSD определения XML-Data Reduced (XDR) и XML-схемы. **XmlSchemaCollection** повышает производительность за счет кэширования схем в памяти вместо обращения к ним из файла или URL-адрес.  
  
> [!NOTE]
>  Несмотря на то что **XmlSchemaCollection** класс хранит XDR-схемы и XML-схем, любые методы и свойства, которое принимает или возвращает **XmlSchema** объектов поддерживает только схемы XML.  
  
> [!IMPORTANT]
>  Класс <xref:System.Xml.Schema.XmlSchemaCollection> устарел и заменен классом <xref:System.Xml.Schema.XmlSchemaSet>. Дополнительные сведения о <xref:System.Xml.Schema.XmlSchemaSet> см. класс, [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
## <a name="add-schemas-to-the-collection"></a>Добавление схем в коллекцию  
 Схемы загружаются в коллекцию с помощью **добавить** метод **XmlSchemaCollection**, во время работы которого схема связывается с URI пространства имен. Для схем XML URI-код пространства имен обычно является целевым пространством имен для схемы. Для схем XDR URI-код пространства имен будет задаваться во время добавления схемы в коллекцию.  
  
## <a name="check-for-a-schema-in-the-collection"></a>Проверка наличия схемы в коллекции  
 Можно проверить, находится ли схема в коллекции с помощью **Contains** метод. **Contains** метод принимает либо **XmlSchema** объекта (только для схем XML) или строка, представляющая пространство имен URI, связанное со схемой (для схем XML и XDR).  
  
## <a name="retrieve-a-schema-from-the-collection"></a>Получение схемы из коллекции  
 Можно получить схему из коллекции с помощью **элемент** свойство. **Элемент** свойство принимает строку, представляющую пространство имен URI, связанное со схемой, обычно целевое пространство имен и возвращает **XmlSchema** объекта. **Элемент** свойство применяется только к XML-схем. Для схем XDR всегда возвращается ссылка NULL, поскольку для них нет доступной модели объектов.  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>Проверка XML-документов с помощью XmlSchemaCollection  
 Можно проверить экземпляр XML-документа при помощи **XmlSchemaCollection** путем создания **XmlSchemaCollection** объекта, добавив схемы в коллекцию и задание **схемы**  свойство **XmlValidatingReader** Чтобы назначить созданную **XmlSchemaCollection** для **XmlValidatingReader**.  
  
### <a name="improved-performance"></a>Повышенная производительность  
 Рекомендуется, если проверяются более одного документа по одной схеме, которая используется **XmlSchemaCollection** из-за счет кэширования схем в памяти, он обеспечивает более высокую производительность.  
  
 В следующем примере кода создается **XmlSchemaCollection** , схемы добавляются в коллекцию и задается **схемы** свойство.  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");    
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a>См. также  
 [Проверка XDR с помощью XmlSchemaCollection](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [Проверка схемы (XSD) XML с помощью XmlSchemaCollection](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
