---
title: Построение XML-схем
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 8a5ea56c-0140-4b51-8997-875ae6a8e0cb
ms.openlocfilehash: c921331b00fe137d4ad52d62951e8c161768dfae
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711146"
---
# <a name="building-xml-schemas"></a>Построение XML-схем
Классы в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType> сопоставляются со структурами, определенными в рекомендациях по схемам XML консорциума W3C, и могут использоваться для сборки схем XML в памяти.  
  
## <a name="building-an-xml-schema"></a>Построение схемы XML  
 В следующем примере кода для построения схемы XML в памяти используется API модели SOM.  
  
### <a name="creating-element-and-attributes"></a>Создание элемента и атрибутов  
 Примеры кода собирают пользовательскую схему снизу вверх, вначале создавая дочерние элементы, атрибуты и их соответствующие типы, а затем элементы верхнего уровня.  
  
 В следующем примере кода элементы `FirstName` и `LastName`, а также атрибут пользовательской схемы `CustomerId` создаются с помощью классов <xref:System.Xml.Schema.XmlSchemaElement> и <xref:System.Xml.Schema.XmlSchemaAttribute> модели SOM. Помимо свойств <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> классов <xref:System.Xml.Schema.XmlSchemaElement> и <xref:System.Xml.Schema.XmlSchemaAttribute>, соответствующих атрибуту name элементов `<xs:element />` и `<xs:attribute />` схемы XML, все остальные атрибуты, разрешенные схемой (`defaultValue`, `fixedValue`, `form` и так далее), имеют соответствующие свойства в классах <xref:System.Xml.Schema.XmlSchemaElement> и <xref:System.Xml.Schema.XmlSchemaAttribute>.  
  
 [!code-cpp[XmlSchemaCreateExample#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#2)]
 [!code-csharp[XmlSchemaCreateExample#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#2)]
 [!code-vb[XmlSchemaCreateExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#2)]  
  
### <a name="creating-schema-types"></a>Создание типов схемы  
 Содержимое элементов и атрибутов определяется их типом. Чтобы создать элементы и атрибуты со встроенными типами схемы, свойство <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> классов <xref:System.Xml.Schema.XmlSchemaElement> или <xref:System.Xml.Schema.XmlSchemaAttribute> принимает значение соответствующего полного имени встроенного типа с помощью класса <xref:System.Xml.XmlQualifiedName>. Чтобы создать определяемый пользователем тип для элементов и атрибутов, формируется новый простой или сложный тип с помощью классов <xref:System.Xml.Schema.XmlSchemaSimpleType> или <xref:System.Xml.Schema.XmlSchemaComplexType>.  
  
> [!NOTE]
> Чтобы создать неименованные простые или сложные типы, являющиеся анонимными потомками элемента или атрибута (к атрибутам применяются только простые типы), присвойте свойству <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> класса <xref:System.Xml.Schema.XmlSchemaElement> или класса <xref:System.Xml.Schema.XmlSchemaAttribute> значение неименованного простого или сложного типа, а не свойства <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> классов <xref:System.Xml.Schema.XmlSchemaElement> или <xref:System.Xml.Schema.XmlSchemaAttribute>.  
  
 Схемы XML допускают, чтобы анонимные и именованные простые типы выводились по ограничению из других простых типов (встроенных или пользовательских) либо конструировались в виде списка или объединения других простых типов. Класс <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> используется для создания простого типа, ограничивая встроенный тип `xs:string`. Чтобы создать тип списка или объединения, можно также использовать класс <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> или <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion>. Свойство <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> обозначает, является ли оно простым типом ограничения, типом списка или объединением.  
  
 В следующем примере кода тип `FirstName` элемента является встроенным типом `xs:string`, тип `LastName` - именованным простым типом, представляющим собой ограничение встроенного типа `xs:string` со значением аспекта `MaxLength`, равным 20, а тип атрибута `CustomerId` является встроенным типом `xs:positiveInteger`. Элемент `Customer` представляет собой анонимный сложный тип, примитив которого является последовательностью элементов `FirstName` и `LastName` и атрибут которого содержит атрибут `CustomerId`.  
  
> [!NOTE]
> Классы <xref:System.Xml.Schema.XmlSchemaChoice> и <xref:System.Xml.Schema.XmlSchemaAll> можно также использовать в качестве примитивов сложного типа для репликации семантики `<xs:choice />` или `<xs:all />`.  
  
 [!code-cpp[XmlSchemaCreateExample#3](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#3)]
 [!code-csharp[XmlSchemaCreateExample#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#3)]
 [!code-vb[XmlSchemaCreateExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#3)]  
  
### <a name="creating-and-compiling-schemas"></a>Создание и компиляция схем  
 В этой точке дочерние элементы и атрибуты, их соответствующие типы и элемент верхнего уровня `Customer` были созданы в памяти с помощью API модели SOM. В следующем примере кода с помощью класса <xref:System.Xml.Schema.XmlSchema> создается элемент схемы, к нему добавляются элементы верхнего уровня и типы с помощью свойства <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> и полная схема компилируется с помощью класса <xref:System.Xml.Schema.XmlSchemaSet> и выводится на консоль.  
  
 [!code-cpp[XmlSchemaCreateExample#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#4)]
 [!code-csharp[XmlSchemaCreateExample#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#4)]
 [!code-vb[XmlSchemaCreateExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#4)]  
  
 Метод <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> проверяет пользовательскую схему по правилам схемы XML и делает доступными свойства результатов проверки компиляции схемы.  
  
> [!NOTE]
> Все свойства результатов проверки компиляции схемы в API модели SOM отличаются от информационного набора окончательной проверки схемы.  
  
 Объект <xref:System.Xml.Schema.ValidationEventHandler>, добавленный к набору <xref:System.Xml.Schema.XmlSchemaSet>, является делегатом, вызывающим метод ответного вызова `ValidationCallback` для обработки ошибок и предупреждений проверки схемы.  
  
 Ниже приводится полный пример кода, а пользовательская схема выводится на консоль.  
  
 [!code-cpp[XmlSchemaCreateExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#1)]
 [!code-csharp[XmlSchemaCreateExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#1)]
 [!code-vb[XmlSchemaCreateExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
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
```  
  
## <a name="see-also"></a>См. также:

- [Общие сведения об модели объектов XML-схемы](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Чтение и запись XML-схем](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Обход XML-схем](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [Изменение XML-схем](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [Включение или импорт XML-схем](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [XmlSchemaSet для компиляции схемы](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Набор сведений для постсхемной компиляции](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
