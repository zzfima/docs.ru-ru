---
title: "Компиляция схемы XmlSchemaCollection | Microsoft Docs"
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
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Компиляция схемы XmlSchemaCollection
Объект **XmlSchemaCollection** является кэшем или библиотекой, где можно хранить и проверять схемы XDR и XSD.  Использование **XmlSchemaCollection** повышает производительность за счет кэширования схем в памяти вместо обращения к ним из файла или по URL\-адресу.  
  
> [!NOTE]
>  Класс **XmlSchemaCollection** хранит и схемы XDR, и схемы XML, но любой метод и свойство, принимающие или возвращающие объект **XmlSchema**, поддерживает только схемы XML.  
  
> [!IMPORTANT]
>  Класс <xref:System.Xml.Schema.XmlSchemaCollection> устарел и заменен классом <xref:System.Xml.Schema.XmlSchemaSet>.  Дополнительные сведений о классе <xref:System.Xml.Schema.XmlSchemaSet> см. в разделе [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
## Добавление схем в коллекцию  
 Схемы загружаются в коллекцию с помощью метода **Add** класса **XmlSchemaCollection**, во время работы которого схема связывается с URI\-кодом пространства имен.  Для схем XML URI\-код пространства имен обычно является целевым пространством имен для схемы.  Для схем XDR URI\-код пространства имен будет задаваться во время добавления схемы в коллекцию.  
  
## Проверка наличия схемы в коллекции  
 Можно проверить наличие схемы в коллекции с помощью метода **Contains**.  Метод **Contains** принимает объект **XmlSchema** \(только для схем XML\) или строку, представляющую URI\-код пространства имен, связанного со схемой \(для схем XML и XDR\).  
  
## Получение схемы из коллекции  
 Можно получить схему из коллекции с помощью свойства **Item**.  Свойство **Item** принимает строку, представляющую URI\-код пространства имен, связанного со схемой \(обычно это целевое пространство имен\), и возвращает объект **XmlSchema**.  Свойство **Item** применяется только к схемам XML.  Для схем XDR всегда возвращается ссылка NULL, поскольку для них нет доступной модели объектов.  
  
## Проверка XML\-документов с помощью XmlSchemaCollection  
 Можно проверить экземпляр XML\-документа с помощью **XmlSchemaCollection**, создав объект **XmlSchemaCollection**, добавив схемы в коллекцию и задав свойство **Schemas** объекта **XmlValidatingReader**, чтобы назначить созданную коллекцию **XmlSchemaCollection** для объекта **XmlValidatingReader**.  
  
### Повышенная производительность  
 Если по одной схеме проверяется несколько документов, рекомендуется использовать объект **XmlSchemaCollection**, поскольку он обеспечивает повышение производительности за счет кэширования схем в памяти.  
  
 В следующем примере кода создается объект **XmlSchemaCollection**, схемы добавляются в коллекцию и задается свойство **Schemas**.  
  
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
  
## См. также  
 [XDR\-проверка с помощью XmlSchemaCollection](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)   
 [Проверка по XML\-схеме \(XSD\) с помощью XmlSchemaCollection](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)