---
title: Чтение и запись XML-схем
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: 889c5f85a2ea3fc08dadefda5509de0fcfab76ec
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710418"
---
# <a name="reading-and-writing-xml-schemas"></a>Чтение и запись XML-схем
API модели SOM можно использовать для чтения и записи схем на языке XSD из файлов или других источников, а также строить схемы XML в памяти с помощью классов в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, которые сопоставляются со структурами, определенными в рекомендациях W3C по схемам XML.  
  
## <a name="reading-and-writing-xml-schemas"></a>Чтение и запись XML-схем  
 Класс <xref:System.Xml.Schema.XmlSchema> предоставляет методы <xref:System.Xml.Schema.XmlSchema.Read%2A> и <xref:System.Xml.Schema.XmlSchema.Write%2A> для чтения и записи схем XML. Метод <xref:System.Xml.Schema.XmlSchema.Read%2A> возвращает объект <xref:System.Xml.Schema.XmlSchema>, представляющий схему XML, и принимает необязательный объект <xref:System.Xml.Schema.ValidationEventHandler> в качестве параметра для обработки предупреждений и ошибок проверки схемы, обнаруженных при чтении схемы XML.  
  
 Метод <xref:System.Xml.Schema.XmlSchema.Write%2A> записывает схемы XML в объекты <xref:System.IO.Stream>, <xref:System.IO.TextWriter> и <xref:System.Xml.XmlWriter> и может принимать в качестве параметра необязательный объект <xref:System.Xml.XmlNamespaceManager>. Объект <xref:System.Xml.XmlNamespaceManager> используется, чтобы обрабатывать пространства имен, обнаруженные в схеме XML. Дополнительные сведения о классе <xref:System.Xml.XmlNamespaceManager>см. в руководству по [пространствах имен в документе XML](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).  
  
 Следующий пример кода иллюстрирует чтение из файла и запись в файл схем XML. Пример кода берет файл `example.xsd`, считывает его в объект <xref:System.Xml.Schema.XmlSchema> с помощью метода `static`<xref:System.Xml.Schema.XmlSchema.Read%2A>, а затем записывает файл в консоль и новый файл `new.xsd`. Кроме того, в этом примере кода методу <xref:System.Xml.Schema.ValidationEventHandler>`static` в качестве параметра передается объект <xref:System.Xml.Schema.XmlSchema.Read%2A> для обработки любых предупреждений и ошибок проверки схемы, обнаруженных при чтении схемы XML. Если объект <xref:System.Xml.Schema.ValidationEventHandler> не указан (значение `null`), об ошибках или предупреждениях сообщаться не будет.  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 В примере в качестве входных данных используется файл `example.xsd`.  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>См. также:

- [Общие сведения об модели объектов XML-схемы](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Построение XML-схем](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Обход XML-схем](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [Изменение XML-схем](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [Включение или импорт XML-схем](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Набор сведений для постсхемной компиляции](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
- [Управление пространствами имен в XML-документе](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)
