---
title: Управление сериализацией XML с использованием атрибутов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, serializing
- XML serialization, examples
- derived classes, serializing
- arrays, serializing
- XML serialization, attributes
- preventing serialization
- attributes [.NET Framework], XML serialization
- serialization, examples
- serialization, attributes
ms.assetid: 47d4c39d-30e1-4c7b-8a2e-301325390647
ms.openlocfilehash: d4e30984a232b17d1f40e300655c519ec1a6e191
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159914"
---
# <a name="controlling-xml-serialization-using-attributes"></a><span data-ttu-id="b3469-102">Управление сериализацией XML с использованием атрибутов</span><span class="sxs-lookup"><span data-stu-id="b3469-102">Controlling XML Serialization Using Attributes</span></span>

<span data-ttu-id="b3469-103">Атрибуты можно использовать для управления сериализацией XML объекта или для создания альтернативного потока XML из того же набора классов.</span><span class="sxs-lookup"><span data-stu-id="b3469-103">Attributes can be used to control the XML serialization of an object or to create an alternate XML stream from the same set of classes.</span></span> <span data-ttu-id="b3469-104">Дополнительные сведения о создании альтернативного потока XML см. в разделе [Практическое руководство. Указание имени альтернативного элемента для потока XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="b3469-104">For more details about creating an alternate XML stream, see [How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b3469-105">Если создаваемый XML-код должен соответствовать разделу 5 документа консорциум W3C (W3C), озаглавленного " [простой протокол доступа к объектам (SOAP) 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)", используйте атрибуты, перечисленные в разделе [атрибуты, управляющие СЕРИАЛИЗАЦИЕЙ кодированной SOAP](attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="b3469-105">If the XML generated must conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), use the attributes listed in [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>

<span data-ttu-id="b3469-106">По умолчанию имя элемента XML определяется классом или именем члена.</span><span class="sxs-lookup"><span data-stu-id="b3469-106">By default, an XML element name is determined by the class or member name.</span></span> <span data-ttu-id="b3469-107">Как показано в следующем примере, в простом классе с именем `Book` полю с именем `ISBN` будет присвоен тег элемента XML \<ISBN>.</span><span class="sxs-lookup"><span data-stu-id="b3469-107">In a simple class named `Book`, a field named `ISBN` will produce an XML element tag \<ISBN>, as shown in the following example.</span></span>

```vb
Public Class Book
    Public ISBN As String
End Class
' When an instance of the Book class is serialized, it might
' produce this XML:
' <ISBN>1234567890</ISBN>.
```

```csharp
public class Book
{
    public string ISBN;
}
// When an instance of the Book class is serialized, it might
// produce this XML:
// <ISBN>1234567890</ISBN>.
```

<span data-ttu-id="b3469-108">Поведение по умолчанию можно изменить, если элементу следует присвоить новое имя.</span><span class="sxs-lookup"><span data-stu-id="b3469-108">This default behavior can be changed if you want to give the element a new name.</span></span> <span data-ttu-id="b3469-109">В следующем примере кода показано, как это можно сделать с помощью атрибута, задав свойство <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A><xref:System.Xml.Serialization.XmlElementAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b3469-109">The following code shows how an attribute enables this by setting the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> property of a <xref:System.Xml.Serialization.XmlElementAttribute>.</span></span>

```vb
Public Class TaxRates
   < XmlElement(ElementName = "TaxRate")> _
    Public ReturnTaxRate As Decimal
End Class
```

```csharp
public class TaxRates {
    [XmlElement(ElementName = "TaxRate")]
    public decimal ReturnTaxRate;
}
```

<span data-ttu-id="b3469-110">Дополнительные сведения об атрибутах см. в разделе [Атрибуты](../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="b3469-110">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span> <span data-ttu-id="b3469-111">Список атрибутов, которые управляют сериализацией XML, см. в разделе [Атрибуты управления сериализацией XML](attributes-that-control-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="b3469-111">For a list of attributes that control XML serialization, see [Attributes That Control XML Serialization](attributes-that-control-xml-serialization.md).</span></span>

## <a name="controlling-array-serialization"></a><span data-ttu-id="b3469-112">Управление сериализацией массивов</span><span class="sxs-lookup"><span data-stu-id="b3469-112">Controlling Array Serialization</span></span>

<span data-ttu-id="b3469-113">Атрибуты <xref:System.Xml.Serialization.XmlArrayAttribute> и <xref:System.Xml.Serialization.XmlArrayItemAttribute> предназначены для управления сериализацией массивов.</span><span class="sxs-lookup"><span data-stu-id="b3469-113">The <xref:System.Xml.Serialization.XmlArrayAttribute> and the <xref:System.Xml.Serialization.XmlArrayItemAttribute> attributes are designed to control the serialization of arrays.</span></span> <span data-ttu-id="b3469-114">С помощью этих атрибутов можно управлять именем элемента, пространством имен и типом данных схемы XML (XSD) (согласно документу "Схема XML, часть 2: типы данных" консорциума World Wide Web (www.w3.org)).</span><span class="sxs-lookup"><span data-stu-id="b3469-114">Using these attributes, you can control the element name, namespace, and XML Schema (XSD) data type (as defined in the World Wide Web Consortium [www.w3.org] document titled "XML Schema Part 2: Datatypes").</span></span> <span data-ttu-id="b3469-115">Также можно указать типы, которые можно включить в массив.</span><span class="sxs-lookup"><span data-stu-id="b3469-115">You can also specify the types that can be included in an array.</span></span>

<span data-ttu-id="b3469-116"><xref:System.Xml.Serialization.XmlArrayAttribute> определяет свойства включающего элемента XML, который создается при сериализации массива.</span><span class="sxs-lookup"><span data-stu-id="b3469-116">The <xref:System.Xml.Serialization.XmlArrayAttribute> will determine the properties of the enclosing XML element that results when an array is serialized.</span></span> <span data-ttu-id="b3469-117">Например, по умолчанию при сериализации массива ниже будет создан элемент XML с именем `Employees`.</span><span class="sxs-lookup"><span data-stu-id="b3469-117">For example, by default, serializing the array below will result in an XML element named `Employees`.</span></span> <span data-ttu-id="b3469-118">Элемент `Employees` будет содержать серию элементов, названную в соответствии с типом массива `Employee`.</span><span class="sxs-lookup"><span data-stu-id="b3469-118">The `Employees` element will contain a series of elements named after the array type `Employee`.</span></span>

```vb
Public Class Group
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
```

```csharp
public class Group {
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
```

<span data-ttu-id="b3469-119">Сериализованный экземпляр может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b3469-119">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</Employees>
</Group>
```

<span data-ttu-id="b3469-120">Применив <xref:System.Xml.Serialization.XmlArrayAttribute>, можно изменить имя элемента XML.</span><span class="sxs-lookup"><span data-stu-id="b3469-120">By applying a <xref:System.Xml.Serialization.XmlArrayAttribute>, you can change the name of the XML element, as follows.</span></span>

```vb
Public Class Group
    <XmlArray("TeamMembers")> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlArray("TeamMembers")]
    public Employee[] Employees;
}
```

<span data-ttu-id="b3469-121">Итоговый XML-код может иметь следующий вид.</span><span class="sxs-lookup"><span data-stu-id="b3469-121">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<TeamMembers>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</TeamMembers>
</Group>
```

<span data-ttu-id="b3469-122">С другой стороны, атрибут <xref:System.Xml.Serialization.XmlArrayItemAttribute> управляет способом сериализации элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="b3469-122">The <xref:System.Xml.Serialization.XmlArrayItemAttribute>, on the other hand, controls how the items contained in the array are serialized.</span></span> <span data-ttu-id="b3469-123">Обратите внимание, что атрибут применен к полю, возвращающему массив.</span><span class="sxs-lookup"><span data-stu-id="b3469-123">Note that the attribute is applied to the field returning the array.</span></span>

```vb
Public Class Group
    <XmlArrayItem("MemberName")> _
    Public Employee() As Employees
End Class
```

```csharp
public class Group {
    [XmlArrayItem("MemberName")]
    public Employee[] Employees;
}
```

<span data-ttu-id="b3469-124">Итоговый XML-код может иметь следующий вид.</span><span class="sxs-lookup"><span data-stu-id="b3469-124">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <MemberName>Haley</MemberName>
</Employees>
</Group>
```

## <a name="serializing-derived-classes"></a><span data-ttu-id="b3469-125">Сериализация производных классов</span><span class="sxs-lookup"><span data-stu-id="b3469-125">Serializing Derived Classes</span></span>

<span data-ttu-id="b3469-126">Другим способом использования <xref:System.Xml.Serialization.XmlArrayItemAttribute> является разрешение сериализации производных классов.</span><span class="sxs-lookup"><span data-stu-id="b3469-126">Another use of the <xref:System.Xml.Serialization.XmlArrayItemAttribute> is to allow the serialization of derived classes.</span></span> <span data-ttu-id="b3469-127">Например, другой класс с именем `Manager`, унаследованный от `Employee`, можно добавить в предыдущий пример.</span><span class="sxs-lookup"><span data-stu-id="b3469-127">For example, another class named `Manager` that derives from `Employee` can be added to the previous example.</span></span> <span data-ttu-id="b3469-128">Если не применять <xref:System.Xml.Serialization.XmlArrayItemAttribute>, при выполнении кода возникнет сбой, поскольку тип производного класса не будет распознан.</span><span class="sxs-lookup"><span data-stu-id="b3469-128">If you do not apply the <xref:System.Xml.Serialization.XmlArrayItemAttribute>, the code will fail at run time because the derived class type will not be recognized.</span></span> <span data-ttu-id="b3469-129">Чтобы это исправить, примените атрибут дважды, при каждой настройке свойства <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> для каждого допустимого типа (базового и производного).</span><span class="sxs-lookup"><span data-stu-id="b3469-129">To remedy this, apply the attribute twice, each time setting the <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> property for each acceptable type (base and derived).</span></span>

```vb
Public Class Group
    <XmlArrayItem(Type:=GetType(Employee)), _
    XmlArrayItem(Type:=GetType(Manager))> _
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
Public Class Manager
Inherits Employee
    Public Level As Integer
End Class
```

```csharp
public class Group {
    [XmlArrayItem(Type = typeof(Employee)),
    XmlArrayItem(Type = typeof(Manager))]
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
public class Manager:Employee {
    public int Level;
}
```

<span data-ttu-id="b3469-130">Сериализованный экземпляр может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b3469-130">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
    <Employee xsi:type = "Manager">
        <Name>Ann</Name>
        <Level>3</Level>
    </Employee>
</Employees>
</Group>
```

## <a name="serializing-an-array-as-a-sequence-of-elements"></a><span data-ttu-id="b3469-131">Сериализация массива как последовательности элементов</span><span class="sxs-lookup"><span data-stu-id="b3469-131">Serializing an Array as a Sequence of Elements</span></span>

<span data-ttu-id="b3469-132">Также предусмотрена возможность сериализации массива как плоской последовательности элементов XML путем применения <xref:System.Xml.Serialization.XmlElementAttribute> к полю, возвращающему массив следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b3469-132">You can also serialize an array as a flat sequence of XML elements by applying a <xref:System.Xml.Serialization.XmlElementAttribute> to the field returning the array as follows.</span></span>

```vb
Public Class Group
    <XmlElement> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlElement]
    public Employee[] Employees;
}
```

<span data-ttu-id="b3469-133">Сериализованный экземпляр может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b3469-133">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Name>Haley</Name>
</Employees>
<Employees>
    <Name>Noriko</Name>
</Employees>
<Employees>
    <Name>Marco</Name>
</Employees>
</Group>
```

<span data-ttu-id="b3469-134">Другим способом различения двух потоков XML является использование инструмента определения схемы XML, с помощью которого создаются файлы документов схемы XML (XSD) из скомпилированного кода.</span><span class="sxs-lookup"><span data-stu-id="b3469-134">Another way to differentiate the two XML streams is to use the XML Schema Definition tool to generate the XML Schema (XSD) document files from the compiled code.</span></span> <span data-ttu-id="b3469-135">(Дополнительные сведения об использовании этого средства см. [в разделе средство определения схемы XML и XML-сериализация](the-xml-schema-definition-tool-and-xml-serialization.md).) Если к полю не применен атрибут, схема описывает элемент следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b3469-135">(For more details on using the tool, see [The XML Schema Definition Tool and XML Serialization](the-xml-schema-definition-tool-and-xml-serialization.md).) When no attribute is applied to the field, the schema describes the element in the following manner.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />
```

<span data-ttu-id="b3469-136">Если к полю применяется <xref:System.Xml.Serialization.XmlElementAttribute>, итоговая схема описывает элемент следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b3469-136">When the <xref:System.Xml.Serialization.XmlElementAttribute> is applied to the field, the resulting schema describes the element as follows.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />
```

## <a name="serializing-an-arraylist"></a><span data-ttu-id="b3469-137">Сериализация ArrayList</span><span class="sxs-lookup"><span data-stu-id="b3469-137">Serializing an ArrayList</span></span>

<span data-ttu-id="b3469-138">Класс <xref:System.Collections.ArrayList> может содержать коллекцию различных объектов.</span><span class="sxs-lookup"><span data-stu-id="b3469-138">The <xref:System.Collections.ArrayList> class can contain a collection of diverse objects.</span></span> <span data-ttu-id="b3469-139">Поэтому <xref:System.Collections.ArrayList> можно использовать в том же объеме, что и массив.</span><span class="sxs-lookup"><span data-stu-id="b3469-139">You can therefore use a <xref:System.Collections.ArrayList> much as you use an array.</span></span> <span data-ttu-id="b3469-140">Однако вместо создания поля, возвращающего массив типизированных объектов, можно создать поле, которое возвращает один <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="b3469-140">Instead of creating a field that returns an array of typed objects, however, you can create a field that returns a single <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="b3469-141">Но как и для массивов, <xref:System.Xml.Serialization.XmlSerializer> следует указать типы объектов, которые содержит <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="b3469-141">However, as with arrays, you must inform the <xref:System.Xml.Serialization.XmlSerializer> of the types of objects the <xref:System.Collections.ArrayList> contains.</span></span> <span data-ttu-id="b3469-142">Для этого необходимо назначить для поля несколько экземпляров <xref:System.Xml.Serialization.XmlElementAttribute>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b3469-142">To accomplish this, assign multiple instances of the <xref:System.Xml.Serialization.XmlElementAttribute> to the field, as shown in the following example.</span></span>

```vb
Public Class Group
    <XmlElement(Type:=GetType(Employee)), _
    XmlElement(Type:=GetType(Manager))> _
    Public Info As ArrayList
End Class
```

```csharp
public class Group {
    [XmlElement(Type = typeof(Employee)),
    XmlElement(Type = typeof(Manager))]
    public ArrayList Info;
}
```

## <a name="controlling-serialization-of-classes-using-xmlrootattribute-and-xmltypeattribute"></a><span data-ttu-id="b3469-143">Управление сериализацией классов с использованием атрибутов XmlRootAttribute и XmlTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="b3469-143">Controlling Serialization of Classes Using XmlRootAttribute and XmlTypeAttribute</span></span>

<span data-ttu-id="b3469-144">К классу (и только к одному классу) можно применить два атрибута: <xref:System.Xml.Serialization.XmlRootAttribute> и <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b3469-144">There are two attributes that can be applied to a class (and only a class): <xref:System.Xml.Serialization.XmlRootAttribute> and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span> <span data-ttu-id="b3469-145">Эти атрибуты в значительной степени схожи.</span><span class="sxs-lookup"><span data-stu-id="b3469-145">These attributes are very similar.</span></span> <span data-ttu-id="b3469-146">Атрибут <xref:System.Xml.Serialization.XmlRootAttribute> можно применить только к одному классу, классу, который при сериализации представляет открывающий и закрывающий элемент документа XML, другими словами, корневой элемент.</span><span class="sxs-lookup"><span data-stu-id="b3469-146">The <xref:System.Xml.Serialization.XmlRootAttribute> can be applied to only one class: the class that, when serialized, represents the XML document's opening and closing element—in other words, the root element.</span></span> <span data-ttu-id="b3469-147">С другой стороны, атрибут <xref:System.Xml.Serialization.XmlTypeAttribute> можно применить к любому классу, включая корневой.</span><span class="sxs-lookup"><span data-stu-id="b3469-147">The <xref:System.Xml.Serialization.XmlTypeAttribute>, on the other hand, can be applied to any class, including the root class.</span></span>

<span data-ttu-id="b3469-148">В предыдущих примерах класс `Group` является корневым, и все его открытые поля и свойства становятся элементами XML, находящимися в документе XML.</span><span class="sxs-lookup"><span data-stu-id="b3469-148">For example, in the previous examples, the `Group` class is the root class, and all its public fields and properties become the XML elements found in the XML document.</span></span> <span data-ttu-id="b3469-149">Поэтому может существовать только один корневой класс.</span><span class="sxs-lookup"><span data-stu-id="b3469-149">Therefore, there can be only one root class.</span></span> <span data-ttu-id="b3469-150">Применяя <xref:System.Xml.Serialization.XmlRootAttribute>, можно управлять потоком XML, созданным с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b3469-150">By applying the <xref:System.Xml.Serialization.XmlRootAttribute>, you can control the XML stream generated by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="b3469-151">Например, можно изменить имя элемента и пространство имен.</span><span class="sxs-lookup"><span data-stu-id="b3469-151">For example, you can change the element name and namespace.</span></span>

<span data-ttu-id="b3469-152">Атрибут <xref:System.Xml.Serialization.XmlTypeAttribute> обеспечивает управление схемой созданного XML.</span><span class="sxs-lookup"><span data-stu-id="b3469-152">The <xref:System.Xml.Serialization.XmlTypeAttribute> allows you to control the schema of the generated XML.</span></span> <span data-ttu-id="b3469-153">Такая возможность полезна, когда необходимо опубликовать схему через XML-веб-службу.</span><span class="sxs-lookup"><span data-stu-id="b3469-153">This capability is useful when you need to publish the schema through an XML Web service.</span></span> <span data-ttu-id="b3469-154">В следующем примере применяются <xref:System.Xml.Serialization.XmlTypeAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute> к одному и тому же классу.</span><span class="sxs-lookup"><span data-stu-id="b3469-154">The following example applies both the <xref:System.Xml.Serialization.XmlTypeAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the same class.</span></span>

```vb
<XmlRoot("NewGroupName"), _
XmlType("NewTypeName")> _
Public Class Group
    Public Employees() As Employee
End Class
```

```csharp
[XmlRoot("NewGroupName")]
[XmlType("NewTypeName")]
public class Group {
    public Employee[] Employees;
}
```

<span data-ttu-id="b3469-155">При компилировании этого класса и использовании инструмента определения схемы XML для создания этой схемы следующий XML будет описывать `Group`.</span><span class="sxs-lookup"><span data-stu-id="b3469-155">If this class is compiled, and the XML Schema Definition tool is used to generate its schema, you would find the following XML describing `Group`.</span></span>

```xml
<xs:element name="NewGroupName" type="NewTypeName">
```

<span data-ttu-id="b3469-156">В противоположность этому, если бы выполнялась сериализация экземпляра класса, в документе XML хранилось бы только `NewGroupName`.</span><span class="sxs-lookup"><span data-stu-id="b3469-156">In contrast, if you were to serialize an instance of the class, only `NewGroupName` would be found in the XML document.</span></span>

```xml
<NewGroupName>
    . . .
</NewGroupName>
```

## <a name="preventing-serialization-with-the-xmlignoreattribute"></a><span data-ttu-id="b3469-157">Предотвращение сериализации с атрибутом XmlIgnoreAttribute</span><span class="sxs-lookup"><span data-stu-id="b3469-157">Preventing Serialization with the XmlIgnoreAttribute</span></span>

<span data-ttu-id="b3469-158">Возможны ситуации, в которых не требуется сериализация открытого свойства или поля.</span><span class="sxs-lookup"><span data-stu-id="b3469-158">There might be situations when a public property or field does not need to be serialized.</span></span> <span data-ttu-id="b3469-159">Например, поле или свойство могут использоваться для хранения метаданных.</span><span class="sxs-lookup"><span data-stu-id="b3469-159">For example, a field or property could be used to contain metadata.</span></span> <span data-ttu-id="b3469-160">В таких случаях примените к полю или свойству <xref:System.Xml.Serialization.XmlIgnoreAttribute>, и <xref:System.Xml.Serialization.XmlSerializer> его пропустит.</span><span class="sxs-lookup"><span data-stu-id="b3469-160">In such cases, apply the <xref:System.Xml.Serialization.XmlIgnoreAttribute> to the field or property and the <xref:System.Xml.Serialization.XmlSerializer> will skip over it.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3469-161">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3469-161">See also</span></span>

- [<span data-ttu-id="b3469-162">Атрибуты управления сериализацией XML</span><span class="sxs-lookup"><span data-stu-id="b3469-162">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="b3469-163">Атрибуты управления сериализацией с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="b3469-163">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="b3469-164">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="b3469-164">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="b3469-165">Примеры сериализации XML</span><span class="sxs-lookup"><span data-stu-id="b3469-165">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)
- [<span data-ttu-id="b3469-166">Практическое руководство. Указание имени альтернативного элемента для потока XML</span><span class="sxs-lookup"><span data-stu-id="b3469-166">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="b3469-167">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="b3469-167">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="b3469-168">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="b3469-168">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
