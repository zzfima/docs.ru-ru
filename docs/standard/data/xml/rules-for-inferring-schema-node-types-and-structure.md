---
title: Правила выведения структуры и типов узлов схемы
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
ms.openlocfilehash: 6d66384dea7018bcc3b2dd8fde96f4fa2653f8e8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710249"
---
# <a name="rules-for-inferring-schema-node-types-and-structure"></a>Правила выведения структуры и типов узлов схемы
В данном разделе описывается, как в процессе вывода схемы различные типы узлов XML-документа преобразуются в структуру языка XSD.  
  
## <a name="element-inference-rules"></a>Правила вывода элементов  
 В данном разделе описаны правила вывода для декларации элементов. Могут быть выведены восемь структур деклараций элементов.  
  
1. Элемент простого типа  
  
2. Пустой элемент  
  
3. Пустой элемент с атрибутами  
  
4. Элемент с атрибутами и простым содержимым  
  
5. Элемент с последовательностью дочерних элементов  
  
6. Элемент с последовательностью дочерних элементов и атрибутов  
  
7. Элемент с последовательностью выборов дочерних элементов  
  
8. Элемент с последовательностью выборов дочерних элементов и атрибутов  
  
> [!NOTE]
> Все декларации элементов `complexType` выводятся как анонимные типы. Единственный выводимый глобальный элемент - корневой элемент; все остальные элементы локальны.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
### <a name="simple-typed-element"></a>Простой типизированный элемент  
 В следующей таблице показаны входные XML-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML-схема. Элемент, выделенный полужирным шрифтом, показывает схему, выведенную для элемента простого типа.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root" type="xs:string" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element"></a>Пустой элемент  
 В следующей таблице показаны входные XML-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML-схема. Элемент, выделенный полужирным шрифтом, показывает схему, выведенную для пустого элемента.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element-with-attributes"></a>Пустой элемент с атрибутами  
 В следующей таблице показаны входные XML-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML-схема. Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для пустого элемента с атрибутами.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-attributes-and-simple-content"></a>Элемент с атрибутами и простым содержимым  
 В следующей таблице показаны входные XML-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML-схема. Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с атрибутами и простым содержимым.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:simpleContent>`<br /><br /> `<xs:extension base="xs:string">`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:extension>`<br /><br /> `</xs:simpleContent>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements"></a>Элемент с последовательностью дочерних элементов  
 В следующей таблице показаны входные XML-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML-схема. Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с последовательностью дочерних элементов.  
  
> [!NOTE]
> Даже если элемент содержит только один дочерний элемент, он все равно интерпретируется как последовательность.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement" />`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements-and-attributes"></a>Элемент с последовательностью дочерних элементов и атрибутов  
 В следующей таблице показаны входные XML-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML-схема. Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с последовательностью дочерних элементов и атрибутов.  
  
> [!NOTE]
> Даже если элемент содержит только один дочерний элемент, он все равно интерпретируется как последовательность.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choices-of-child-elements"></a>Элемент с последовательностью и выбором дочерних элементов  
 В следующей таблице показаны входные XML-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML-схема. Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с последовательностью и выбором дочерних элементов.  
  
> [!NOTE]
> Для атрибута `maxOccurs` элемента `xs:choice` устанавливается в выводимой схеме значение `"unbounded"`.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choice-of-child-elements-and-attributes"></a>Элемент с последовательностью и выбором дочерних элементов и атрибутов  
 В следующей таблице показаны входные XML-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML-схема. Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с последовательностью и выбором дочерних элементов и атрибутов.  
  
> [!NOTE]
> Для атрибута `maxOccurs` элемента `xs:choice` устанавливается в выводимой схеме значение `"unbounded"`.  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="attribute-processing"></a>Обработка атрибутов  
 Каждый раз, когда в узле встречается новый атрибут, он добавляется к выведенному определению узла с помощью атрибута `use="required"`. В следующий раз, когда в экземпляре обнаружится этот узел, процесс вывода сравнит атрибуты текущего экземпляра с уже выведенными. Если в данном экземпляре отсутствуют некоторые из уже выведенных атрибутов, к определению атрибута добавляется атрибут `use="optional"`. Новые атрибуты добавляются к существующим декларациям с атрибутом `use="optional"`.  
  
### <a name="occurrence-constraints"></a>Ограничения вхождений  
 При выводе схемы формируются атрибуты `minOccurs` и `maxOccurs` для выведенных компонентов схемы, имеющие значения `"0"` или `"1"` и `"1"` или `"unbounded"`. Значения `"1"` и `"unbounded"` используются только в случае, когда не удается выполнить проверку XML-документа со значениями `"0"` и `"1"` (например, если `MinOccurs="0"` не описывает действительное состояние элемента, используется значение `minOccurs="1"`).  
  
### <a name="mixed-content"></a>Смешанное содержимое  
 Для элемента, имеющего смешанное содержимое (например, текст, перемежающийся элементами), для выводимого определения сложного типа будет создан атрибут `mixed="true"`.  
  
## <a name="other-node-type-inference-rules"></a>Другие правила определения типов узлов  
 В следующей таблице описаны правила вывода для инструкций по обработке, комментариев, ссылок на сущности, данных типа CDATA, типа документа и узлов пространства имен.  
  
|Тип узла|Преобразование|  
|---------------|-----------------|  
|Инструкция по обработке|Пропускается.|  
|Комментарий|Пропускается.|  
|Ссылка на сущность|Класс <xref:System.Xml.Schema.XmlSchemaInference> не обрабатывает ссылки на сущности. Если XML-документ содержит ссылки на сущности, нужно использовать модуль чтения данных, разворачивающий сущности. Например, можно передать в качестве параметра объект <xref:System.Xml.XmlTextReader>, у которого свойство <xref:System.Xml.XmlTextReader.EntityHandling%2A> имеет значение <xref:System.Xml.EntityHandling.ExpandEntities>. Если обнаружены ссылки на сущности и модуль чтения данных не разворачивает сущности, будет вызвано исключение.|  
|CDATA|Все разделы `<![CDATA[ … ]]` в XML-документе будут выведены как `xs:string`.|  
|Тип документа|Пропускается.|  
|Пространства имен|Пропускается.|  
  
 См. дополнительные сведения о [выведении схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.Schema.XmlSchemaInference>
- [Модель объектов схемы XML (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
- [Выведение XML-схемы](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)
- [Выведение схем из XML-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)
- [Правила выведения простых типов](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)
