---
title: Принудительная проверка с помощью XmlSchemaValidator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 911d4460-dd91-4958-85b2-2ca3299f9ec6
ms.openlocfilehash: 6a0cc110c2b8bcd97b9f5c16a344db5a63046353
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709807"
---
# <a name="xmlschemavalidator-push-based-validation"></a><span data-ttu-id="06791-102">Принудительная проверка с помощью XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="06791-102">XmlSchemaValidator Push-Based Validation</span></span>

<span data-ttu-id="06791-103">Класс <xref:System.Xml.Schema.XmlSchemaValidator> предоставляет эффективный, высокопроизводительный механизм для принудительной проверки XML-данных по схемам XML.</span><span class="sxs-lookup"><span data-stu-id="06791-103">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides an efficient, high-performance mechanism to validate XML data against XML schemas in a push-based manner.</span></span> <span data-ttu-id="06791-104">Например, класс <xref:System.Xml.Schema.XmlSchemaValidator> позволяет проверять информационный набор XML локально, без сериализации в виде XML-документа, а затем повторно выполнить синтаксический анализ с помощью проверяющего модуля чтения XML.</span><span class="sxs-lookup"><span data-stu-id="06791-104">For example, the <xref:System.Xml.Schema.XmlSchemaValidator> class allows you to validate an XML infoset in-place without having to serialize it as an XML document and then reparse the document using a validating XML reader.</span></span>

<span data-ttu-id="06791-105">Класс <xref:System.Xml.Schema.XmlSchemaValidator> можно использовать в расширенных сценариях, например, для создания подсистем проверки в пользовательских источниках XML-данных или проверяющего модуля записи XML.</span><span class="sxs-lookup"><span data-stu-id="06791-105">The <xref:System.Xml.Schema.XmlSchemaValidator> class can be used in advanced scenarios such as building validation engines over custom XML data sources or as a way to build a validating XML writer.</span></span>

<span data-ttu-id="06791-106">В следующем примере класс <xref:System.Xml.Schema.XmlSchemaValidator> используется для проверки файла `contosoBooks.xml` по схеме `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="06791-106">The following is an example of using the <xref:System.Xml.Schema.XmlSchemaValidator> class to validate the `contosoBooks.xml` file against the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="06791-107">Класс <xref:System.Xml.Serialization.XmlSerializer> в примере используется для десериализации файла `contosoBooks.xml` и передачи значений узлов методам класса <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-107">The example uses the <xref:System.Xml.Serialization.XmlSerializer> class to deserialize the `contosoBooks.xml` file and pass the value of the nodes to the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

> [!NOTE]
> <span data-ttu-id="06791-108">Этот пример приводится во всех подразделах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="06791-108">This example is used throughout the sections of this topic.</span></span>

[!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
[!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]

<span data-ttu-id="06791-109">В примере в качестве входных данных используется файл `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="06791-109">The example takes the `contosoBooks.xml` file as input.</span></span>

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

<span data-ttu-id="06791-110">В примере также в качестве входных данных используется `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="06791-110">The example also takes the `contosoBooks.xsd` as an input.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.contoso.com/books" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="bookstore">
        <xs:complexType>
            <xs:sequence>
                <xs:element maxOccurs="unbounded" name="book">
                    <xs:complexType>
                        <xs:sequence>
                            <xs:element name="title" type="xs:string" />
                            <xs:element name="author">
                                <xs:complexType>
                                    <xs:sequence>
                                        <xs:element minOccurs="0" name="name" type="xs:string" />
                                        <xs:element minOccurs="0" name="first-name" type="xs:string" />
                                        <xs:element minOccurs="0" name="last-name" type="xs:string" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="price" type="xs:decimal" />
                        </xs:sequence>
                        <xs:attribute name="genre" type="xs:string" use="required" />
                        <xs:attribute name="publicationdate" type="xs:date" use="required" />
                        <xs:attribute name="ISBN" type="xs:string" use="required" />
                    </xs:complexType>
                </xs:element>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
```

## <a name="validating-xml-data-using-xmlschemavalidator"></a><span data-ttu-id="06791-111">Проверка XML-данных с помощью XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="06791-111">Validating XML Data using XmlSchemaValidator</span></span>

<span data-ttu-id="06791-112">Чтобы начать проверку информационного набора XML, необходимо вначале инициализировать новый экземпляр класса <xref:System.Xml.Schema.XmlSchemaValidator> с помощью конструктора <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-112">To begin validating an XML infoset, you must first initialize a new instance of the <xref:System.Xml.Schema.XmlSchemaValidator> class using the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor.</span></span>

<span data-ttu-id="06791-113">Конструктор <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> принимает объекты <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet> и <xref:System.Xml.XmlNamespaceManager>, а также значение <xref:System.Xml.Schema.XmlSchemaValidationFlags> в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="06791-113">The <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor takes <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet>, and <xref:System.Xml.XmlNamespaceManager> objects as parameters as well as a <xref:System.Xml.Schema.XmlSchemaValidationFlags> value as a parameter.</span></span> <span data-ttu-id="06791-114">Объект <xref:System.Xml.XmlNameTable> используется для атомизации известных строк пространств имен (таких как пространство имен схемы, пространство имен XML и так далее) и передает их методу <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> при проверке простого содержимого.</span><span class="sxs-lookup"><span data-stu-id="06791-114">The <xref:System.Xml.XmlNameTable> object is used to atomize well-known namespace strings like the schema namespace, the XML namespace, and so on, and is passed to the <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> method while validating simple content.</span></span> <span data-ttu-id="06791-115">Объект <xref:System.Xml.Schema.XmlSchemaSet> содержит схемы XML, используемые при проверке информационного набора XML.</span><span class="sxs-lookup"><span data-stu-id="06791-115">The <xref:System.Xml.Schema.XmlSchemaSet> object contains the XML schemas used to validate the XML infoset.</span></span> <span data-ttu-id="06791-116">Объект <xref:System.Xml.XmlNamespaceManager> применяется для разрешения пространства имен во время проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-116">The <xref:System.Xml.XmlNamespaceManager> object is used to resolve namespaces encountered during validation.</span></span> <span data-ttu-id="06791-117">Значение <xref:System.Xml.Schema.XmlSchemaValidationFlags> используется для отключения определенных функций проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-117">The <xref:System.Xml.Schema.XmlSchemaValidationFlags> value is used to disable certain features of validation.</span></span>

