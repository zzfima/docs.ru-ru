---
title: Изменение XML-схем
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fa09c8e5-c2b9-49d2-bb0d-40330cd13e4d
ms.openlocfilehash: d7d9f8e0d4ec2f343b50e68e942bf94e93576f25
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710951"
---
# <a name="editing-xml-schemas"></a>Изменение XML-схем

Изменение схем XML является одной из самых важных возможностей модели SOM. Все свойства модели SOM, относящиеся к работе перед компиляцией схемы, можно использовать для изменения существующих значений в схеме XML. Затем можно повторно скомпилировать схему XML, чтобы изменения вступили в силу.

Первым шагом в изменении схемы, загруженной в модель SOM, является обзор схемы. Перед изменением схемы следует ознакомиться с обзором схемы, в котором используется API модели SOM. Также следует ознакомиться со свойствами информационного набора PSCI, относящиеся к работе перед компиляцией схемы и после нее.

## <a name="editing-an-xml-schema"></a>Изменение схемы XML

В этом разделе приводятся два примера кода, в которых изменяется пользовательская схема, созданная в руководстве по [созданию схем XML](../../../../docs/standard/data/xml/building-xml-schemas.md). В первом примере кода добавляется новый элемент `PhoneNumber` в элемент `Customer`, а во втором примере кода добавляется новый атрибут `Title` в элемент `FirstName`. В первом образце для обзора пользовательской схемы используется коллекция <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> типа «после компиляции схемы», а во втором примере кода используется коллекция <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> типа «перед компиляцией схемы».

### <a name="phonenumber-element-example"></a>Пример элемента PhoneNumber

В первом примере кода добавляется новый элемент `PhoneNumber` в элемент `Customer` пользовательской схемы. Пример кода изменяет пользовательскую схему посредством следующих шагов.

1. Добавление пользовательской схемы в новый объект <xref:System.Xml.Schema.XmlSchemaSet>, а затем ее компиляция. Любые предупреждения и ошибки проверки схемы, обнаруженные в процессе ее чтения или компиляции, обрабатываются делегатом <xref:System.Xml.Schema.ValidationEventHandler>.

2. Получение скомпилированного объекта <xref:System.Xml.Schema.XmlSchema> из <xref:System.Xml.Schema.XmlSchemaSet> путем итерации по свойству <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>. Так как схема компилируется, свойства Post-Schema-Compilation-Infoset (PSCI) доступны.

3. Создание элемента `PhoneNumber` с использованием класса <xref:System.Xml.Schema.XmlSchemaElement>, ограничение простого типа `xs:string` с использованием классов <xref:System.Xml.Schema.XmlSchemaSimpleType> и <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>, добавление аспекта шаблона в свойство <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> ограничения, добавление ограничения в свойство <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> простого типа и добавление простого типа в свойство <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> элемента `PhoneNumber`.

4. Проход по всем элементам <xref:System.Xml.Schema.XmlSchemaElement> в коллекции <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> для коллекции <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> типа «после компиляции схемы».

5. Если свойство <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> элемента имеет значение `"Customer"`, возвращается сложный тип элемента `Customer` с использованием класса <xref:System.Xml.Schema.XmlSchemaComplexType> и примитив sequence сложного типа с использованием класса <xref:System.Xml.Schema.XmlSchemaSequence>.

6. Добавление нового элемента `PhoneNumber` в последовательность, содержащую существующие элементы `FirstName` и `LastName`, с использованием коллекции <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> типа «перед компиляцией схемы» для последовательности.

7. Наконец, повторная обработка и компиляция измененного объекта <xref:System.Xml.Schema.XmlSchema> с помощью методов <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> и <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> и запись его в консоль.

Ниже приведен полный пример кода.

