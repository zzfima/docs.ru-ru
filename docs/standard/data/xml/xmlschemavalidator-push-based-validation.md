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
# <a name="xmlschemavalidator-push-based-validation"></a>Принудительная проверка с помощью XmlSchemaValidator

Класс <xref:System.Xml.Schema.XmlSchemaValidator> предоставляет эффективный, высокопроизводительный механизм для принудительной проверки XML-данных по схемам XML. Например, класс <xref:System.Xml.Schema.XmlSchemaValidator> позволяет проверять информационный набор XML локально, без сериализации в виде XML-документа, а затем повторно выполнить синтаксический анализ с помощью проверяющего модуля чтения XML.

Класс <xref:System.Xml.Schema.XmlSchemaValidator> можно использовать в расширенных сценариях, например, для создания подсистем проверки в пользовательских источниках XML-данных или проверяющего модуля записи XML.

В следующем примере класс <xref:System.Xml.Schema.XmlSchemaValidator> используется для проверки файла `contosoBooks.xml` по схеме `contosoBooks.xsd`. Класс <xref:System.Xml.Serialization.XmlSerializer> в примере используется для десериализации файла `contosoBooks.xml` и передачи значений узлов методам класса <xref:System.Xml.Schema.XmlSchemaValidator>.

> [!NOTE]
> Этот пример приводится во всех подразделах этого раздела.