<span data-ttu-id="06791-118">Дополнительные сведения о конструкторе <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-118">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="initializing-validation"></a><span data-ttu-id="06791-119">Инициализация проверки</span><span class="sxs-lookup"><span data-stu-id="06791-119">Initializing Validation</span></span>

<span data-ttu-id="06791-120">После создания объект <xref:System.Xml.Schema.XmlSchemaValidator> имеет два перегруженных метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, которые применяются для инициализации состояния объекта <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-120">After an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed, there are two overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods used to initialize the state of the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="06791-121">Ниже представлены два этих метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-121">The following are the two <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

<span data-ttu-id="06791-122">Метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, применяющийся по умолчанию, инициализирует начальное состояние объекта <xref:System.Xml.Schema.XmlSchemaValidator>, а перегруженный метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, принимающий в качестве параметра <xref:System.Xml.Schema.XmlSchemaObject>, инициализирует начальное состояние объекта <xref:System.Xml.Schema.XmlSchemaValidator> для частичной проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-122">The default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state, and the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>

<span data-ttu-id="06791-123">Оба метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> можно вызвать только сразу после создания объекта <xref:System.Xml.Schema.XmlSchemaValidator> или вызова <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-123">Both <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods can only be called immediately after an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed or after a call to <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.</span></span>

<span data-ttu-id="06791-124">Пример метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> см. в примере во введении.</span><span class="sxs-lookup"><span data-stu-id="06791-124">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method, see the example in the introduction.</span></span> <span data-ttu-id="06791-125">Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-125">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="partial-validation"></a><span data-ttu-id="06791-126">Частичная проверка</span><span class="sxs-lookup"><span data-stu-id="06791-126">Partial Validation</span></span>

<span data-ttu-id="06791-127">Метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, принимающий в качестве параметра <xref:System.Xml.Schema.XmlSchemaObject>, инициализирует начальное состояние объекта <xref:System.Xml.Schema.XmlSchemaValidator> для частичной проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-127">The <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>

<span data-ttu-id="06791-128">В следующем примере объект <xref:System.Xml.Schema.XmlSchemaObject> инициализируется для частичной проверки с помощью метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="06791-128">In the following example, an <xref:System.Xml.Schema.XmlSchemaObject> is initialized for partial validation using the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="06791-129">Элемент схемы `orderNumber` передается путем выбора <xref:System.Xml.XmlQualifiedName> в коллекции <xref:System.Xml.Schema.XmlSchemaObjectTable>, возвращаемой свойством <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> объекта <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="06791-129">The `orderNumber` schema element is passed by selecting the schema element by <xref:System.Xml.XmlQualifiedName> in the <xref:System.Xml.Schema.XmlSchemaObjectTable> collection returned by the <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> object.</span></span> <span data-ttu-id="06791-130">Затем объект <xref:System.Xml.Schema.XmlSchemaValidator> проверяет этот элемент.</span><span class="sxs-lookup"><span data-stu-id="06791-130">The <xref:System.Xml.Schema.XmlSchemaValidator> object then validates this specific element.</span></span>

```vb
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
schemaSet.Compile()
Dim nameTable As NameTable = New NameTable()
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)

Dim validator As XmlSchemaValidator = New XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None)
validator.Initialize(schemaSet.GlobalElements.Item(New XmlQualifiedName("orderNumber")))

validator.ValidateElement("orderNumber", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateText("123")
validator.ValidateEndElement(Nothing)
```

```csharp
XmlSchemaSet schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
schemaSet.Compile();
NameTable nameTable = new NameTable();
XmlNamespaceManager manager = new XmlNamespaceManager(nameTable);

XmlSchemaValidator validator = new XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize(schemaSet.GlobalElements[new XmlQualifiedName("orderNumber")]);

validator.ValidateElement("orderNumber", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateText("123");
validator.ValidateEndElement(null);
```

