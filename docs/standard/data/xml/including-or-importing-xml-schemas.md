---
title: Включение или импорт XML-схем
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fe1b4a11-37f4-4e1a-93c9-239f4fe736c0
ms.openlocfilehash: d9a18876d8a5ba3067aa35c617b1e20fce0411f5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710782"
---
# <a name="including-or-importing-xml-schemas"></a>Включение или импорт XML-схем
Схема XML может содержать элементы `<xs:import />`, `<xs:include />` и `<xs:redefine />`. Эти элементы схемы ссылаются на другие схемы XML, которые можно использовать в дополнение к структуре схемы, их включающей или импортирующей. Классы <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> и <xref:System.Xml.Schema.XmlSchemaRedefine> сопоставляются с этими элементами в API модели SOM.  
  
## <a name="including-or-importing-an-xml-schema"></a>Включение или импорт схемы XML  
 В следующем примере кода [пользовательская схема XML](../../../../docs/standard/data/xml/building-xml-schemas.md) дополняется схемой адресов. Добавление к пользовательской схеме схемы адресов делает типы адресов доступными в пользовательской схеме.  
  
 Схему адресов можно добавить с помощью элементов `<xs:include />` или `<xs:import />`, использующих компоненты схемы адресов без изменения, или с помощью элемента `<xs:redefine />`, который изменяет компоненты схемы в соответствии с задачами пользовательской схемы. Поскольку схема адресов имеет пространство имен `targetNamespace`, которое отличается от пользовательской схемы, используется элемент `<xs:import />` и семантика импорта.  
  
 Пример кода включает пользовательскую схему со следующими шагами.  
  
1. Добавление пользовательской схемы и схемы адресов в новый объект <xref:System.Xml.Schema.XmlSchemaSet> и компиляция схем. Все предупреждения и ошибки проверки схемы, обнаруженные в процессе чтения или компиляции, обрабатываются делегатом <xref:System.Xml.Schema.ValidationEventHandler>.  
  
2. Получение скомпилированных объектов <xref:System.Xml.Schema.XmlSchema> для пользовательской схемы и схемы адресов из <xref:System.Xml.Schema.XmlSchemaSet> путем прохода по свойству <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>. Так как схемы скомпилированы, доступны свойства информационного набора PSCI.  
  
3. Создание объекта <xref:System.Xml.Schema.XmlSchemaImport>, задание в свойстве импорта <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> пространства имен схемы адресов, задание в свойстве импорта <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> объекта <xref:System.Xml.Schema.XmlSchema> схемы адресов и добавление импорта в свойство <xref:System.Xml.Schema.XmlSchema.Includes%2A> пользовательской схемы.  
  
4. Повторная обработка и компиляция измененного объекта <xref:System.Xml.Schema.XmlSchema> с помощью методов <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> и <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> и последующая запись объекта в консоль.  
  
5. Заключительный шаг - рекурсивная запись всех схем, импортированных в пользовательскую схему, в консоль с помощью свойства <xref:System.Xml.Schema.XmlSchema.Includes%2A> пользовательской схемы. Свойство <xref:System.Xml.Schema.XmlSchema.Includes%2A> предоставляет доступ ко всем объектам, добавленным в схему путем включения, импорта или переопределения.  
  
 Далее приведен полный пример кода, а также пользовательская схема и схема адресов, записанные в консоль.  
  
 [!code-cpp[XmlSchemaImportExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaImportExample/CPP/XmlSchemaImportExample.cpp#1)]
 [!code-csharp[XmlSchemaImportExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaImportExample/CS/XmlSchemaImportExample.cs#1)]
 [!code-vb[XmlSchemaImportExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaImportExample/VB/XmlSchemaImportExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://www.example.com/IPO" />  
  <xs:element name="Customer">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="FirstName" type="xs:string" />  
        <xs:element name="LastName" type="tns:LastNameType" />  
      </xs:sequence>  
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" />  
    </xs:complexType>  
  </xs:element>  
  <xs:simpleType name="LastNameType">  
    <xs:restriction base="xs:string">  
      <xs:maxLength value="20" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
<schema targetNamespace="http://www.example.com/IPO" xmlns="http://www.w3.org/2001/XMLSchema" xmlns:ipo="http://www.example.com/IPO">  
  <annotation>  
    <documentation xml:lang="en">  
      Addresses for International Purchase order schema  
      Copyright 2000 Example.com. All rights reserved.  
    </documentation>  
  </annotation>  
  <complexType name="Address">  
    <sequence>  
      <element name="name"   type="string"/>  
      <element name="street" type="string"/>  
      <element name="city"   type="string"/>  
    </sequence>  
  </complexType>  
  <complexType name="USAddress">  
    <complexContent>  
      <extension base="ipo:Address">  
        <sequence>  
          <element name="state" type="ipo:USState"/>  
          <element name="zip"   type="positiveInteger"/>  
        </sequence>  
      </extension>  
    </complexContent>  
  </complexType>  
  <!-- other Address derivations for more countries or regions -->  
  <simpleType name="USState">  
    <restriction base="string">  
      <enumeration value="AK"/>  
      <enumeration value="AL"/>  
      <enumeration value="AR"/>  
      <!-- and so on ... -->  
    </restriction>  
  </simpleType>  
</schema>  
```  
  
 Дополнительные сведения об элементах `<xs:import />`, `<xs:include />` и `<xs:redefine />`, а также классах <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> и <xref:System.Xml.Schema.XmlSchemaRedefine> см. в [документации консорциума W3C по схемам XML](https://www.w3.org/XML/Schema) и в справочной документации по классу пространства имен <xref:System.Xml.Schema?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также:

- [Общие сведения об модели объектов XML-схемы](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Чтение и запись XML-схем](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Построение XML-схем](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Обход XML-схем](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [Изменение XML-схем](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
