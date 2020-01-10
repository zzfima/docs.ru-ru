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
# <a name="editing-xml-schemas"></a><span data-ttu-id="8bf07-102">Изменение XML-схем</span><span class="sxs-lookup"><span data-stu-id="8bf07-102">Editing XML Schemas</span></span>

<span data-ttu-id="8bf07-103">Изменение схем XML является одной из самых важных возможностей модели SOM.</span><span class="sxs-lookup"><span data-stu-id="8bf07-103">Editing an XML schema is one of the most important features of the Schema Object Model (SOM).</span></span> <span data-ttu-id="8bf07-104">Все свойства модели SOM, относящиеся к работе перед компиляцией схемы, можно использовать для изменения существующих значений в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="8bf07-104">All of the pre-schema-compilation properties of the SOM can be used to change the existing values in an XML schema.</span></span> <span data-ttu-id="8bf07-105">Затем можно повторно скомпилировать схему XML, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="8bf07-105">The XML schema can then be recompiled to reflect the changes.</span></span>

<span data-ttu-id="8bf07-106">Первым шагом в изменении схемы, загруженной в модель SOM, является обзор схемы.</span><span class="sxs-lookup"><span data-stu-id="8bf07-106">The first step in editing a schema loaded into the SOM is to traverse the schema.</span></span> <span data-ttu-id="8bf07-107">Перед изменением схемы следует ознакомиться с обзором схемы, в котором используется API модели SOM.</span><span class="sxs-lookup"><span data-stu-id="8bf07-107">You should be familiar with traversing a schema using the SOM API before you attempt to edit a schema.</span></span> <span data-ttu-id="8bf07-108">Также следует ознакомиться со свойствами информационного набора PSCI, относящиеся к работе перед компиляцией схемы и после нее.</span><span class="sxs-lookup"><span data-stu-id="8bf07-108">You should also be familiar with the pre- and post-schema-compilation properties of the Post-Schema-Compilation-Infoset (PSCI).</span></span>

## <a name="editing-an-xml-schema"></a><span data-ttu-id="8bf07-109">Изменение схемы XML</span><span class="sxs-lookup"><span data-stu-id="8bf07-109">Editing an XML Schema</span></span>