<span data-ttu-id="06791-131">Этот пример принимает в качестве входных данных следующую схему XML.</span><span class="sxs-lookup"><span data-stu-id="06791-131">The example takes the following XML schema as input.</span></span>

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="orderNumber" type="xs:int" />
</xs:schema>
```

<span data-ttu-id="06791-132">Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-132">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="adding-additional-schemas"></a><span data-ttu-id="06791-133">Добавление дополнительных схем</span><span class="sxs-lookup"><span data-stu-id="06791-133">Adding Additional Schemas</span></span>

<span data-ttu-id="06791-134">Метод <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> класса <xref:System.Xml.Schema.XmlSchemaValidator> используется для добавления схемы XML в набор схем, который применяется во время проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-134">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method of the <xref:System.Xml.Schema.XmlSchemaValidator> class is used to add an XML schema to the set of schemas used during validation.</span></span> <span data-ttu-id="06791-135">Метод <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> может использоваться для моделирования результата обнаружения встроенной схемы XML в проверяемом информационном наборе XML.</span><span class="sxs-lookup"><span data-stu-id="06791-135">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method can be used to simulate the effect of encountering an inline XML schema in the XML infoset being validated.</span></span>

> [!NOTE]
> <span data-ttu-id="06791-136">Целевое пространство имен параметра <xref:System.Xml.Schema.XmlSchema> не может соответствовать пространству имен элемента или атрибута, уже обнаруженного объектом <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-136">The target namespace of the <xref:System.Xml.Schema.XmlSchema> parameter cannot match that of any element or attribute already encountered by the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>
>
> <span data-ttu-id="06791-137">Если значение <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> не было передано в качестве параметра конструктору <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, метод <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> не предпринимает никаких действий.</span><span class="sxs-lookup"><span data-stu-id="06791-137">If the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> value was not passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method does nothing.</span></span>

<span data-ttu-id="06791-138">Результат метода <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> зависит от текущего контекста проверяемого XML-узла.</span><span class="sxs-lookup"><span data-stu-id="06791-138">The result of the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method is dependant on the current XML node context being validated.</span></span> <span data-ttu-id="06791-139">Дополнительные сведения о контексте проверки см. в подразделе «Контекст проверки» этого раздела.</span><span class="sxs-lookup"><span data-stu-id="06791-139">For more information about validation contexts, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="06791-140">Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-140">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="validating-elements-attributes-and-content"></a><span data-ttu-id="06791-141">Проверка элементов, атрибутов и содержимого</span><span class="sxs-lookup"><span data-stu-id="06791-141">Validating Elements, Attributes, and Content</span></span>

<span data-ttu-id="06791-142">Класс <xref:System.Xml.Schema.XmlSchemaValidator> предоставляет несколько методов для проверки по схемам XML элементов, атрибутов и содержимого информационного набора XML.</span><span class="sxs-lookup"><span data-stu-id="06791-142">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides several methods used to validate elements, attributes, and content in an XML infoset against XML schemas.</span></span> <span data-ttu-id="06791-143">В следующей таблице описан каждый из этих методов.</span><span class="sxs-lookup"><span data-stu-id="06791-143">The following table describes each of these methods.</span></span>

|<span data-ttu-id="06791-144">Метод</span><span class="sxs-lookup"><span data-stu-id="06791-144">Method</span></span>|<span data-ttu-id="06791-145">Описание</span><span class="sxs-lookup"><span data-stu-id="06791-145">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="06791-146">Проверяет имя элемента в текущем контексте.</span><span class="sxs-lookup"><span data-stu-id="06791-146">Validates the element name in the current context.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="06791-147">Проверяет атрибут в контексте текущего элемента или по объекту <xref:System.Xml.Schema.XmlSchemaAttribute>, переданному в качестве параметра методу <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-147">Validates the attribute in the current element context or against the <xref:System.Xml.Schema.XmlSchemaAttribute> object passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="06791-148">Проверяет наличие всех необходимых атрибутов в контексте элемента и подготавливает объект <xref:System.Xml.Schema.XmlSchemaValidator> для проверки содержимого дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-148">Verifies whether all the required attributes in the element context are present and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate the child content of the element.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="06791-149">Проверяет, разрешен ли текст в контексте текущего элемента и накапливает текст для проверки, если текущий элемент имеет простое содержимое.</span><span class="sxs-lookup"><span data-stu-id="06791-149">Validates whether text is allowed in the current element context, and accumulates the text for validation if the current element has simple content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="06791-150">Проверяет, разрешены ли пробелы в контексте текущего элемента и накапливает пробелы для проверки, если текущий элемент имеет простое содержимое.</span><span class="sxs-lookup"><span data-stu-id="06791-150">Validates whether white-space is allowed in the current element context, and accumulates the white-space for validation whether the current element has simple content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="06791-151">Проверяет допустимость текстового содержимого элемента с простым содержимым и полноту содержимого текущего элемента для элементов со сложным содержимым.</span><span class="sxs-lookup"><span data-stu-id="06791-151">Verifies whether the text content of the element is valid according to its data type for elements with simple content, and verifies whether the content of the current element is complete for elements with complex content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="06791-152">Пропускает проверку содержимого текущего элемента и подготавливает объект <xref:System.Xml.Schema.XmlSchemaValidator> для проверки содержимого в контексте родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-152">Skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="06791-153">Завершает проверку и проверяет ограничения удостоверения для всего XML-документа, если указан параметр проверки <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints>.</span><span class="sxs-lookup"><span data-stu-id="06791-153">Ends validation and checks identity constraints for the entire XML document if the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints> validation option is set.</span></span>|

> [!NOTE]
> <span data-ttu-id="06791-154">В классе <xref:System.Xml.Schema.XmlSchemaValidator> объявляется переход между состояниями, определяющий последовательность и вхождение вызовов каждого метода, описанного в приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="06791-154">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods described in the previous table.</span></span> <span data-ttu-id="06791-155">Специальный переход между состояниями класса <xref:System.Xml.Schema.XmlSchemaValidator> описан в подразделе «Переход между состояниями XmlSchemaValidator» этого раздела.</span><span class="sxs-lookup"><span data-stu-id="06791-155">The specific state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class is described in the "XmlSchemaValidator State Transition" section of this topic.</span></span>

<span data-ttu-id="06791-156">Пример методов, которые используются для проверки элементов, атрибутов и содержимого в информационном наборе XML, см. в примерах предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="06791-156">For an example of the methods used to validate elements, attributes, and content in an XML infoset, see the example in the previous section.</span></span> <span data-ttu-id="06791-157">Дополнительные сведения об этих методах см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-157">For more information about these methods, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="validating-content-using-an-xmlvaluegetter"></a><span data-ttu-id="06791-158">Проверка содержимого с помощью XmlValueGetter</span><span class="sxs-lookup"><span data-stu-id="06791-158">Validating Content Using an XmlValueGetter</span></span>

<span data-ttu-id="06791-159"><xref:System.Xml.Schema.XmlValueGetter>`delegate` может использоваться для передачи значения узла атрибута, текста или пробела как типов CLR, совместимых с типами XSD для узла атрибута, текста или пробела.</span><span class="sxs-lookup"><span data-stu-id="06791-159">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` can be used to pass the value of attribute, text, or white-space nodes as a Common Language Runtime (CLR) types compatible with the XML Schema Definition Language (XSD) type of the attribute, text, or white-space node.</span></span> <span data-ttu-id="06791-160"><xref:System.Xml.Schema.XmlValueGetter>`delegate` полезно использовать, если значение CLR узла атрибута, текста или пробела уже доступно, так как это позволяет избежать затрат на преобразование в тип `string` и последующий повторный синтаксический анализ для проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-160">An <xref:System.Xml.Schema.XmlValueGetter>`delegate` is useful if the CLR value of an attribute, text, or white-space node is already available, and avoids the cost of converting it to a `string` and then reparsing it again for validation.</span></span>

<span data-ttu-id="06791-161">Методы <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> перегружены и принимают значение узла атрибута, текста или пробела как тип `string` или <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span><span class="sxs-lookup"><span data-stu-id="06791-161">The <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> methods are overloaded and accept the value of attribute, text, or white-space nodes as a `string` or <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span></span>

<span data-ttu-id="06791-162">Следующие методы класса <xref:System.Xml.Schema.XmlSchemaValidator> принимают <xref:System.Xml.Schema.XmlValueGetter>`delegate` в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="06791-162">The following methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlValueGetter>`delegate` as a parameter.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>