[!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
[!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]

В примере в качестве входных данных используется файл `contosoBooks.xml`.

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

В примере также в качестве входных данных используется `contosoBooks.xsd`.

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

## <a name="validating-xml-data-using-xmlschemavalidator"></a>Проверка XML-данных с помощью XmlSchemaValidator

Чтобы начать проверку информационного набора XML, необходимо вначале инициализировать новый экземпляр класса <xref:System.Xml.Schema.XmlSchemaValidator> с помощью конструктора <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>.

Конструктор <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> принимает объекты <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet> и <xref:System.Xml.XmlNamespaceManager>, а также значение <xref:System.Xml.Schema.XmlSchemaValidationFlags> в качестве параметра. Объект <xref:System.Xml.XmlNameTable> используется для атомизации известных строк пространств имен (таких как пространство имен схемы, пространство имен XML и так далее) и передает их методу <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> при проверке простого содержимого. Объект <xref:System.Xml.Schema.XmlSchemaSet> содержит схемы XML, используемые при проверке информационного набора XML. Объект <xref:System.Xml.XmlNamespaceManager> применяется для разрешения пространства имен во время проверки. Значение <xref:System.Xml.Schema.XmlSchemaValidationFlags> используется для отключения определенных функций проверки.

Дополнительные сведения о конструкторе <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="initializing-validation"></a>Инициализация проверки

После создания объект <xref:System.Xml.Schema.XmlSchemaValidator> имеет два перегруженных метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, которые применяются для инициализации состояния объекта <xref:System.Xml.Schema.XmlSchemaValidator>. Ниже представлены два этих метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

Метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, применяющийся по умолчанию, инициализирует начальное состояние объекта <xref:System.Xml.Schema.XmlSchemaValidator>, а перегруженный метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, принимающий в качестве параметра <xref:System.Xml.Schema.XmlSchemaObject>, инициализирует начальное состояние объекта <xref:System.Xml.Schema.XmlSchemaValidator> для частичной проверки.

Оба метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> можно вызвать только сразу после создания объекта <xref:System.Xml.Schema.XmlSchemaValidator> или вызова <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.

Пример метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> см. в примере во введении. Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="partial-validation"></a>Частичная проверка

Метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, принимающий в качестве параметра <xref:System.Xml.Schema.XmlSchemaObject>, инициализирует начальное состояние объекта <xref:System.Xml.Schema.XmlSchemaValidator> для частичной проверки.

В следующем примере объект <xref:System.Xml.Schema.XmlSchemaObject> инициализируется для частичной проверки с помощью метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>. Элемент схемы `orderNumber` передается путем выбора <xref:System.Xml.XmlQualifiedName> в коллекции <xref:System.Xml.Schema.XmlSchemaObjectTable>, возвращаемой свойством <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> объекта <xref:System.Xml.Schema.XmlSchemaSet>. Затем объект <xref:System.Xml.Schema.XmlSchemaValidator> проверяет этот элемент.

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

Этот пример принимает в качестве входных данных следующую схему XML.

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="orderNumber" type="xs:int" />
</xs:schema>
```

Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="adding-additional-schemas"></a>Добавление дополнительных схем

Метод <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> класса <xref:System.Xml.Schema.XmlSchemaValidator> используется для добавления схемы XML в набор схем, который применяется во время проверки. Метод <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> может использоваться для моделирования результата обнаружения встроенной схемы XML в проверяемом информационном наборе XML.

> [!NOTE]
> Целевое пространство имен параметра <xref:System.Xml.Schema.XmlSchema> не может соответствовать пространству имен элемента или атрибута, уже обнаруженного объектом <xref:System.Xml.Schema.XmlSchemaValidator>.
>
> Если значение <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> не было передано в качестве параметра конструктору <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, метод <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> не предпринимает никаких действий.

Результат метода <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> зависит от текущего контекста проверяемого XML-узла. Дополнительные сведения о контексте проверки см. в подразделе «Контекст проверки» этого раздела.

Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="validating-elements-attributes-and-content"></a>Проверка элементов, атрибутов и содержимого

Класс <xref:System.Xml.Schema.XmlSchemaValidator> предоставляет несколько методов для проверки по схемам XML элементов, атрибутов и содержимого информационного набора XML. В следующей таблице описан каждый из этих методов.

|Метод|Описание|
|------------|-----------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|Проверяет имя элемента в текущем контексте.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|Проверяет атрибут в контексте текущего элемента или по объекту <xref:System.Xml.Schema.XmlSchemaAttribute>, переданному в качестве параметра методу <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|Проверяет наличие всех необходимых атрибутов в контексте элемента и подготавливает объект <xref:System.Xml.Schema.XmlSchemaValidator> для проверки содержимого дочернего элемента.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|Проверяет, разрешен ли текст в контексте текущего элемента и накапливает текст для проверки, если текущий элемент имеет простое содержимое.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|Проверяет, разрешены ли пробелы в контексте текущего элемента и накапливает пробелы для проверки, если текущий элемент имеет простое содержимое.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|Проверяет допустимость текстового содержимого элемента с простым содержимым и полноту содержимого текущего элемента для элементов со сложным содержимым.|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|Пропускает проверку содержимого текущего элемента и подготавливает объект <xref:System.Xml.Schema.XmlSchemaValidator> для проверки содержимого в контексте родительского элемента.|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|Завершает проверку и проверяет ограничения удостоверения для всего XML-документа, если указан параметр проверки <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints>.|

> [!NOTE]
> В классе <xref:System.Xml.Schema.XmlSchemaValidator> объявляется переход между состояниями, определяющий последовательность и вхождение вызовов каждого метода, описанного в приведенной выше таблице. Специальный переход между состояниями класса <xref:System.Xml.Schema.XmlSchemaValidator> описан в подразделе «Переход между состояниями XmlSchemaValidator» этого раздела.

Пример методов, которые используются для проверки элементов, атрибутов и содержимого в информационном наборе XML, см. в примерах предыдущего раздела. Дополнительные сведения об этих методах см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="validating-content-using-an-xmlvaluegetter"></a>Проверка содержимого с помощью XmlValueGetter

<xref:System.Xml.Schema.XmlValueGetter>`delegate` может использоваться для передачи значения узла атрибута, текста или пробела как типов CLR, совместимых с типами XSD для узла атрибута, текста или пробела. <xref:System.Xml.Schema.XmlValueGetter>`delegate` полезно использовать, если значение CLR узла атрибута, текста или пробела уже доступно, так как это позволяет избежать затрат на преобразование в тип `string` и последующий повторный синтаксический анализ для проверки.

Методы <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> перегружены и принимают значение узла атрибута, текста или пробела как тип `string` или <xref:System.Xml.Schema.XmlValueGetter>`delegate`.

Следующие методы класса <xref:System.Xml.Schema.XmlSchemaValidator> принимают <xref:System.Xml.Schema.XmlValueGetter>`delegate` в качестве параметра.

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>

Следующий пример <xref:System.Xml.Schema.XmlValueGetter>`delegate` взят из примера класса <xref:System.Xml.Schema.XmlSchemaValidator> во введении. <xref:System.Xml.Schema.XmlValueGetter>`delegate` возвращает значение атрибута в виде объекта <xref:System.DateTime>. Для проверки объекта <xref:System.DateTime>, возвращенного <xref:System.Xml.Schema.XmlValueGetter>, объект <xref:System.Xml.Schema.XmlSchemaValidator> вначале преобразует его в тип ValueType для типа данных атрибута (ValueType является сопоставлением CLR по умолчанию для типа XSD), а затем проверяет аспекты в преобразованном значении.

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

Полный пример <xref:System.Xml.Schema.XmlValueGetter>`delegate` см. во введении. Дополнительные сведения о <xref:System.Xml.Schema.XmlValueGetter>`delegate` см. в справочной документации по классам <xref:System.Xml.Schema.XmlValueGetter> и <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="post-schema-validation-information"></a>Post-Schema-Validation-Information

Класс <xref:System.Xml.Schema.XmlSchemaInfo> представляет некоторые сведения после проверки схемы XML-узла, проверенного классом <xref:System.Xml.Schema.XmlSchemaValidator>. Различные методы класса <xref:System.Xml.Schema.XmlSchemaValidator> принимают объект <xref:System.Xml.Schema.XmlSchemaInfo> в качестве необязательного (`null`) параметра типа `out`.

По окончании успешной проверки свойства объекта <xref:System.Xml.Schema.XmlSchemaInfo> принимают значения результатов проверки. Например, по окончании успешной проверки атрибута с помощью метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, свойства <xref:System.Xml.Schema.XmlSchemaInfo>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A> и <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> (если они заданы) объекта <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> принимают значения результатов проверки.

Следующие методы класса <xref:System.Xml.Schema.XmlSchemaValidator> принимают объект <xref:System.Xml.Schema.XmlSchemaInfo> в качестве выходного параметра.

- <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>

Полный пример класса <xref:System.Xml.Schema.XmlSchemaInfo> см. во введении. Дополнительные сведения о классе <xref:System.Xml.Schema.XmlSchemaInfo> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaInfo>.

### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a>Получение ожидаемых примитивов, атрибутов и неуказанных атрибутов по умолчанию

Класс <xref:System.Xml.Schema.XmlSchemaValidator> предоставляет методы <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> для получения ожидаемых примитивов, атрибутов и неуказанных атрибутов по умолчанию в текущем контексте проверки.

#### <a name="retrieving-expected-particles"></a>Получение ожидаемых примитивов

Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает массив объектов <xref:System.Xml.Schema.XmlSchemaParticle>, содержащих ожидаемые примитивы в текущем контекстном элементе. Допустимыми примитивами, возвращаемыми методом <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, являются экземпляры классов <xref:System.Xml.Schema.XmlSchemaElement> и <xref:System.Xml.Schema.XmlSchemaAny>.

Если компоновщиком модели содержимого является `xs:sequence`, возвращается только следующий примитив последовательности. Если компоновщиком модели содержимого является `xs:all` или `xs:choice`, возвращаются все допустимые примитивы, которые могут следовать в текущем контекстном элементе.

> [!NOTE]
> Если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> вызывается сразу после вызова <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>метода <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, он возвращает все глобальные элементы.

Например, в следующей схеме XSD и XML-документе после проверки элемента `book` текущим контекстным элементом является элемент `book`. Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает массив, который содержит один объект <xref:System.Xml.Schema.XmlSchemaElement>, представляющий элемент `title`. Если контекстом проверки является элемент `title`, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив. Если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> вызывается после проверки элемента `title`, но перед проверкой элемента `description`, он возвращает массив, который содержит один объект <xref:System.Xml.Schema.XmlSchemaElement>, представляющий элемент `description`. Если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> вызывается после проверки элемента `description`, он возвращает массив, который содержит один объект <xref:System.Xml.Schema.XmlSchemaAny>, представляющий символ-шаблон.

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

 В примере в качестве входных данных используется следующий XML-код:

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

В примере в качестве входных данных используется следующая схема XSD:

```xml
<book>
  <title>My Book</title>
  <description>My Book's Description</description>
  <namespace>System.Xml.Schema</namespace>
</book>
```

> [!NOTE]
> Результаты выполнения методов <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> класса <xref:System.Xml.Schema.XmlSchemaValidator> зависят от текущего подвергаемого проверке контекста. Дополнительные сведения см. в подразделе «Контекст проверки» в данном разделе.

Пример метода <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> см. в примере во введении. Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="retrieving-expected-attributes"></a>Получение ожидаемых атрибутов

Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает массив объектов <xref:System.Xml.Schema.XmlSchemaAttribute>, содержащих ожидаемые атрибуты в текущем контекстном элементе.

Например, в примере во введении метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> используется для получения всех атрибутов элемента `book`.

Если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> вызывается сразу после метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>, возвращаются все атрибуты, которые могут встретиться в XML-документе. Но если метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> вызывается после одного или нескольких вызовов метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, возвращаются еще не проверенные атрибуты текущего элемента.

> [!NOTE]
> Результаты выполнения методов <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> класса <xref:System.Xml.Schema.XmlSchemaValidator> зависят от текущего подвергаемого проверке контекста. Дополнительные сведения см. в подразделе «Контекст проверки» в данном разделе.

Пример метода <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> см. в примере во введении. Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="retrieving-unspecified-default-attributes"></a>Получение неуказанных атрибутов по умолчанию

Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> заполняет список <xref:System.Collections.ArrayList>, заданный объектами <xref:System.Xml.Schema.XmlSchemaAttribute> для всех атрибутов, значениями по умолчанию, которые ранее не были проверены с помощью метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> в контексте элемента. Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> следует вызывать после метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> для каждого атрибута в контексте элемента. Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> необходимо использовать для определения атрибутов по умолчанию, которые должны быть вставлены в проверяемый XML-документ.

Дополнительные сведения о методе <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="handling-schema-validation-events"></a>Обработка событий проверки схемы

Предупреждения и ошибки схемы, встретившиеся во время проверки, обрабатываются событием <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> класса <xref:System.Xml.Schema.XmlSchemaValidator>.

Предупреждения проверки схемы имеют значение <xref:System.Xml.Schema.XmlSeverityType> с типом <xref:System.Xml.Schema.XmlSeverityType.Warning>, а ошибки проверки схемы имеют значение <xref:System.Xml.Schema.XmlSeverityType> с типом <xref:System.Xml.Schema.XmlSeverityType.Error>. Если обработчик <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> не назначен, вызывается исключение <xref:System.Xml.Schema.XmlSchemaValidationException> для всех ошибок проверки схемы со значением <xref:System.Xml.Schema.XmlSeverityType> и типом <xref:System.Xml.Schema.XmlSeverityType.Error>. Однако исключение <xref:System.Xml.Schema.XmlSchemaValidationException> не вызывается для предупреждений проверки схемы со значением <xref:System.Xml.Schema.XmlSeverityType> и типом <xref:System.Xml.Schema.XmlSeverityType.Warning>.

Следующий пример обработчика <xref:System.Xml.Schema.ValidationEventHandler> из введения получает предупреждения и ошибки проверки схемы, встретившиеся во время проверки.

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

Полный пример для метода <xref:System.Xml.Schema.ValidationEventHandler> см. во введении. Дополнительные сведения см. в справочной документации по классу <xref:System.Xml.Schema.XmlSchemaInfo>.

## <a name="xmlschemavalidator-state-transition"></a>Переход между состояниями XmlSchemaValidator

В классе <xref:System.Xml.Schema.XmlSchemaValidator> объявляется переход между состояниями, определяющий последовательность и вхождение вызовов каждого метода, которые используются для проверки элементов, атрибутов и содержимого в информационном наборе XML.

В следующей таблице описан переход между состояниями класса <xref:System.Xml.Schema.XmlSchemaValidator>, а также последовательность и вхождение вызовов методов, возможных в каждом состоянии.

|Состояние|Переход|
|-----------|----------------|
|Validate|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|
|TopLevel|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element|
|Элемент|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> содержимое\*)? <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;<br /><br /> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>&#124;<br /><br /> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> содержимого\*&#124;|
|Content|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element|

> [!NOTE]
> Исключение <xref:System.InvalidOperationException> вызывается всеми методами в приведенной выше таблице, если вызов метода выполняется в неверной последовательности в зависимости от текущего состояния объекта <xref:System.Xml.Schema.XmlSchemaValidator>.

Приведенная выше таблица переходов между состояниями использует символы пунктуации для описания методов и других состояний, которые можно вызывать при переходе состояний класса <xref:System.Xml.Schema.XmlSchemaValidator>. Используемые символы те же, что и в справочнике по XML-стандартам для определения типа документа (DTD).

В следующей таблице показано, как символы пунктуации из приведенной выше таблицы перехода состояний влияют на методы и другие состояния, которые можно вызывать при переходе состояний класса <xref:System.Xml.Schema.XmlSchemaValidator>.

|Символ|Описание|
|------------|-----------------|
|&#124;|Можно вызывать или метод, или состояние (перед чертой или после нее).|
|?|Метод или состояние перед вопросительным знаком (?) являются необязательными, но их можно вызывать только один раз.|
|*|Метод или состояние перед символом «звездочки» (*) являются необязательными. Их можно вызывать несколько раз.|

## <a name="validation-context"></a>Контекст проверки

Методы класса <xref:System.Xml.Schema.XmlSchemaValidator> используются для проверки элементов, атрибутов и содержимого в информационном наборе XML, а также изменения контекста проверки объекта <xref:System.Xml.Schema.XmlSchemaValidator>. Например, метод <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> пропускает проверку содержимого текущего элемента и подготавливает объект <xref:System.Xml.Schema.XmlSchemaValidator> для проверки в контексте родительского элемента. Это равнозначно пропуску проверки всех потомков текущего элемента и вызову метода <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.

Результаты выполнения методов <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> и <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> класса <xref:System.Xml.Schema.XmlSchemaValidator> зависят от текущего подвергаемого проверке контекста.

В следующей таблице приводятся результаты выполнения этих методов после вызова одного из методов класса <xref:System.Xml.Schema.XmlSchemaValidator> для проверки элементов, атрибутов и содержимого в информационном наборе XML.

|Метод|GetExpectedParticles|GetExpectedAttributes|AddSchema|
|------------|--------------------------|---------------------------|---------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|Если вызывается метод по умолчанию <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает массив всех глобальных элементов.<br /><br /> Если перегруженный метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, принимающий в качестве параметра объект <xref:System.Xml.Schema.XmlSchemaObject>, вызывается для инициализации частичной проверки элемента, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает только элемент, для которого инициализируется объект <xref:System.Xml.Schema.XmlSchemaValidator>.|Если вызывается метод по умолчанию <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.<br /><br /> Если перегруженный метод <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, принимающий в качестве параметра объект <xref:System.Xml.Schema.XmlSchemaObject>, вызывается для инициализации частичной проверки атрибута, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает только атрибут, для которого инициализируется объект <xref:System.Xml.Schema.XmlSchemaValidator>.|Добавляет схему к набору <xref:System.Xml.Schema.XmlSchemaSet> объекта <xref:System.Xml.Schema.XmlSchemaValidator> при отсутствии ошибок предварительной обработки.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|Если контекстный элемент допустим, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемых в качестве потомков контекстного элемента.<br /><br /> Если контекстный элемент недопустим, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.|Если контекстный элемент допустим, и не вызывался метод <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список всех атрибутов, определенных в контекстном элементе.<br /><br /> Если некоторые атрибуты уже проверены, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список оставшихся непроверенных атрибутов.<br /><br /> Если контекстный элемент недопустим, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.|То же, что и выше.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|Если контекстный атрибут является атрибутом верхнего уровня, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.<br /><br /> В противном случае метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемую в качестве первого дочернего элемента контекстного элемента.|Если контекстный атрибут является атрибутом верхнего уровня, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.<br /><br /> В противном случае метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список оставшихся непроверенных атрибутов.|То же, что и выше.|
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемую в качестве первого дочернего элемента контекстного элемента.|Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список необходимых и необязательных атрибутов, оставшихся для проверки в контекстном элементе.|То же, что и выше.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемую в качестве первого дочернего элемента контекстного элемента.|Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.|То же, что и выше.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|Если содержимое контекстного элемента имеет тип Mixed, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемых в следующей позиции.<br /><br /> Если содержимое контекстного элемента имеет тип TextOnly или Empty, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.<br /><br /> Если содержимое контекстного элемента имеет тип ElementOnly, метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемых в следующей позиции, однако ошибка проверки уже произошла.|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список атрибутов контекстного элемента, не подвергнутых проверке.|То же, что и выше.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|Если контекстный пробел является пробелом верхнего уровня, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает пустой массив.<br /><br /> В противном случае поведение метода <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> аналогично <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.|Если контекстный пробел является пробелом верхнего уровня, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой массив.<br /><br /> В противном случае поведение метода <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> аналогично <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.|То же, что и выше.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|Метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> возвращает последовательность элементов, ожидаемых после контекстного элемента (возможных одноуровневых элементов).|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает список атрибутов контекстного элемента, не подвергнутых проверке.<br /><br /> Если у контекстного элемента отсутствует родительский элемент, то метод <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> возвращает пустой список (контекстный элемент является родительским для текущего элемента, в котором вызывается метод <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>).|То же, что и выше.|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|Аналогично <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|Аналогично <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|То же, что и выше.|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|Возвращает пустой массив.|Возвращает пустой массив.|То же, что и выше.|

> [!NOTE]
> Значения, возвращаемые различными свойствами класса <xref:System.Xml.Schema.XmlSchemaValidator>, не изменяются при вызовах методов, описанных в приведенной выше таблице.

## <a name="see-also"></a>См. также:

- <xref:System.Xml.Schema.XmlSchemaValidator>
