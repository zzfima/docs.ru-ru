---
title: Доступ к XML-данным со строгой типизацией с помощью XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 898e0f52-8a7c-4d1f-afcd-6ffb28b050b4
ms.openlocfilehash: ec08b668bf54c5460e078bbb27bfbc370aff4e4a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711185"
---
# <a name="accessing-strongly-typed-xml-data-using-xpathnavigator"></a>Доступ к XML-данным со строгой типизацией с помощью XPathNavigator
Класс <xref:System.Xml.XPath.XPathNavigator> как экземпляр модели данных XPath 2.0, может содержать данные со строгой типизацией, которые сопоставляются с типами CLR. Согласно модели данных XPath 2.0, только элементы и атрибуты могут содержать данные со строгой типизацией. Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет механизмы для доступа к данным со строгой типизацией в объектах <xref:System.Xml.XPath.XPathDocument> и <xref:System.Xml.XmlDocument>, а также механизмы для преобразования данных из одного типа в другой.  
  
## <a name="type-information-exposed-by-xpathnavigator"></a>Информация о типах, предоставляемая XPathNavigator  
 Данные XML 1.0 практически не имеют типа, если они не обработаны с помощью определения DTD, схемы XSD или другим средством. Существует несколько категорий сведений о типах, которые можно связать с XML-элементом или атрибутом.  
  
- Простые типы CLR. Ни один из языков схемы XML не поддерживает типы CLR напрямую. Поскольку удобно иметь возможность просматривать простое содержимое элементов и атрибутов в виде соответствующих типов CLR, все простое содержимое можно типизировать как <xref:System.String> в отсутствие данных схемы и любой добавленной информации о схеме, способной уточнить наиболее соответствующий тип этого содержимого. Наиболее совпадающий тип CLR для простого содержимого элемента или атрибута можно найти с помощью свойства <xref:System.Xml.XPath.XPathNavigator.ValueType%2A>. Дополнительные сведения о сопоставлении встроенных типов схемы с типами CLR см. в руководстве по [поддержке типов в классах System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).  
  
- Списки простых типов (CLR). Элемент или атрибут с простым содержимым может включать список значений, разделенных пробелом. Тип значений определяется схемой XML как тип списка. В отсутствие схемы XML содержимое такого простого типа считается одиночным текстовым узлом. При наличии схемы XML это простое содержимое может быть представлено как ряд атомарных значений, каждое из которых имеет простой тип, сопоставляемый с коллекцией объектов CLR. Дополнительные сведения о сопоставлении встроенных типов схемы с типами CLR см. в руководстве по [поддержке типов в классах System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).  
  
- Типизированное значение. Проверенный на соответствие схеме атрибут или элемент с простым типом, имеющий типизированное значение. Это значение является типом-примитивом, например типом numeric, string или date. Все встроенные простые типы в XSD могут сопоставляться с типами CLR, предоставляющими доступ к значению узла как наиболее соответствующему типу, а не просто типу <xref:System.String>. Элемент с атрибутами или дочерними элементами рассматривается как сложный тип. Типизированное значение сложного типа с простым содержимым (только текстовые узлы в качестве дочерних элементов) - то же самое, что и значение простого типа. Типизированное значение сложного типа со сложным содержимым (один или несколько дочерних элементов) является строковым значением объединения всех его текстовых узлов, возвращенных как тип <xref:System.String>. Дополнительные сведения о сопоставлении встроенных типов схемы с типами CLR см. в руководстве по [поддержке типов в классах System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).  
  
- Имя типа, зависящее от языка схемы. В большинстве случаев типы CLR, которые устанавливаются как результат применения внешней схемы, используются для предоставления доступа к значению узла. Однако в некоторых ситуациях нужно изучить тип, связанный с конкретной схемой, примененной к XML-документу. Например, требуется выполнить поиск в XML-документе и получить все элементы, имеющие тип содержимого «PurchaseOrder», согласно присоединенной схеме. Такие сведения о типе можно получить только в результате проверки схемы, а доступ к ним осуществляется с помощью свойств <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> и <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> класса <xref:System.Xml.XPath.XPathNavigator>. Дополнительные сведения см. в разделе «Набор сведений для постсхемной проверки (PSVI)» ниже.  
  
- Отражение типа, зависящее от языка схемы. В других случаях, возможно, потребуется получить дополнительные сведения о типе, зависящем от схемы, примененной к XML-документу. Например, при чтении XML-файла нужно получить атрибут `maxOccurs` для каждого допустимого узла в XML-документе, чтобы выполнить собственные вычисления. Поскольку эти сведения устанавливаются только через проверку схемы, доступ к ним осуществляется с помощью свойства <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> класса <xref:System.Xml.XPath.XPathNavigator>. Дополнительные сведения см. в разделе «Набор сведений для постсхемной проверки (PSVI)» ниже.  
  
## <a name="xpathnavigator-typed-accessors"></a>Типизированные методы доступа XPathNavigator  
 В следующей таблице показаны свойства и методы класса <xref:System.Xml.XPath.XPathNavigator>, которые используются для доступа к данным о типе узла.  
  
