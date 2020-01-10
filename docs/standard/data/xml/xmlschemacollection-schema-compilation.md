---
title: Компиляция схемы XmlSchemaCollection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
ms.openlocfilehash: 1f300bab01f94af8c70c8b67a69a73fbc5ba5bac
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709833"
---
# <a name="xmlschemacollection-schema-compilation"></a>Компиляция схемы XmlSchemaCollection
Объект **XmlSchemaCollection** является кэшем или библиотекой, где можно хранить и проверять схемы XDR и XSD. Использование **XmlSchemaCollection** повышает производительность, поскольку схемы кэшируются в памяти и их не нужно каждый раз получать из файла или по URL-адресу.  
  
> [!NOTE]
> Класс **XmlSchemaCollection** хранит и схемы XDR, и схемы XML, но все методы и свойства, которые принимают или возвращают объект **XmlSchema**, поддерживают только схемы XML.  
  
> [!IMPORTANT]
> Класс <xref:System.Xml.Schema.XmlSchemaCollection> устарел и заменен классом <xref:System.Xml.Schema.XmlSchemaSet>. Дополнительные сведения о классе <xref:System.Xml.Schema.XmlSchemaSet> см. в руководстве по [использованию XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
## <a name="add-schemas-to-the-collection"></a>Добавление схем в коллекцию  
 Схемы загружаются в коллекцию с помощью метода **Add** класса **XmlSchemaCollection**, и одновременно с этим схема связывается с URI пространства имен. Для схем XML URI-код пространства имен обычно является целевым пространством имен для схемы. Для схем XDR URI-код пространства имен будет задаваться во время добавления схемы в коллекцию.  
  
## <a name="check-for-a-schema-in-the-collection"></a>Проверка наличия схемы в коллекции  
 Наличие схемы в коллекции вы можете проверить с помощью метода **Contains**. Метод **Contains** принимает объект **XmlSchema** (только для схем XML) или строку, представляющую URI пространства имен, связанного со схемой (для схем XML и XDR).  
  
## <a name="retrieve-a-schema-from-the-collection"></a>Получение схемы из коллекции  
 Схему из коллекции можно получить с помощью свойства **Item**. Свойство **Item** принимает строку, представляющую URI пространства имен, связанного со схемой (обычно это целевое пространство имен), и возвращает объект **XmlSchema**. Свойство **Item** применимо только к схемам XML. Для схем XDR всегда возвращается ссылка NULL, поскольку для них нет доступной модели объектов.  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>Проверка XML-документов с помощью XmlSchemaCollection  
 Чтобы проверить экземпляр XML-документа с помощью **XmlSchemaCollection**, создайте объект **XmlSchemaCollection**, добавьте в эту коллекцию схемы и задайте свойство **Schemas** для объекта **XmlValidatingReader**, чтобы назначить созданную коллекцию **XmlSchemaCollection** для объекта **XmlValidatingReader**.  
  
### <a name="improved-performance"></a>Повышенная производительность  
 Если вы проверяете несколько документов по одной схеме, мы рекомендуем использовать объект **XmlSchemaCollection**, поскольку его производительность выше благодаря кэшированию схем в памяти.  
  
 Следующий пример кода создает объект **XmlSchemaCollection**, добавляет схемы в коллекцию и задает свойство **Schemas**.  
  
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
  
## <a name="see-also"></a>См. также:

- [XDR-проверка с помощью XmlSchemaCollection](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)
- [Проверка по XML-схеме (XSD) с помощью XmlSchemaCollection](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