[!code-cpp[XmlSchemaEditExample1#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample1/CPP/XmlSchemaEditExample1.cpp#1)]
[!code-csharp[XmlSchemaEditExample1#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample1/CS/XmlSchemaEditExample1.cs#1)]
[!code-vb[XmlSchemaEditExample1#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample1/VB/XmlSchemaEditExample1.vb#1)]

Ниже приведена измененная пользовательская [схема XML](../../../../docs/standard/data/xml/building-xml-schemas.md).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="xs:string" />
        <xs:element name="LastName" type="tns:LastNameType" />
        <xs:element name="PhoneNumber">           <xs:simpleType>             <xs:restriction base="xs:string">               <xs:pattern value="\d{3}-\d{3}-\d(4)" />             </xs:restriction>           </xs:simpleType>         </xs:element>
      </xs:sequence>
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /
>
    </xs:complexType>
  </xs:element>
  <xs:simpleType name="LastNameType">
    <xs:restriction base="xs:string">
      <xs:maxLength value="20" />
    </xs:restriction>
  </xs:simpleType>
</xs:schema>
```

### <a name="title-attribute-example"></a>Пример атрибута Title

Во втором примере кода добавляется новый атрибут `Title` в элемент `FirstName` пользовательской схемы. В первом примере кода элемент `FirstName` имеет тип `xs:string`. Чтобы элемент `FirstName` имел атрибут со строковым содержимым, его тип необходимо изменить на сложный тип с простым расширением содержимого в модели содержимого.

Пример кода изменяет пользовательскую схему посредством следующих шагов.

1. Добавление пользовательской схемы в новый объект <xref:System.Xml.Schema.XmlSchemaSet>, а затем ее компиляция. Любые предупреждения и ошибки проверки схемы, обнаруженные в процессе ее чтения или компиляции, обрабатываются делегатом <xref:System.Xml.Schema.ValidationEventHandler>.

2. Получение скомпилированного объекта <xref:System.Xml.Schema.XmlSchema> из <xref:System.Xml.Schema.XmlSchemaSet> путем итерации по свойству <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>. Так как схема компилируется, свойства Post-Schema-Compilation-Infoset (PSCI) доступны.

3. Создание нового сложного типа для элемента `FirstName` с использованием класса <xref:System.Xml.Schema.XmlSchemaComplexType>.

4. Создание нового простого расширения содержимого с базовым типом `xs:string` с использованием классов <xref:System.Xml.Schema.XmlSchemaSimpleContent> и <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension>.

5. Создание нового атрибута `Title` с использованием класса <xref:System.Xml.Schema.XmlSchemaAttribute> со значением <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> для `xs:string`, и добавление атрибута в простое расширение содержимого.

6. Установка простого расширения содержимого для модели простого содержимого и простого содержимого для модели сложного типа.

7. Добавление нового сложного типа в коллекцию <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> типа «перед компиляцией схемы».

8. Выполнение итерации по каждому <xref:System.Xml.Schema.XmlSchemaObject> в коллекции <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> перед компиляцией схемы.

> [!NOTE]
> Поскольку элемент `FirstName` не является глобальным в схеме, он недоступен в коллекциях <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> и <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>. Пример кода определяет расположение элемента `FirstName` по расположению элемента `Customer`.
>
> В первом примере кода обзор схемы выполняется с помощью коллекции <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> типа «после компиляции схемы». В этом образце для обзора схемы используется коллекция <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> типа «перед компиляцией схемы». Обе коллекции предоставляют доступ к глобальным элементам схемы, но проход по коллекции <xref:System.Xml.Schema.XmlSchema.Items%2A> занимает больше времени, поскольку необходимо проходить по всем глобальным элементам в схеме, а в схеме отсутствуют свойства PSCI. Коллекции PSCI (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType> и т. д.) предоставляют прямой доступ к своим глобальным элементам, атрибутам, типам и их свойствам PSCI.

1. Если объект <xref:System.Xml.Schema.XmlSchemaObject> является элементом, значением <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> которого является `"Customer"`, возвращается сложный тип элемента `Customer` с использованием класса <xref:System.Xml.Schema.XmlSchemaComplexType> и примитив sequence сложного типа с использованием класса <xref:System.Xml.Schema.XmlSchemaSequence>.

2. Выполнение итерации по каждому <xref:System.Xml.Schema.XmlSchemaParticle> в коллекции <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> перед компиляцией схемы.

3. Если объект <xref:System.Xml.Schema.XmlSchemaParticle> является элементом, значением <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> которого является `"FirstName"`, в свойстве <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> элемента `FirstName` задается новый сложный тип `FirstName`.

4. Наконец, повторная обработка и компиляция измененного объекта <xref:System.Xml.Schema.XmlSchema> с помощью методов <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> и <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> и запись его в консоль.

Ниже приведен полный пример кода.

[!code-cpp[XmlSchemaEditExample2#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample2/CPP/XmlSchemaEditExample2.cpp#1)]
[!code-csharp[XmlSchemaEditExample2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample2/CS/XmlSchemaEditExample2.cs#1)]
[!code-vb[XmlSchemaEditExample2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample2/VB/XmlSchemaEditExample2.vb#1)]

Ниже приведена измененная пользовательская [схема XML](../../../../docs/standard/data/xml/building-xml-schemas.md).

```xml
<?xml version="1.0" encoding=" utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="tns:FirstNameComplexType" />
        <xs:element name="LastName" type="tns:LastNameType" />
      </xs:sequence>
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /
>
    </xs:complexType>
  </xs:element>
  <xs:simpleType name="LastNameType">
    <xs:restriction base="xs:string">
      <xs:maxLength value="20" />
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FirstNameComplexType">     <xs:simpleContent>       <xs:extension base="xs:string">         <xs:attribute name="Title" type="xs:string" />       </xs:extension>     </xs:simpleContent>   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a>См. также:

- [Общие сведения об модели объектов XML-схемы](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Чтение и запись XML-схем](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Построение XML-схем](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Обход XML-схем](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [Включение или импорт XML-схем](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Набор сведений для постсхемной компиляции](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