<span data-ttu-id="06791-163">Следующий пример <xref:System.Xml.Schema.XmlValueGetter>`delegate` взят из примера класса <xref:System.Xml.Schema.XmlSchemaValidator> во введении.</span><span class="sxs-lookup"><span data-stu-id="06791-163">The following is an example <xref:System.Xml.Schema.XmlValueGetter>`delegate` taken from the <xref:System.Xml.Schema.XmlSchemaValidator> class example in the introduction.</span></span> <span data-ttu-id="06791-164"><xref:System.Xml.Schema.XmlValueGetter>`delegate` возвращает значение атрибута в виде объекта <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="06791-164">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` returns the value of an attribute as a <xref:System.DateTime> object.</span></span> <span data-ttu-id="06791-165">Для проверки объекта <xref:System.DateTime>, возвращенного <xref:System.Xml.Schema.XmlValueGetter>, объект <xref:System.Xml.Schema.XmlSchemaValidator> вначале преобразует его в тип ValueType для типа данных атрибута (ValueType является сопоставлением CLR по умолчанию для типа XSD), а затем проверяет аспекты в преобразованном значении.</span><span class="sxs-lookup"><span data-stu-id="06791-165">To validate this <xref:System.DateTime> object returned by the <xref:System.Xml.Schema.XmlValueGetter>, the <xref:System.Xml.Schema.XmlSchemaValidator> object first converts it to the ValueType (ValueType is the default CLR mapping for the XSD type) for the data type of the attribute and then checks facets on the converted value.</span></span>

```vb
Shared dateTimeGetterContent As Object

Shared Function DateTimeGetterHandle() As Object
    Return dateTimeGetterContent
End Function

Shared Function DateTimeGetter(dateTime As DateTime) As XmlValueGetter
    dateTimeGetterContent = dateTime
    Return New XmlValueGetter(AddressOf DateTimeGetterHandle)
End Function
```

```csharp
static object dateTimeGetterContent;

static object DateTimeGetterHandle()
{
    return dateTimeGetterContent;
}

static XmlValueGetter DateTimeGetter(DateTime dateTime)
{
    dateTimeGetterContent = dateTime;
    return new XmlValueGetter(dateTimeGetterHandle);
}
```

<span data-ttu-id="06791-166">Полный пример <xref:System.Xml.Schema.XmlValueGetter>`delegate` см. во введении.</span><span class="sxs-lookup"><span data-stu-id="06791-166">For a complete example of the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the example in the introduction.</span></span> <span data-ttu-id="06791-167">Дополнительные сведения о <xref:System.Xml.Schema.XmlValueGetter>`delegate` см. в справочной документации по классам <xref:System.Xml.Schema.XmlValueGetter> и <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-167">For more information about the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the <xref:System.Xml.Schema.XmlValueGetter>, and <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="post-schema-validation-information"></a><span data-ttu-id="06791-168">Post-Schema-Validation-Information</span><span class="sxs-lookup"><span data-stu-id="06791-168">Post-Schema-Validation-Information</span></span>

<span data-ttu-id="06791-169">Класс <xref:System.Xml.Schema.XmlSchemaInfo> представляет некоторые сведения после проверки схемы XML-узла, проверенного классом <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-169">The <xref:System.Xml.Schema.XmlSchemaInfo> class represents some of the Post-Schema-Validation-Information of an XML node validated by the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="06791-170">Различные методы класса <xref:System.Xml.Schema.XmlSchemaValidator> принимают объект <xref:System.Xml.Schema.XmlSchemaInfo> в качестве необязательного (`null`) параметра типа `out`.</span><span class="sxs-lookup"><span data-stu-id="06791-170">Various methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an optional, (`null`) `out` parameter.</span></span>

<span data-ttu-id="06791-171">По окончании успешной проверки свойства объекта <xref:System.Xml.Schema.XmlSchemaInfo> принимают значения результатов проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-171">Upon successful validation, properties of the <xref:System.Xml.Schema.XmlSchemaInfo> object are set with the results of the validation.</span></span> <span data-ttu-id="06791-172">Например, по окончании успешной проверки атрибута с помощью метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, свойства <xref:System.Xml.Schema.XmlSchemaInfo>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A> и <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> (если они заданы) объекта <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> принимают значения результатов проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-172">For example, upon successful validation of an attribute using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the <xref:System.Xml.Schema.XmlSchemaInfo> object's (if specified) <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A>, and <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> properties are set with the results of the validation.</span></span>

<span data-ttu-id="06791-173">Следующие методы класса <xref:System.Xml.Schema.XmlSchemaValidator> принимают объект <xref:System.Xml.Schema.XmlSchemaInfo> в качестве выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="06791-173">The following <xref:System.Xml.Schema.XmlSchemaValidator> class methods accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an out parameter.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>

<span data-ttu-id="06791-174">Полный пример класса <xref:System.Xml.Schema.XmlSchemaInfo> см. во введении.</span><span class="sxs-lookup"><span data-stu-id="06791-174">For a complete example of the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the example in the introduction.</span></span> <span data-ttu-id="06791-175">Дополнительные сведения о классе <xref:System.Xml.Schema.XmlSchemaInfo> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaInfo>.</span><span class="sxs-lookup"><span data-stu-id="06791-175">For more information about the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>

### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a><span data-ttu-id="06791-176">Получение ожидаемых примитивов, атрибутов и неуказанных атрибутов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="06791-176">Retrieving Expected Particles, Attributes, and Unspecified Default Attributes</span></span>

<span data-ttu-id="06791-177">Класс <xref:System.Xml.Schema.XmlSchemaValidator> предоставляет методы <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> для получения ожидаемых примитивов, атрибутов и неуказанных атрибутов по умолчанию в текущем контексте проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-177">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> methods to retrieve the expected particles, attributes, and unspecified default attributes in the current validation context.</span></span>

#### <a name="retrieving-expected-particles"></a><span data-ttu-id="06791-178">Получение ожидаемых примитивов</span><span class="sxs-lookup"><span data-stu-id="06791-178">Retrieving Expected Particles</span></span>

<span data-ttu-id="06791-179">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает массив объектов <xref:System.Xml.Schema.XmlSchemaParticle>, содержащих ожидаемые примитивы в текущем контекстном элементе.</span><span class="sxs-lookup"><span data-stu-id="06791-179">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaParticle> objects containing the expected particles in the current element context.</span></span> <span data-ttu-id="06791-180">Допустимыми примитивами, возвращаемыми методом <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, являются экземпляры классов <xref:System.Xml.Schema.XmlSchemaElement> и <xref:System.Xml.Schema.XmlSchemaAny>.</span><span class="sxs-lookup"><span data-stu-id="06791-180">The valid particles that can be returned by the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method are instances of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAny> classes.</span></span>

<span data-ttu-id="06791-181">Если компоновщиком модели содержимого является `xs:sequence`, возвращается только следующий примитив последовательности.</span><span class="sxs-lookup"><span data-stu-id="06791-181">When the compositor for the content model is an `xs:sequence`, only the next particle in the sequence is returned.</span></span> <span data-ttu-id="06791-182">Если компоновщиком модели содержимого является `xs:all` или `xs:choice`, возвращаются все допустимые примитивы, которые могут следовать в текущем контекстном элементе.</span><span class="sxs-lookup"><span data-stu-id="06791-182">If the compositor for the content model is an `xs:all` or an `xs:choice`, then all valid particles that could follow in the current element context are returned.</span></span>

> [!NOTE]
> <span data-ttu-id="06791-183">Если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> вызывается сразу после вызова <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, он возвращает все глобальные элементы.</span><span class="sxs-lookup"><span data-stu-id="06791-183">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called immediately after calling the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns all global elements.</span></span>

<span data-ttu-id="06791-184">Например, в следующей схеме XSD и XML-документе после проверки элемента `book` текущим контекстным элементом является элемент `book`.</span><span class="sxs-lookup"><span data-stu-id="06791-184">For example, in the XML Schema Definition Language (XSD) schema and XML document that follow, after validating the `book` element, the `book` element is the current element context.</span></span> <span data-ttu-id="06791-185">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает массив, который содержит один объект <xref:System.Xml.Schema.XmlSchemaElement>, представляющий элемент `title`.</span><span class="sxs-lookup"><span data-stu-id="06791-185">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `title` element.</span></span> <span data-ttu-id="06791-186">Если контекстом проверки является элемент `title`, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-186">When the validation context is the `title` element, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an empty array.</span></span> <span data-ttu-id="06791-187">Если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> вызывается после проверки элемента `title`, но перед проверкой элемента `description`, он возвращает массив, который содержит один объект <xref:System.Xml.Schema.XmlSchemaElement>, представляющий элемент `description`.</span><span class="sxs-lookup"><span data-stu-id="06791-187">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `title` element has been validated but before the `description` element has been validated, it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `description` element.</span></span> <span data-ttu-id="06791-188">Если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> вызывается после проверки элемента `description`, он возвращает массив, который содержит один объект <xref:System.Xml.Schema.XmlSchemaAny>, представляющий символ-шаблон.</span><span class="sxs-lookup"><span data-stu-id="06791-188">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `description` element has been validated then it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaAny> object representing the wildcard.</span></span>

```vb
Dim reader As XmlReader =  XmlReader.Create("input.xml")

