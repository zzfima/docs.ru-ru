---
title: Обход XML-схем
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: cce69574-5861-4a30-b730-2e18d915d8ee
ms.openlocfilehash: dbe02242f9bb8654e3f12d87b6ff6c2aea1f76b1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710119"
---
# <a name="traversing-xml-schemas"></a>Обход XML-схем

Обзор схемы XML с помощью API-интерфейса объектной модели схемы XML (SOM) предоставляет доступ к элементам, атрибутам и типам, хранящимся в модели SOM. Проход по схеме XML, загружаемой в SOM, представляет собой также первый шаг в изменении схемы XML с помощью SOM API.

## <a name="traversing-an-xml-schema"></a>Обзор схемы XML

Следующие свойства класса <xref:System.Xml.Schema.XmlSchema> предоставляют доступ к коллекции глобальных объектов, добавляемых к схеме XML.

|Идентификаторы|Тип объекта, хранимого в коллекции или массиве|
|--------------|---------------------------------------------------|
|<xref:System.Xml.Schema.XmlSchema.Elements%2A>|<xref:System.Xml.Schema.XmlSchemaElement>|
|<xref:System.Xml.Schema.XmlSchema.Attributes%2A>|<xref:System.Xml.Schema.XmlSchemaAttribute>|
|<xref:System.Xml.Schema.XmlSchema.AttributeGroups%2A>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|
|<xref:System.Xml.Schema.XmlSchema.Groups%2A>|<xref:System.Xml.Schema.XmlSchemaGroup>|
|<xref:System.Xml.Schema.XmlSchema.Includes%2A>|<xref:System.Xml.Schema.XmlSchemaExternal>, <xref:System.Xml.Schema.XmlSchemaInclude>, <xref:System.Xml.Schema.XmlSchemaImport> или <xref:System.Xml.Schema.XmlSchemaRedefine>|
|<xref:System.Xml.Schema.XmlSchema.Items%2A>|<xref:System.Xml.Schema.XmlSchemaObject> (предоставляет доступ ко всем элементам, атрибутам и типам глобального уровня).|
|<xref:System.Xml.Schema.XmlSchema.Notations%2A>|<xref:System.Xml.Schema.XmlSchemaNotation>|
|<xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A>|<xref:System.Xml.Schema.XmlSchemaType>значение <xref:System.Xml.Schema.XmlSchemaSimpleType>значение <xref:System.Xml.Schema.XmlSchemaComplexType>|
|<xref:System.Xml.Schema.XmlSchema.UnhandledAttributes%2A>|<xref:System.Xml.XmlAttribute> (предоставляет доступ к атрибутам, не принадлежащим к пространству имен схемы).|

> [!NOTE]
> Все свойства, перечисленные выше в таблице, кроме свойства <xref:System.Xml.Schema.XmlSchema.Items%2A>, являются свойствами Post-Schema-Compilation-Infoset (PSCI), доступными только после компиляции схемы. Свойство <xref:System.Xml.Schema.XmlSchema.Items%2A> доступно до компиляции схемы и может использоваться, когда схема еще не скомпилирована, для доступа ко всем элементам, атрибутам и типам глобального уровня и для их изменения.
>
> Свойство <xref:System.Xml.Schema.XmlSchema.UnhandledAttributes%2A> предоставляет доступ ко всем атрибутам, не принадлежащим к пространству имен схемы. Эти атрибуты не обрабатываются обработчиком схемы.

Ниже приведен пример кода, демонстрирующий обзор [пользовательской схемы XML](../../../../docs/standard/data/xml/building-xml-schemas.md). Приводится пример кода, в котором схема просматривается с помощью коллекций, описанных выше, и все элементы и атрибуты схемы выводятся в консоль.

В данном примере схема Customer просматривается с помощью следующих шагов.

1. Добавление пользовательской схемы в новый объект <xref:System.Xml.Schema.XmlSchemaSet>, а затем ее компиляция. Любые предупреждения и ошибки проверки схемы, обнаруженные в процессе ее чтения или компиляции, обрабатываются делегатом <xref:System.Xml.Schema.ValidationEventHandler>.

2. Получение скомпилированного объекта <xref:System.Xml.Schema.XmlSchema> из <xref:System.Xml.Schema.XmlSchemaSet> путем итерации по свойству <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>. Так как схема компилируется, свойства Post-Schema-Compilation-Infoset (PSCI) доступны.

3. Выполняется проход по каждому элементу <xref:System.Xml.Schema.XmlSchemaElement> в коллекции <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> коллекции PSCI <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> и выводится имя каждого элемента в консоль.

4. Возвращается сложный тип элемента `Customer` с помощью класса <xref:System.Xml.Schema.XmlSchemaComplexType>.

5. Если у сложного типа есть атрибуты, возвращается объект <xref:System.Collections.IDictionaryEnumerator> для перечисления всех атрибутов <xref:System.Xml.Schema.XmlSchemaAttribute> и вывода их имен в консоль.

6. Возвращается примитив sequence сложного типа с помощью класса <xref:System.Xml.Schema.XmlSchemaSequence>.

7. Выполняется проход по каждому элементу <xref:System.Xml.Schema.XmlSchemaElement> в коллекции <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> и выводится имя каждого элемента в консоль.

Ниже приведен полный пример кода.

[!code-cpp[XmlSchemaTraverseExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaTraverseExample/CPP/XmlSchemaTraverseExample.cpp#1)]
[!code-csharp[XmlSchemaTraverseExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaTraverseExample/CS/XmlSchemaTraverseExample.cs#1)]
[!code-vb[XmlSchemaTraverseExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaTraverseExample/VB/XmlSchemaTraverseExample.vb#1)]

Свойство <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A?displayProperty=nameWithType> может иметь тип <xref:System.Xml.Schema.XmlSchemaSimpleType> или <xref:System.Xml.Schema.XmlSchemaComplexType> если это определенный пользователем простой тип или сложный тип. Оно может также иметь тип <xref:System.Xml.Schema.XmlSchemaDatatype>, если это один из встроенных типов данных, описанных в рекомендациях схемы XML W3C. В схеме «Заказчик» тип <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> элемента `Customer` представляет собой <xref:System.Xml.Schema.XmlSchemaComplexType>, а тип элементов `FirstName` и `LastName` - <xref:System.Xml.Schema.XmlSchemaSimpleType>.

Пример кода в руководстве по [созданию схемы XML](../../../../docs/standard/data/xml/building-xml-schemas.md) использует коллекцию <xref:System.Xml.Schema.XmlSchemaComplexType.Attributes%2A?displayProperty=nameWithType> для добавления атрибута `CustomerId` к элементу `Customer`. Это свойство доступно до компиляции схемы. Соответствующее свойство PSCI (доступное только после компиляции схемы) представляет собой коллекцию <xref:System.Xml.Schema.XmlSchemaComplexType.AttributeUses%2A?displayProperty=nameWithType>, которая хранит все атрибуты сложного типа, в том числе унаследованные.

## <a name="see-also"></a>См. также:

- [Общие сведения об модели объектов XML-схемы](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Чтение и запись XML-схем](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Построение XML-схем](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Изменение XML-схем](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [Включение или импорт XML-схем](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Набор сведений для постсхемной компиляции](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
