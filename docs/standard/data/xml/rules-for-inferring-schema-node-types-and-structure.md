---
title: "Правила выведения структуры и типов узлов схемы | Microsoft Docs"
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
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Правила выведения структуры и типов узлов схемы
В данном разделе описывается, как в процессе вывода схемы различные типы узлов XML\-документа преобразуются в структуру языка XSD.  
  
## Правила вывода элементов  
 В данном разделе описаны правила вывода для декларации элементов.  Могут быть выведены восемь структур деклараций элементов.  
  
1.  Элемент простого типа  
  
2.  Пустой элемент  
  
3.  Пустой элемент с атрибутами  
  
4.  Элемент с атрибутами и простым содержимым  
  
5.  Элемент с последовательностью дочерних элементов  
  
6.  Элемент с последовательностью дочерних элементов и атрибутов  
  
7.  Элемент с последовательностью выборов дочерних элементов  
  
8.  Элемент с последовательностью выборов дочерних элементов и атрибутов  
  
> [!NOTE]
>  Все декларации элементов `complexType` выводятся как анонимные типы.  Единственный выводимый глобальный элемент \- корневой элемент; все остальные элементы локальны.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
### Простой типизированный элемент  
 В следующей таблице показаны входные XML\-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML\-схема.  Элемент, выделенный полужирным шрифтом, показывает схему, выведенную для элемента простого типа.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|-----------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root" type="xs:string" />`<br /><br /> `\</xs:schema>`|  
  
### Пустой элемент  
 В следующей таблице показаны входные XML\-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML\-схема.  Элемент, выделенный полужирным шрифтом, показывает схему, выведенную для пустого элемента.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|-----------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="empty" />`<br /><br /> `\</xs:schema>`|  
  
### Пустой элемент с атрибутами  
 В следующей таблице показаны входные XML\-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML\-схема.  Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для пустого элемента с атрибутами.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|-----------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="empty">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### Элемент с атрибутами и простым содержимым  
 В следующей таблице показаны входные XML\-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML\-схема.  Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с атрибутами и простым содержимым.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|-----------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:simpleContent>`<br /><br /> `\<xs:extension base="xs:string">`<br /><br /> `\<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `\</xs:extension>`<br /><br /> `\</xs:simpleContent>`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### Элемент с последовательностью дочерних элементов  
 В следующей таблице показаны входные XML\-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML\-схема.  Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с последовательностью дочерних элементов.  
  
> [!NOTE]
>  Даже если элемент содержит только один дочерний элемент, он все равно интерпретируется как последовательность.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|-----------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:sequence>`<br /><br /> `\<xs:element name="subElement" />`<br /><br /> `\</xs:sequence>`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### Элемент с последовательностью дочерних элементов и атрибутов  
 В следующей таблице показаны входные XML\-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML\-схема.  Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с последовательностью дочерних элементов и атрибутов.  
  
> [!NOTE]
>  Даже если элемент содержит только один дочерний элемент, он все равно интерпретируется как последовательность.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|-----------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:sequence>`<br /><br /> `\<xs:element name="subElement1" />`<br /><br /> `\<xs:element name="subElement2" />`<br /><br /> `\</xs:sequence>`<br /><br /> `\<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### Элемент с последовательностью и выбором дочерних элементов  
 В следующей таблице показаны входные XML\-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML\-схема.  Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с последовательностью и выбором дочерних элементов.  
  
> [!NOTE]
>  Для атрибута `maxOccurs` элемента `xs:choice` устанавливается в выводимой схеме значение `"unbounded"`.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|-----------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:sequence>`<br /><br /> `\<xs:choice maxOccurs="unbounded">`<br /><br /> `\<xs:element name="subElement1" />`<br /><br /> `\<xs:element name="subElement2" />`<br /><br /> `\</xs:choice>`<br /><br /> `\</xs:sequence>`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### Элемент с последовательностью и выбором дочерних элементов и атрибутов  
 В следующей таблице показаны входные XML\-данные для метода <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> и созданная XML\-схема.  Элементы, выделенные полужирным шрифтом, показывают схему, выведенную для элемента с последовательностью и выбором дочерних элементов и атрибутов.  
  
> [!NOTE]
>  Для атрибута `maxOccurs` элемента `xs:choice` устанавливается в выводимой схеме значение `"unbounded"`.  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
|XML|Схема|  
|---------|-----------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:sequence>`<br /><br /> `\<xs:choice maxOccurs="unbounded">`<br /><br /> `\<xs:element name="subElement1" />`<br /><br /> `\<xs:element name="subElement2" />`<br /><br /> `\</xs:choice>`<br /><br /> `\</xs:sequence>`<br /><br /> `\<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### Обработка атрибутов  
 Каждый раз, когда в узле встречается новый атрибут, он добавляется к выведенному определению узла с помощью атрибута `use="required"`.  В следующий раз, когда в экземпляре обнаружится этот узел, процесс вывода сравнит атрибуты текущего экземпляра с уже выведенными.  Если в данном экземпляре отсутствуют некоторые из уже выведенных атрибутов, к определению атрибута добавляется атрибут `use="optional"`.  Новые атрибуты добавляются к существующим декларациям с атрибутом `use="optional"`.  
  
### Ограничения вхождений  
 При выводе схемы формируются атрибуты `minOccurs` и `maxOccurs` для выведенных компонентов схемы, имеющие значения `"0"` или `"1"` и `"1"` или `"unbounded"`.  Значения `"1"` и `"unbounded"` используются только в случае, когда не удается выполнить проверку XML\-документа со значениями `"0"` и `"1"` \(например, если `MinOccurs="0"` не описывает действительное состояние элемента, используется значение `minOccurs="1"`\).  
  
### Смешанное содержимое  
 Для элемента, имеющего смешанное содержимое \(например, текст, перемежающийся элементами\), для выводимого определения сложного типа будет создан атрибут `mixed="true"`.  
  
## Другие правила определения типов узлов  
 В следующей таблице описаны правила вывода для инструкций по обработке, комментариев, ссылок на сущности, данных типа CDATA, типа документа и узлов пространства имен.  
  
|Тип узла|Перевод|  
|--------------|-------------|  
|Инструкция по обработке|Не обрабатывается.|  
|Комментарий|Не обрабатывается.|  
|Ссылка на сущность|Класс <xref:System.Xml.Schema.XmlSchemaInference> не обрабатывает ссылки на сущности.  Если XML\-документ содержит ссылки на сущности, нужно использовать модуль чтения данных, разворачивающий сущности.  Например, можно передать в качестве параметра объект <xref:System.Xml.XmlTextReader>, у которого свойство <xref:System.Xml.XmlTextReader.EntityHandling%2A> имеет значение <xref:System.Xml.EntityHandling>.  Если обнаружены ссылки на сущности и модуль чтения данных не разворачивает сущности, будет вызвано исключение.|  
|CDATA|Все разделы `<![CDATA[ … ]]` в XML\-документе будут выведены как `xs:string`.|  
|Тип документа|Не обрабатывается.|  
|Пространства имен|Не обрабатывается.|  
  
 Дополнительные сведения о процессе выведения схемы см. в разделе [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).  
  
## См. также  
 <xref:System.Xml.Schema.XmlSchemaInference>   
 [Модель объектов схемы XML \(SOM\)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)   
 [Выведение XML\-схемы](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)   
 [Выведение схем из XML\-документов](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)   
 [Правила выведения простых типов](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)