Dim schemaSet As New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
Dim manager As New XmlNamespaceManager(reader.NameTable)

Dim validator As New XmlSchemaValidator(reader.NameTable,schemaSet,manager,XmlSchemaValidationFlags.None)
validator.Initialize()

validator.ValidateElement("book", "", Nothing)

validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("title", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next
validator.ValidateEndElement(Nothing)

For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("description", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

For Each particle As XmlSchemaParticle In validator.GetExpectedParticles()
    Console.WriteLine(particle.GetType())
Next

validator.ValidateElement("namespace", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

validator.ValidateEndElement(Nothing)
```

```csharp
XmlReader reader = XmlReader.Create("input.xml");

var schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
var manager = new XmlNamespaceManager(reader.NameTable);

var validator = new XmlSchemaValidator(reader.NameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize();

validator.ValidateElement("book", "", null);

validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("title", "", null);
validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}
validator.ValidateEndElement(null);

foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("description", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

foreach (XmlSchemaParticle particle in validator.GetExpectedParticles())
{
    Console.WriteLine(particle.GetType());
}

validator.ValidateElement("namespace", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

validator.ValidateEndElement(null);
```

 <span data-ttu-id="06791-189">В примере в качестве входных данных используется следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="06791-189">The example takes the following XML as input:</span></span>

```xml
<xs:schema xmlns:xs="http://www.w3c.org/2001/XMLSchema">
  <xs:element name="book">
    <xs:sequence>
      <xs:element name="title" type="xs:string" />
      <xs:element name="description" type="xs:string" />
      <xs:any processContent="lax" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="06791-190">В примере в качестве входных данных используется следующая схема XSD:</span><span class="sxs-lookup"><span data-stu-id="06791-190">The example takes the following XSD schema as input:</span></span>

```xml
<book>
  <title>My Book</title>
  <description>My Book's Description</description>
  <namespace>System.Xml.Schema</namespace>
</book>
```

> [!NOTE]
> <span data-ttu-id="06791-191">Результаты выполнения методов <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> класса <xref:System.Xml.Schema.XmlSchemaValidator> зависят от текущего подвергаемого проверке контекста.</span><span class="sxs-lookup"><span data-stu-id="06791-191">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="06791-192">Дополнительные сведения см. в подразделе «Контекст проверки» в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="06791-192">For more information, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="06791-193">Пример метода <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> см. в примере во введении.</span><span class="sxs-lookup"><span data-stu-id="06791-193">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="06791-194">Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-194">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="retrieving-expected-attributes"></a><span data-ttu-id="06791-195">Получение ожидаемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="06791-195">Retrieving Expected Attributes</span></span>

<span data-ttu-id="06791-196">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает массив объектов <xref:System.Xml.Schema.XmlSchemaAttribute>, содержащих ожидаемые атрибуты в текущем контекстном элементе.</span><span class="sxs-lookup"><span data-stu-id="06791-196">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaAttribute> objects containing the expected attributes in the current element context.</span></span>

<span data-ttu-id="06791-197">Например, в примере во введении метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> используется для получения всех атрибутов элемента `book`.</span><span class="sxs-lookup"><span data-stu-id="06791-197">For example, in the example in the introduction, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method is used to retrieve all the attributes of the `book` element.</span></span>

<span data-ttu-id="06791-198">Если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> вызывается сразу после метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>, возвращаются все атрибуты, которые могут встретиться в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="06791-198">If you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method immediately after the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> method, all the attributes that could appear in the XML document are returned.</span></span> <span data-ttu-id="06791-199">Но если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> вызывается после одного или нескольких вызовов метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, возвращаются еще не проверенные атрибуты текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-199">However, if you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method after one or more calls to the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the attributes that have not yet been validated for the current element are returned.</span></span>

> [!NOTE]
> <span data-ttu-id="06791-200">Результаты выполнения методов <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> класса <xref:System.Xml.Schema.XmlSchemaValidator> зависят от текущего подвергаемого проверке контекста.</span><span class="sxs-lookup"><span data-stu-id="06791-200">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="06791-201">Дополнительные сведения см. в подразделе «Контекст проверки» в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="06791-201">For more information, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="06791-202">Пример метода <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> см. в примере во введении.</span><span class="sxs-lookup"><span data-stu-id="06791-202">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="06791-203">Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-203">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="retrieving-unspecified-default-attributes"></a><span data-ttu-id="06791-204">Получение неуказанных атрибутов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="06791-204">Retrieving Unspecified Default Attributes</span></span>

<span data-ttu-id="06791-205">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> заполняет список <xref:System.Collections.ArrayList>, заданный объектами <xref:System.Xml.Schema.XmlSchemaAttribute> для всех атрибутов, значениями по умолчанию, которые ранее не были проверены с помощью метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> в контексте элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-205">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method populates the <xref:System.Collections.ArrayList> specified with <xref:System.Xml.Schema.XmlSchemaAttribute> objects for any attributes with default values that have not been previously validated using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method in the element context.</span></span> <span data-ttu-id="06791-206">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> следует вызывать после метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> для каждого атрибута в контексте элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-206">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be called after calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method on each attribute in the element context.</span></span> <span data-ttu-id="06791-207">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> необходимо использовать для определения атрибутов по умолчанию, которые должны быть вставлены в проверяемый XML-документ.</span><span class="sxs-lookup"><span data-stu-id="06791-207">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be used to determine what default attributes are to be inserted into the XML document being validated.</span></span>

<span data-ttu-id="06791-208">Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-208">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="handling-schema-validation-events"></a><span data-ttu-id="06791-209">Обработка событий проверки схемы</span><span class="sxs-lookup"><span data-stu-id="06791-209">Handling Schema Validation Events</span></span>

<span data-ttu-id="06791-210">Предупреждения и ошибки схемы, встретившиеся во время проверки, обрабатываются событием <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> класса <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-210">Schema validation warnings and errors encountered during validation are handled by the <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> event of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

<span data-ttu-id="06791-211">Предупреждения проверки схемы имеют значение <xref:System.Xml.Schema.XmlSeverityType> с типом <xref:System.Xml.Schema.XmlSeverityType.Warning>, а ошибки проверки схемы имеют значение <xref:System.Xml.Schema.XmlSeverityType> с типом <xref:System.Xml.Schema.XmlSeverityType.Error>.</span><span class="sxs-lookup"><span data-stu-id="06791-211">Schema validation warnings have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning> and schema validation errors have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="06791-212">Если обработчик <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> не назначен, вызывается исключение <xref:System.Xml.Schema.XmlSchemaValidationException> для всех ошибок проверки схемы со значением <xref:System.Xml.Schema.XmlSeverityType> и типом <xref:System.Xml.Schema.XmlSeverityType.Error>.</span><span class="sxs-lookup"><span data-stu-id="06791-212">If no <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> has been assigned, an <xref:System.Xml.Schema.XmlSchemaValidationException> is thrown for all schema validation errors with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="06791-213">Однако исключение <xref:System.Xml.Schema.XmlSchemaValidationException> не вызывается для предупреждений проверки схемы со значением <xref:System.Xml.Schema.XmlSeverityType> и типом <xref:System.Xml.Schema.XmlSeverityType.Warning>.</span><span class="sxs-lookup"><span data-stu-id="06791-213">However, an <xref:System.Xml.Schema.XmlSchemaValidationException> is not thrown for schema validation warnings with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning>.</span></span>

<span data-ttu-id="06791-214">Следующий пример обработчика <xref:System.Xml.Schema.ValidationEventHandler> из введения получает предупреждения и ошибки проверки схемы, встретившиеся во время проверки.</span><span class="sxs-lookup"><span data-stu-id="06791-214">The following is an example of a <xref:System.Xml.Schema.ValidationEventHandler> that receives schema validation warnings and errors encountered during schema validation taken from the example in the introduction.</span></span>

```vb
Shared Sub SchemaValidationEventHandler(sender As Object, e As ValidationEventArgs)

    Select Case e.Severity
        Case XmlSeverityType.Error
            Console.WriteLine(vbCrLf & "Error: {0}", e.Message)
            Exit Sub
        Case XmlSeverityType.Warning
            Console.WriteLine(vbCrLf & "Warning: {0}", e.Message)
            Exit Sub
    End Select
End Sub
```

```csharp
static void SchemaValidationEventHandler(object sender, ValidationEventArgs e)
{
    switch (e.Severity)
    {
        case XmlSeverityType.Error:
            Console.WriteLine("\nError: {0}", e.Message);
            break;
        case XmlSeverityType.Warning:
            Console.WriteLine("\nWarning: {0}", e.Message);
            break;
    }
}
```

<span data-ttu-id="06791-215">Полный пример для метода <xref:System.Xml.Schema.ValidationEventHandler> см. во введении.</span><span class="sxs-lookup"><span data-stu-id="06791-215">For a complete example of the <xref:System.Xml.Schema.ValidationEventHandler>, see the example in the introduction.</span></span> <span data-ttu-id="06791-216">Дополнительные сведения см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaInfo>.</span><span class="sxs-lookup"><span data-stu-id="06791-216">For more information, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>

## <a name="xmlschemavalidator-state-transition"></a><span data-ttu-id="06791-217">Переход между состояниями XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="06791-217">XmlSchemaValidator State Transition</span></span>

<span data-ttu-id="06791-218">В классе <xref:System.Xml.Schema.XmlSchemaValidator> объявляется переход между состояниями, определяющий последовательность и вхождение вызовов каждого метода, которые используются для проверки элементов, атрибутов и содержимого в информационном наборе XML.</span><span class="sxs-lookup"><span data-stu-id="06791-218">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods used to validate elements, attributes, and content in an XML infoset.</span></span>

<span data-ttu-id="06791-219">В следующей таблице описан переход между состояниями класса <xref:System.Xml.Schema.XmlSchemaValidator>, а также последовательность и вхождение вызовов методов, возможных в каждом состоянии.</span><span class="sxs-lookup"><span data-stu-id="06791-219">The following table describes the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class, and the sequence and occurrence of method calls that can be made in each state.</span></span>

|<span data-ttu-id="06791-220">Состояние</span><span class="sxs-lookup"><span data-stu-id="06791-220">State</span></span>|<span data-ttu-id="06791-221">Переход</span><span class="sxs-lookup"><span data-stu-id="06791-221">Transition</span></span>|
|-----------|----------------|
|<span data-ttu-id="06791-222">Validate</span><span class="sxs-lookup"><span data-stu-id="06791-222">Validate</span></span>|<span data-ttu-id="06791-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span><span class="sxs-lookup"><span data-stu-id="06791-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span></span>|
|<span data-ttu-id="06791-224">TopLevel</span><span class="sxs-lookup"><span data-stu-id="06791-224">TopLevel</span></span>|<span data-ttu-id="06791-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span><span class="sxs-lookup"><span data-stu-id="06791-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|
|<span data-ttu-id="06791-226">Элемент</span><span class="sxs-lookup"><span data-stu-id="06791-226">Element</span></span>|<span data-ttu-id="06791-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> содержимое\*)?</span><span class="sxs-lookup"><span data-stu-id="06791-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\*)?</span></span> <span data-ttu-id="06791-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="06791-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="06791-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>&#124;</span><span class="sxs-lookup"><span data-stu-id="06791-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="06791-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> содержимого\*&#124;</span><span class="sxs-lookup"><span data-stu-id="06791-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span>|
|<span data-ttu-id="06791-231">Content</span><span class="sxs-lookup"><span data-stu-id="06791-231">Content</span></span>|<span data-ttu-id="06791-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span><span class="sxs-lookup"><span data-stu-id="06791-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|

> [!NOTE]
> <span data-ttu-id="06791-233">Исключение <xref:System.InvalidOperationException> вызывается всеми методами в приведенной выше таблице, если вызов метода выполняется в неверной последовательности в зависимости от текущего состояния объекта <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-233">An <xref:System.InvalidOperationException> is thrown by each of the methods in the table above when the call to the method is made in the incorrect sequence according to the current state of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>

<span data-ttu-id="06791-234">Приведенная выше таблица переходов между состояниями использует символы пунктуации для описания методов и других состояний, которые можно вызывать при переходе состояний класса <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-234">The state transition table above uses punctuation symbols to describe the methods and other states that can be called for each state of the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="06791-235">Используемые символы те же, что и в справочнике по XML-стандартам для определения типа документа (DTD).</span><span class="sxs-lookup"><span data-stu-id="06791-235">The symbols used are the same symbols found in the XML Standards reference for Document Type Definition (DTD).</span></span>

<span data-ttu-id="06791-236">В следующей таблице показано, как символы пунктуации из приведенной выше таблицы перехода состояний влияют на методы и другие состояния, которые можно вызывать при переходе состояний класса <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-236">The following table describes how the punctuation symbols found in the state transition table above affect the methods and other states that can be called for each state in the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

|<span data-ttu-id="06791-237">Символ</span><span class="sxs-lookup"><span data-stu-id="06791-237">Symbol</span></span>|<span data-ttu-id="06791-238">Описание</span><span class="sxs-lookup"><span data-stu-id="06791-238">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="06791-239">&#124;</span><span class="sxs-lookup"><span data-stu-id="06791-239">&#124;</span></span>|<span data-ttu-id="06791-240">Можно вызывать или метод, или состояние (перед чертой или после нее).</span><span class="sxs-lookup"><span data-stu-id="06791-240">Either method or state (the one before the bar or the one after it) can be called.</span></span>|
|<span data-ttu-id="06791-241">?</span><span class="sxs-lookup"><span data-stu-id="06791-241">?</span></span>|<span data-ttu-id="06791-242">Метод или состояние перед вопросительным знаком (?) являются необязательными, но их можно вызывать только один раз.</span><span class="sxs-lookup"><span data-stu-id="06791-242">The method or state that precedes the question mark is optional but if it is called it can only be called once.</span></span>|
|*|<span data-ttu-id="06791-243">Метод или состояние перед символом «звездочки» (\*) являются необязательными. Их можно вызывать несколько раз.</span><span class="sxs-lookup"><span data-stu-id="06791-243">The method or state that precedes the \* symbol is optional, and can be called more than once.</span></span>|

## <a name="validation-context"></a><span data-ttu-id="06791-244">Контекст проверки</span><span class="sxs-lookup"><span data-stu-id="06791-244">Validation Context</span></span>

<span data-ttu-id="06791-245">Методы класса <xref:System.Xml.Schema.XmlSchemaValidator> используются для проверки элементов, атрибутов и содержимого в информационном наборе XML, а также изменения контекста проверки объекта <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-245">The methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset, change the validation context of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="06791-246">Например, метод <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> пропускает проверку содержимого текущего элемента и подготавливает объект <xref:System.Xml.Schema.XmlSchemaValidator> для проверки в контексте родительского элемента. Это равнозначно пропуску проверки всех потомков текущего элемента и вызову метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-246">For example, the <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> method skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context; it is equivalent to skipping validation for all the children of the current element and then calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> method.</span></span>

<span data-ttu-id="06791-247">Результаты выполнения методов <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> класса <xref:System.Xml.Schema.XmlSchemaValidator> зависят от текущего подвергаемого проверке контекста.</span><span class="sxs-lookup"><span data-stu-id="06791-247">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span>

<span data-ttu-id="06791-248">В следующей таблице приводятся результаты выполнения этих методов после вызова одного из методов класса <xref:System.Xml.Schema.XmlSchemaValidator> для проверки элементов, атрибутов и содержимого в информационном наборе XML.</span><span class="sxs-lookup"><span data-stu-id="06791-248">The following table describes the results of calling these methods after calling one of the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset.</span></span>

|<span data-ttu-id="06791-249">Метод</span><span class="sxs-lookup"><span data-stu-id="06791-249">Method</span></span>|<span data-ttu-id="06791-250">GetExpectedParticles</span><span class="sxs-lookup"><span data-stu-id="06791-250">GetExpectedParticles</span></span>|<span data-ttu-id="06791-251">GetExpectedAttributes</span><span class="sxs-lookup"><span data-stu-id="06791-251">GetExpectedAttributes</span></span>|<span data-ttu-id="06791-252">AddSchema</span><span class="sxs-lookup"><span data-stu-id="06791-252">AddSchema</span></span>|
|------------|--------------------------|---------------------------|---------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|<span data-ttu-id="06791-253">Если вызывается метод по умолчанию <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает массив всех глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="06791-253">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an array containing all global elements.</span></span><br /><br /> <span data-ttu-id="06791-254">Если перегруженный метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, принимающий в качестве параметра объект <xref:System.Xml.Schema.XmlSchemaObject>, вызывается для инициализации частичной проверки элемента, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает только элемент, для которого инициализируется объект <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-254">If the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an element, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns only the element to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="06791-255">Если вызывается метод по умолчанию <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-255">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="06791-256">Если перегруженный метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, принимающий в качестве параметра объект <xref:System.Xml.Schema.XmlSchemaObject>, вызывается для инициализации частичной проверки атрибута, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает только атрибут, для которого инициализируется объект <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="06791-256">If the overload of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns only the attribute to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="06791-257">Добавляет схему к набору <xref:System.Xml.Schema.XmlSchemaSet> объекта <xref:System.Xml.Schema.XmlSchemaValidator> при отсутствии ошибок предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="06791-257">Adds the schema to the <xref:System.Xml.Schema.XmlSchemaSet> of the <xref:System.Xml.Schema.XmlSchemaValidator> object if it has no preprocessing errors.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="06791-258">Если контекстный элемент допустим, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемых в качестве потомков контекстного элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-258">If the context element is valid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as children of the context element.</span></span><br /><br /> <span data-ttu-id="06791-259">Если контекстный элемент недопустим, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-259">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span>|<span data-ttu-id="06791-260">Если контекстный элемент допустим, и не вызывался метод <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список всех атрибутов, определенных в контекстном элементе.</span><span class="sxs-lookup"><span data-stu-id="06791-260">If the context element is valid, and if no call to <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> has been previously made, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of all the attributes defined on the context element.</span></span><br /><br /> <span data-ttu-id="06791-261">Если некоторые атрибуты уже проверены, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список оставшихся непроверенных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="06791-261">If some attributes have already been validated, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the remaining attributes to be validated.</span></span><br /><br /> <span data-ttu-id="06791-262">Если контекстный элемент недопустим, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-262">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="06791-263">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-263">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="06791-264">Если контекстный атрибут является атрибутом верхнего уровня, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-264">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="06791-265">В противном случае метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемую в качестве первого дочернего элемента контекстного элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-265">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="06791-266">Если контекстный атрибут является атрибутом верхнего уровня, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-266">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="06791-267">В противном случае метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список оставшихся непроверенных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="06791-267">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the list of remaining attributes to be validated.</span></span>|<span data-ttu-id="06791-268">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-268">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<span data-ttu-id="06791-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемую в качестве первого дочернего элемента контекстного элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="06791-270">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список необходимых и необязательных атрибутов, оставшихся для проверки в контекстном элементе.</span><span class="sxs-lookup"><span data-stu-id="06791-270"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the required and optional attributes that are yet to be validated for the context element.</span></span>|<span data-ttu-id="06791-271">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-271">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="06791-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемую в качестве первого дочернего элемента контекстного элемента.</span><span class="sxs-lookup"><span data-stu-id="06791-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="06791-273">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-273"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="06791-274">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-274">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="06791-275">Если содержимое контекстного элемента имеет тип Mixed, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемых в следующей позиции.</span><span class="sxs-lookup"><span data-stu-id="06791-275">If the context element's contentType is Mixed, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position.</span></span><br /><br /> <span data-ttu-id="06791-276">Если содержимое контекстного элемента имеет тип TextOnly или Empty, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-276">If the context element's contentType is TextOnly or Empty, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="06791-277">Если содержимое контекстного элемента имеет тип ElementOnly, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемых в следующей позиции, однако ошибка проверки уже произошла.</span><span class="sxs-lookup"><span data-stu-id="06791-277">If the context element's contentType is ElementOnly, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position but a validation error has already occurred.</span></span>|<span data-ttu-id="06791-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список атрибутов контекстного элемента, не подвергнутых проверке.</span><span class="sxs-lookup"><span data-stu-id="06791-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span>|<span data-ttu-id="06791-279">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-279">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="06791-280">Если контекстный пробел является пробелом верхнего уровня, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-280">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="06791-281">В противном случае поведение метода <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> аналогично <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-281">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="06791-282">Если контекстный пробел является пробелом верхнего уровня, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-282">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="06791-283">В противном случае поведение метода <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> аналогично <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-283">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="06791-284">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-284">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="06791-285">Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемых после контекстного элемента (возможных одноуровневых элементов).</span><span class="sxs-lookup"><span data-stu-id="06791-285"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected after the context element (possible siblings).</span></span>|<span data-ttu-id="06791-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список атрибутов контекстного элемента, не подвергнутых проверке.</span><span class="sxs-lookup"><span data-stu-id="06791-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span><br /><br /> <span data-ttu-id="06791-287">Если у контекстного элемента отсутствует родительский элемент, то метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой список (контекстный элемент является родительским для текущего элемента, в котором вызывается метод <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>).</span><span class="sxs-lookup"><span data-stu-id="06791-287">If the context element has no parent then <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty list (the context element is the parent of the current element on which <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> was called).</span></span>|<span data-ttu-id="06791-288">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-288">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="06791-289">Аналогично <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-289">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="06791-290">Аналогично <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="06791-290">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="06791-291">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-291">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="06791-292">Возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-292">Returns an empty array.</span></span>|<span data-ttu-id="06791-293">Возвращает пустой массив.</span><span class="sxs-lookup"><span data-stu-id="06791-293">Returns an empty array.</span></span>|<span data-ttu-id="06791-294">То же, что и выше.</span><span class="sxs-lookup"><span data-stu-id="06791-294">Same as above.</span></span>|

> [!NOTE]
> <span data-ttu-id="06791-295">Значения, возвращаемые различными свойствами класса <xref:System.Xml.Schema.XmlSchemaValidator>, не изменяются при вызовах методов, описанных в приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="06791-295">The values returned by the various properties of the <xref:System.Xml.Schema.XmlSchemaValidator> class are not altered by calling any of the methods in the above table.</span></span>

## <a name="see-also"></a><span data-ttu-id="06791-296">См. также:</span><span class="sxs-lookup"><span data-stu-id="06791-296">See also</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator>