|Идентификаторы|Описание|  
|--------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.XmlType%2A>|Содержит информацию о типе схемы XML для узла, если он допустим.|  
|<xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>|Содержит информационный набор после проверки по схеме узла, который добавляется после проверки. Он включает сведения о типе схемы XML, а также сведения о достоверности.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueType%2A>|Тип CLR типизированного значения узла.|  
|<xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>|Содержимое узла в виде одного или нескольких значений CLR, тип которых больше всего соответствует типу схемы XML узла.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsBoolean%2A>|Значение <xref:System.String> текущего узла приводится к значению <xref:System.Boolean> в соответствии с правилами приведения типов XPath 2.0 для `xs:boolean`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDateTime%2A>|Значение <xref:System.String> текущего узла приводится к значению <xref:System.DateTime> в соответствии с правилами приведения типов XPath 2.0 для `xs:datetime`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>|Значение <xref:System.String> текущего узла приводится к значению <xref:System.Double> в соответствии с правилами приведения типов XPath 2.0 для `xsd:double`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>|Значение <xref:System.String> текущего узла приводится к значению <xref:System.Int32> в соответствии с правилами приведения типов XPath 2.0 для `xs:integer`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>|Значение <xref:System.String> текущего узла приводится к значению <xref:System.Int64> в соответствии с правилами приведения типов XPath 2.0 для `xs:integer`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAs%2A>|Содержимое узла, приведенное к целевому типу согласно правилам приведения типов XPath 2.0.|  
  
 Дополнительные сведения о сопоставлении встроенных типов схемы с типами CLR см. в руководстве по [поддержке типов в классах System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).  
  
## <a name="the-post-schema-validation-infoset-psvi"></a>Информационный набор после проверки по схеме  
 Процессор схемы XML принимает в качестве входных данных информационный набор XML и преобразует его в информационный набор после проверки по схеме. Информационный набор после проверки по схеме является исходным информационным набором XML с новыми информационными элементами и новыми свойствами, добавленными к существующим информационным элементам. Существует три широких класса данных, которые добавляются в информационный набор XML в информационном наборе после проверки по схеме, предоставляемом классом <xref:System.Xml.XPath.XPathNavigator>.  
  
1. Результаты проверки. Сведения об успешной или неуспешной проверке элемента или атрибута. Это представляется свойством <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> свойства <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> класса <xref:System.Xml.XPath.XPathNavigator>.  
  
2. Сведения по умолчанию. Данные о том, было ли получено значение элемента или атрибута из заданных в схеме значений по умолчанию или из других источников. Это представляется свойством <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> свойства <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> класса <xref:System.Xml.XPath.XPathNavigator>.  
  
3. Заметки о типе. Ссылки на компоненты схемы, которые могут быть определениями типов или объявлениями элементов и атрибутов. Свойство <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> объекта <xref:System.Xml.XPath.XPathNavigator> содержит конкретные сведения о типе узла, если он допустим. Если достоверность узла неизвестна, например если он после проверки подвергся изменению, то свойство <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> имеет значение `null`, но информация о типе остается доступной через различные свойства <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> класса <xref:System.Xml.XPath.XPathNavigator>.  
  
 В следующем примере демонстрируются сведения информационного набора после проверки по схеме, предоставленной объектом <xref:System.Xml.XPath.XPathNavigator>.  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("books.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("published", "http://www.contoso.com/books")  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name)  
Console.WriteLine(navigator.SchemaInfo.Validity)  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("books.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("published", "http://www.contoso.com/books");  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name);  
Console.WriteLine(navigator.SchemaInfo.Validity);  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs);  
```  
  
 В примере в качестве входных данных используется файл `books.xml`.  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 В примере в качестве входных данных также используется схема `books.xsd`.  
  
```xml  
<xs:schema xmlns="http://www.contoso.com/books"   
attributeFormDefault="unqualified" elementFormDefault="qualified"   
targetNamespace="http://www.contoso.com/books"   
xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="publishedType">  
        <xs:restriction base="xs:date">  
            <xs:minInclusive value="2003-01-01" />  
            <xs:maxInclusive value="2003-12-31" />  
        </xs:restriction>  
    </xs:simpleType>  
    <xs:complexType name="bookType">  
        <xs:sequence>  
            <xs:element name="title" type="xs:string"/>  
            <xs:element name="price" type="xs:decimal"/>  
            <xs:element name="published" type="publishedType"/>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="booksType">  
        <xs:sequence>  
            <xs:element name="book" type="bookType" />  
        </xs:sequence>  
    </xs:complexType>  
    <xs:element name="books" type="booksType" />  
</xs:schema>  
```  
  
## <a name="obtain-typed-values-using-valueas-properties"></a>Получение типизированных значений с помощью свойств ValueAs  
 Типизированное значение узла можно получить с помощью свойства <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> класса <xref:System.Xml.XPath.XPathNavigator>. В определенных случаях можно преобразовать типизированное значение узла в другое значение. Распространенным примером является получение численного значения из XML-узла. Например, рассмотрим следующий непроверенный и нетипизированный XML-документ.  
  
```xml  
<books>  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 Если объект <xref:System.Xml.XPath.XPathNavigator> расположен на элементе `price`, свойство <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> будет иметь значение `null`, свойство <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> - значение <xref:System.String>, а свойство <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> примет строковое значение `10.00`.  
  
 Однако все же можно получить цифровое значение с помощью методов и свойств <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A> и <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>. В следующем примере показано такое приведение к типу с помощью метода <xref:System.Xml.XPath.XPathItem.ValueAs%2A>.  
  
```vb  
Dim document As New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "")  
navigator.MoveToChild("book", "")  
navigator.MoveToChild("price", "")  
  
Dim price = navigator.ValueAs(GetType(Decimal))  
Dim discount As Decimal = 0.2  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * discount))  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "");  
navigator.MoveToChild("book", "");  
navigator.MoveToChild("price", "");  
  
Decimal price = (decimal)navigator.ValueAs(typeof(decimal));  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * (decimal)0.20));  
```  
  
 Дополнительные сведения о сопоставлении встроенных типов схемы с типами CLR см. в руководстве по [поддержке типов в классах System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Поддержка типов в классах System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Навигация в наборе узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)
- [Навигация по узлам атрибутов и пространств имен с помощью XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [Извлечение XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)