<span data-ttu-id="8bf07-110">В этом разделе приводятся два примера кода, в которых изменяется пользовательская схема, созданная в руководстве по [созданию схем XML](../../../../docs/standard/data/xml/building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="8bf07-110">In this section, two code examples are provided, both of which edit the customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span> <span data-ttu-id="8bf07-111">В первом примере кода добавляется новый элемент `PhoneNumber` в элемент `Customer`, а во втором примере кода добавляется новый атрибут `Title` в элемент `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="8bf07-111">The first code example adds a new `PhoneNumber` element to the `Customer` element and the second code example adds a new `Title` attribute to the `FirstName` element.</span></span> <span data-ttu-id="8bf07-112">В первом образце для обзора пользовательской схемы используется коллекция <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> типа «после компиляции схемы», а во втором примере кода используется коллекция <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> типа «перед компиляцией схемы».</span><span class="sxs-lookup"><span data-stu-id="8bf07-112">The first sample also uses the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection as the means of traversing the customer schema while the second code example uses the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

### <a name="phonenumber-element-example"></a><span data-ttu-id="8bf07-113">Пример элемента PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="8bf07-113">PhoneNumber Element Example</span></span>

<span data-ttu-id="8bf07-114">В первом примере кода добавляется новый элемент `PhoneNumber` в элемент `Customer` пользовательской схемы.</span><span class="sxs-lookup"><span data-stu-id="8bf07-114">This first code example adds a new `PhoneNumber` element to the `Customer` element of the customer schema.</span></span> <span data-ttu-id="8bf07-115">Пример кода изменяет пользовательскую схему посредством следующих шагов.</span><span class="sxs-lookup"><span data-stu-id="8bf07-115">The code example edits the customer schema in the following steps.</span></span>

1. <span data-ttu-id="8bf07-116">Добавление пользовательской схемы в новый объект <xref:System.Xml.Schema.XmlSchemaSet>, а затем ее компиляция.</span><span class="sxs-lookup"><span data-stu-id="8bf07-116">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="8bf07-117">Любые предупреждения и ошибки проверки схемы, обнаруженные в процессе ее чтения или компиляции, обрабатываются делегатом <xref:System.Xml.Schema.ValidationEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-117">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>

2. <span data-ttu-id="8bf07-118">Получение скомпилированного объекта <xref:System.Xml.Schema.XmlSchema> из <xref:System.Xml.Schema.XmlSchemaSet> путем итерации по свойству <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-118">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="8bf07-119">Так как схема компилируется, свойства Post-Schema-Compilation-Infoset (PSCI) доступны.</span><span class="sxs-lookup"><span data-stu-id="8bf07-119">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>

3. <span data-ttu-id="8bf07-120">Создание элемента `PhoneNumber` с использованием класса <xref:System.Xml.Schema.XmlSchemaElement>, ограничение простого типа `xs:string` с использованием классов <xref:System.Xml.Schema.XmlSchemaSimpleType> и <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>, добавление аспекта шаблона в свойство <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> ограничения, добавление ограничения в свойство <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> простого типа и добавление простого типа в свойство <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> элемента `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="8bf07-120">Creates the `PhoneNumber` element using the <xref:System.Xml.Schema.XmlSchemaElement> class, the `xs:string` simple type restriction using the <xref:System.Xml.Schema.XmlSchemaSimpleType> and <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> classes, adds a pattern facet to the <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> property of the restriction, and adds the restriction to the <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> property of the simple type and the simple type to the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> of the `PhoneNumber` element.</span></span>

4. <span data-ttu-id="8bf07-121">Проход по всем элементам <xref:System.Xml.Schema.XmlSchemaElement> в коллекции <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> для коллекции <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> типа «после компиляции схемы».</span><span class="sxs-lookup"><span data-stu-id="8bf07-121">Iterates over each <xref:System.Xml.Schema.XmlSchemaElement> in the <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> collection of the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span>

5. <span data-ttu-id="8bf07-122">Если свойство <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> элемента имеет значение `"Customer"`, возвращается сложный тип элемента `Customer` с использованием класса <xref:System.Xml.Schema.XmlSchemaComplexType> и примитив sequence сложного типа с использованием класса <xref:System.Xml.Schema.XmlSchemaSequence>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-122">If the <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> of the element is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>

6. <span data-ttu-id="8bf07-123">Добавление нового элемента `PhoneNumber` в последовательность, содержащую существующие элементы `FirstName` и `LastName`, с использованием коллекции <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> типа «перед компиляцией схемы» для последовательности.</span><span class="sxs-lookup"><span data-stu-id="8bf07-123">Adds the new `PhoneNumber` element to the sequence containing the existing `FirstName` and `LastName` elements using the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> collection of the sequence.</span></span>

7. <span data-ttu-id="8bf07-124">Наконец, повторная обработка и компиляция измененного объекта <xref:System.Xml.Schema.XmlSchema> с помощью методов <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> и <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> и запись его в консоль.</span><span class="sxs-lookup"><span data-stu-id="8bf07-124">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>

<span data-ttu-id="8bf07-125">Ниже приведен полный пример кода.</span><span class="sxs-lookup"><span data-stu-id="8bf07-125">The following is the complete code example.</span></span>

[!code-cpp[XmlSchemaEditExample1#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample1/CPP/XmlSchemaEditExample1.cpp#1)]
[!code-csharp[XmlSchemaEditExample1#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample1/CS/XmlSchemaEditExample1.cs#1)]
[!code-vb[XmlSchemaEditExample1#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample1/VB/XmlSchemaEditExample1.vb#1)]

<span data-ttu-id="8bf07-126">Ниже приведена измененная пользовательская [схема XML](../../../../docs/standard/data/xml/building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="8bf07-126">The following is the modified customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span>

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

### <a name="title-attribute-example"></a><span data-ttu-id="8bf07-127">Пример атрибута Title</span><span class="sxs-lookup"><span data-stu-id="8bf07-127">Title Attribute Example</span></span>

<span data-ttu-id="8bf07-128">Во втором примере кода добавляется новый атрибут `Title` в элемент `FirstName` пользовательской схемы.</span><span class="sxs-lookup"><span data-stu-id="8bf07-128">This second code example, adds a new `Title` attribute to the `FirstName` element of the customer schema.</span></span> <span data-ttu-id="8bf07-129">В первом примере кода элемент `FirstName` имеет тип `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="8bf07-129">In the first code example, the type of the `FirstName` element is `xs:string`.</span></span> <span data-ttu-id="8bf07-130">Чтобы элемент `FirstName` имел атрибут со строковым содержимым, его тип необходимо изменить на сложный тип с простым расширением содержимого в модели содержимого.</span><span class="sxs-lookup"><span data-stu-id="8bf07-130">For the `FirstName` element to have an attribute along with string content, its type must be changed to a complex type with a simple content extension content model.</span></span>

<span data-ttu-id="8bf07-131">Пример кода изменяет пользовательскую схему посредством следующих шагов.</span><span class="sxs-lookup"><span data-stu-id="8bf07-131">The code example edits the customer schema in the following steps.</span></span>

1. <span data-ttu-id="8bf07-132">Добавление пользовательской схемы в новый объект <xref:System.Xml.Schema.XmlSchemaSet>, а затем ее компиляция.</span><span class="sxs-lookup"><span data-stu-id="8bf07-132">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="8bf07-133">Любые предупреждения и ошибки проверки схемы, обнаруженные в процессе ее чтения или компиляции, обрабатываются делегатом <xref:System.Xml.Schema.ValidationEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-133">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>

2. <span data-ttu-id="8bf07-134">Получение скомпилированного объекта <xref:System.Xml.Schema.XmlSchema> из <xref:System.Xml.Schema.XmlSchemaSet> путем итерации по свойству <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-134">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="8bf07-135">Так как схема компилируется, свойства Post-Schema-Compilation-Infoset (PSCI) доступны.</span><span class="sxs-lookup"><span data-stu-id="8bf07-135">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>

3. <span data-ttu-id="8bf07-136">Создание нового сложного типа для элемента `FirstName` с использованием класса <xref:System.Xml.Schema.XmlSchemaComplexType>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-136">Creates a new complex type for the `FirstName` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>

4. <span data-ttu-id="8bf07-137">Создание нового простого расширения содержимого с базовым типом `xs:string` с использованием классов <xref:System.Xml.Schema.XmlSchemaSimpleContent> и <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-137">Creates a new simple content extension, with a base type of `xs:string`, using the <xref:System.Xml.Schema.XmlSchemaSimpleContent> and <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension> classes.</span></span>

5. <span data-ttu-id="8bf07-138">Создание нового атрибута `Title` с использованием класса <xref:System.Xml.Schema.XmlSchemaAttribute> со значением <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> для `xs:string`, и добавление атрибута в простое расширение содержимого.</span><span class="sxs-lookup"><span data-stu-id="8bf07-138">Creates the new `Title` attribute using the <xref:System.Xml.Schema.XmlSchemaAttribute> class, with a <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> of `xs:string` and adds the attribute to the simple content extension.</span></span>

6. <span data-ttu-id="8bf07-139">Установка простого расширения содержимого для модели простого содержимого и простого содержимого для модели сложного типа.</span><span class="sxs-lookup"><span data-stu-id="8bf07-139">Sets the content model of the simple content to the simple content extension and the content model of the complex type to the simple content.</span></span>

7. <span data-ttu-id="8bf07-140">Добавление нового сложного типа в коллекцию <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> типа «перед компиляцией схемы».</span><span class="sxs-lookup"><span data-stu-id="8bf07-140">Adds the new complex type to the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

8. <span data-ttu-id="8bf07-141">Выполнение итерации по каждому <xref:System.Xml.Schema.XmlSchemaObject> в коллекции <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> перед компиляцией схемы.</span><span class="sxs-lookup"><span data-stu-id="8bf07-141">Iterates over each <xref:System.Xml.Schema.XmlSchemaObject> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

> [!NOTE]
> <span data-ttu-id="8bf07-142">Поскольку элемент `FirstName` не является глобальным в схеме, он недоступен в коллекциях <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> и <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-142">Because the `FirstName` element is not a global element in the schema, it is not available in the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> or <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collections.</span></span> <span data-ttu-id="8bf07-143">Пример кода определяет расположение элемента `FirstName` по расположению элемента `Customer`.</span><span class="sxs-lookup"><span data-stu-id="8bf07-143">The code example locates the `FirstName` element by first locating the `Customer` element.</span></span>
>
> <span data-ttu-id="8bf07-144">В первом примере кода обзор схемы выполняется с помощью коллекции <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> типа «после компиляции схемы».</span><span class="sxs-lookup"><span data-stu-id="8bf07-144">The first code example traversed the schema using the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="8bf07-145">В этом образце для обзора схемы используется коллекция <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> типа «перед компиляцией схемы».</span><span class="sxs-lookup"><span data-stu-id="8bf07-145">In this sample, the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection is used to traverse the schema.</span></span> <span data-ttu-id="8bf07-146">Обе коллекции предоставляют доступ к глобальным элементам схемы, но проход по коллекции <xref:System.Xml.Schema.XmlSchema.Items%2A> занимает больше времени, поскольку необходимо проходить по всем глобальным элементам в схеме, а в схеме отсутствуют свойства PSCI.</span><span class="sxs-lookup"><span data-stu-id="8bf07-146">While both collections provide access to the global elements in the schema, iterating through the <xref:System.Xml.Schema.XmlSchema.Items%2A> collection is more time consuming because you must iterate over all global elements in the schema and it does not have any PSCI properties.</span></span> <span data-ttu-id="8bf07-147">Коллекции PSCI (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType> и т. д.) предоставляют прямой доступ к своим глобальным элементам, атрибутам, типам и их свойствам PSCI.</span><span class="sxs-lookup"><span data-stu-id="8bf07-147">The PSCI collections (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType>, and so on) provide direct access to their global elements, attributes, and types and their PSCI properties.</span></span>

1. <span data-ttu-id="8bf07-148">Если объект <xref:System.Xml.Schema.XmlSchemaObject> является элементом, значением <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> которого является `"Customer"`, возвращается сложный тип элемента `Customer` с использованием класса <xref:System.Xml.Schema.XmlSchemaComplexType> и примитив sequence сложного типа с использованием класса <xref:System.Xml.Schema.XmlSchemaSequence>.</span><span class="sxs-lookup"><span data-stu-id="8bf07-148">If the <xref:System.Xml.Schema.XmlSchemaObject> is an element, whose <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>

2. <span data-ttu-id="8bf07-149">Выполнение итерации по каждому <xref:System.Xml.Schema.XmlSchemaParticle> в коллекции <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> перед компиляцией схемы.</span><span class="sxs-lookup"><span data-stu-id="8bf07-149">Iterates over each <xref:System.Xml.Schema.XmlSchemaParticle> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="8bf07-150">Если объект <xref:System.Xml.Schema.XmlSchemaParticle> является элементом, значением <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> которого является `"FirstName"`, в свойстве <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> элемента `FirstName` задается новый сложный тип `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="8bf07-150">If the <xref:System.Xml.Schema.XmlSchemaParticle> is an element, who's <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"FirstName"`, sets the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> of the `FirstName` element to the new `FirstName` complex type.</span></span>

4. <span data-ttu-id="8bf07-151">Наконец, повторная обработка и компиляция измененного объекта <xref:System.Xml.Schema.XmlSchema> с помощью методов <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> и <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> класса <xref:System.Xml.Schema.XmlSchemaSet> и запись его в консоль.</span><span class="sxs-lookup"><span data-stu-id="8bf07-151">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>

<span data-ttu-id="8bf07-152">Ниже приведен полный пример кода.</span><span class="sxs-lookup"><span data-stu-id="8bf07-152">The following is the complete code example.</span></span>

[!code-cpp[XmlSchemaEditExample2#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample2/CPP/XmlSchemaEditExample2.cpp#1)]
[!code-csharp[XmlSchemaEditExample2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample2/CS/XmlSchemaEditExample2.cs#1)]
[!code-vb[XmlSchemaEditExample2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample2/VB/XmlSchemaEditExample2.vb#1)]

<span data-ttu-id="8bf07-153">Ниже приведена измененная пользовательская [схема XML](../../../../docs/standard/data/xml/building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="8bf07-153">The following is the modified customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8bf07-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="8bf07-154">See also</span></span>

- [<span data-ttu-id="8bf07-155">Общие сведения об модели объектов XML-схемы</span><span class="sxs-lookup"><span data-stu-id="8bf07-155">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="8bf07-156">Чтение и запись XML-схем</span><span class="sxs-lookup"><span data-stu-id="8bf07-156">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="8bf07-157">Построение XML-схем</span><span class="sxs-lookup"><span data-stu-id="8bf07-157">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [<span data-ttu-id="8bf07-158">Обход XML-схем</span><span class="sxs-lookup"><span data-stu-id="8bf07-158">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="8bf07-159">Включение или импорт XML-схем</span><span class="sxs-lookup"><span data-stu-id="8bf07-159">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="8bf07-160">XmlSchemaSet для компиляции схемы</span><span class="sxs-lookup"><span data-stu-id="8bf07-160">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="8bf07-161">Набор сведений для постсхемной компиляции</span><span class="sxs-lookup"><span data-stu-id="8bf07-161">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
