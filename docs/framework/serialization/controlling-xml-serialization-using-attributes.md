---
title: "Управление XML-сериализацией с использованием атрибутов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "массивы, сериализация"
  - "атрибуты [платформа .NET Framework], XML-сериализация"
  - "классы, сериализация"
  - "производные классы, сериализация"
  - "предотвращение сериализации"
  - "сериализация, атрибуты"
  - "сериализация, примеры"
  - "XML-сериализация, атрибуты"
  - "XML-сериализация, примеры"
ms.assetid: 47d4c39d-30e1-4c7b-8a2e-301325390647
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Управление XML-сериализацией с использованием атрибутов
Атрибуты можно использовать для управления XML\-сериализацией объекта или для создания альтернативного потока XML из того же набора классов.Дополнительные сведения о создании альтернативного потока XML см. в разделе [Как указать имя альтернативного элемента для потока XML](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md).  
  
> [!NOTE]
>  Если сгенерированные XML должны удовлетворять требованиями раздела 5 документа "Протокол SOAP 1.1" консорциума World Wide Web \(www.w3.org\), используйте атрибуты, указанные в разделе [Атрибуты управления SOAP\-сериализацией с кодировкой](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 По умолчанию имя элемента XML определяется классом или именем члена.Как показано в следующем примере, в простом классе с именем `Book` поле с именем `ISBN` создает тег XML\-элемента \<ISBN\>.  
  
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
  
 Поведение по умолчанию можно изменить, если элементу следует присвоить новое имя.В следующем примере кода показано, как это можно сделать с помощью атрибута, задав свойство <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A><xref:System.Xml.Serialization.XmlElementAttribute>.  
  
```vb  
Public Class TaxRates  
   < XmlElement(ElementName = "TaxRate")> _  
    Public ReturnTaxRate As Decimal  
End Class  
  
```  
  
```csharp  
public class TaxRates{  
    [XmlElement(ElementName = "TaxRate")]  
    public decimal ReturnTaxRate;  
}  
```  
  
 Дополнительные сведения об атрибутах см. в разделе [Атрибуты](../../../docs/standard/attributes/index.md).Список атрибутов, управляющих сериализацией XML, см. в разделе [Атрибуты управления XML\-сериализацией](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md).  
  
## Управление сериализацией массивов  
 Атрибуты <xref:System.Xml.Serialization.XmlArrayAttribute> и <xref:System.Xml.Serialization.XmlArrayItemAttribute> предназначены для управления сериализацией массивов.С помощью этих атрибутов можно управлять именем элемента, пространством имен и типом данных схемы XML \(XSD\) \(согласно документу "Схема XML, часть 2: типы данных" консорциума World Wide Web \(www.w3.org\)\).Также можно указать типы, которые можно включить в массив.  
  
 <xref:System.Xml.Serialization.XmlArrayAttribute> определяет свойства включающего элемента XML, который создается при сериализации массива.Например, по умолчанию при сериализации массива ниже будет создан элемент XML с именем `Employees`.Элемент `Employees` будет содержать серию элементов, названную в соответствии с типом массива `Employee`.  
  
```vb  
Public Class Group  
    Public Employees() As Employee  
End Class  
Public Class Employee  
    Public Name As String  
End Class  
  
```  
  
```csharp  
public class Group{  
    public Employee[] Employees;  
}  
public class Employee{  
    public string Name;  
}  
```  
  
 Сериализованный экземпляр может выглядеть следующим образом.  
  
```  
<Group>  
<Employees>  
    <Employee>  
        <Name>Haley</Name>  
    </Employee>  
</Employees >  
</Group>  
```  
  
 Применив <xref:System.Xml.Serialization.XmlArrayAttribute>, можно изменить имя элемента XML.  
  
```vb  
Public Class Group  
    <XmlArray("TeamMembers")> _  
    Public Employees() As Employee  
End Class  
  
```  
  
```csharp  
public class Group{  
    [XmlArray("TeamMembers")]  
    public Employee[] Employees;  
}  
```  
  
 Итоговый XML\-код может иметь следующий вид.  
  
```  
<Group>  
<TeamMembers>  
    <Employee>  
        <Name>Haley</Name>  
    </Employee>  
</TeamMembers>  
```  
  
 С другой стороны, атрибут <xref:System.Xml.Serialization.XmlArrayItemAttribute> управляет способом сериализации элементов в массиве.Обратите внимание, что атрибут применен к полю, возвращающему массив.  
  
```vb  
Public Class Group  
    <XmlArrayItem("MemberName")> _  
    Public Employee() As Employees  
End Class  
  
```  
  
```csharp  
public class Group{  
    [XmlArrayItem("MemberName")]  
    public Employee[] Employees;  
}  
```  
  
 Итоговый XML\-код может иметь следующий вид.  
  
```  
<Group>  
<Employees>  
    <MemberName>Haley</MemberName>  
</Employees>  
</Group>  
```  
  
## Сериализация производных классов  
 Другим способом использования <xref:System.Xml.Serialization.XmlArrayItemAttribute> является разрешение сериализации производных классов.Например, другой класс с именем `Manager`, унаследованный от `Employee`, можно добавить в предыдущий пример.Если не применять <xref:System.Xml.Serialization.XmlArrayItemAttribute>, при выполнении кода возникнет сбой, поскольку тип производного класса не будет распознан.Чтобы это исправить, примените атрибут дважды, при каждой настройке свойства <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> для каждого допустимого типа \(базового и производного\).  
  
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
public class Group{  
    [XmlArrayItem(Type = typeof(Employee)),  
    XmlArrayItem(Type = typeof(Manager))]  
    public Employee[] Employees;  
}  
public class Employee{  
    public string Name;  
}  
public class Manager:Employee{  
    public int Level;  
}  
```  
  
 Сериализованный экземпляр может выглядеть следующим образом.  
  
```  
<Group>  
<Employees>  
    <Employee>  
        <Name>Haley</Name>  
    </Employee>  
    <Employee xsi:type = "Manager">  
        <Name>Ann</Name>  
        <Level>3</Level>  
    <Employee>  
</Employees >  
</Group>  
```  
  
## Сериализация массива как последовательности элементов  
 Также предусмотрена возможность сериализации массива как плоской последовательности элементов XML путем применения <xref:System.Xml.Serialization.XmlElementAttribute> к полю, возвращающему массив следующим образом.  
  
```vb  
Public Class Group  
    <XmlElement> _  
    Public Employees() As Employee  
End Class  
  
```  
  
```csharp  
public class Group{  
    [XmlElement]  
    public Employee[] Employees;  
}  
```  
  
 Сериализованный экземпляр может выглядеть следующим образом.  
  
```  
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
  
 Другим способом различения двух потоков XML является использование инструмента определения схемы XML, с помощью которого создаются файлы документов схемы XML \(XSD\) из скомпилированного кода.\(Дополнительные сведения об использовании инструмента см. в разделе [Инструмент определения схемы XML и сериализация XML](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md).\) Если к полю не применяется никакой атрибут, схема описывает элемент следующим образом.  
  
```  
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />  
```  
  
 Если к полю применяется <xref:System.Xml.Serialization.XmlElementAttribute>, итоговая схема описывает элемент следующим образом.  
  
```  
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />   
```  
  
## Сериализация ArrayList  
 Класс <xref:System.Collections.ArrayList> может содержать коллекцию различных объектов.Поэтому <xref:System.Collections.ArrayList> можно использовать в том же объеме, что и массив.Однако вместо создания поля, возвращающего массив типизированных объектов, можно создать поле, которое возвращает один <xref:System.Collections.ArrayList>.Но как и для массивов, <xref:System.Xml.Serialization.XmlSerializer> следует указать типы объектов, которые содержит <xref:System.Collections.ArrayList>.Для этого необходимо назначить для поля несколько экземпляров <xref:System.Xml.Serialization.XmlElementAttribute>, как показано в следующем примере.  
  
```vb  
Public Class Group  
    <XmlElement(Type:=GetType(Employee)), _  
    XmlElement(Type:=GetType(Manager))> _  
    Public Info As ArrayList  
End Class  
  
```  
  
```csharp  
public class Group{  
    [XmlElement(Type = typeof(Employee)),   
    XmlElement(Type = typeof(Manager))]  
    public ArrayList Info;  
}  
```  
  
## Управление сериализацией классов с использованием атрибутов XmlRootAttribute и XmlTypeAttribute  
 К классу \(и только к одному классу\) можно применить два атрибута: <xref:System.Xml.Serialization.XmlRootAttribute> и <xref:System.Xml.Serialization.XmlTypeAttribute>.Эти атрибуты в значительной степени схожи.Атрибут <xref:System.Xml.Serialization.XmlRootAttribute> можно применить только к одному классу, классу, который при сериализации представляет открывающий и закрывающий элемент документа XML, другими словами, корневой элемент.С другой стороны, атрибут <xref:System.Xml.Serialization.XmlTypeAttribute> можно применить к любому классу, включая корневой.  
  
 В предыдущих примерах класс `Group` является корневым, и все его открытые поля и свойства становятся элементами XML, находящимися в документе XML.Поэтому может существовать только один корневой класс.Применяя <xref:System.Xml.Serialization.XmlRootAttribute>, можно управлять потоком XML, созданным с помощью <xref:System.Xml.Serialization.XmlSerializer>.Например, можно изменить имя элемента и пространство имен.  
  
 Атрибут <xref:System.Xml.Serialization.XmlTypeAttribute> обеспечивает управление схемой созданного XML.Такая возможность полезна, когда необходимо опубликовать схему через XML\-веб\-службу.В следующем примере применяются <xref:System.Xml.Serialization.XmlTypeAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute> к одному и тому же классу.  
  
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
public class Group{  
    public Employee[] Employees;  
}  
```  
  
 При компилировании этого класса и использовании инструмента определения схемы XML для создания этой схемы следующий XML будет описывать `Group`.  
  
```  
<xs:element name="NewGroupName" type="NewTypeName">  
```  
  
 В противоположность этому, если бы выполнялась сериализация экземпляра класса, в документе XML хранилось бы только `NewGroupName`.  
  
```  
<NewGroupName>  
    . . .  
</NewGroupName>  
```  
  
## Предотвращение сериализации с атрибутом XmlIgnoreAttribute  
 Возможны ситуации, в которых не требуется сериализация открытого свойства или поля.Например, поле или свойство могут использоваться для хранения метаданных.В таких случаях примените к полю или свойству <xref:System.Xml.Serialization.XmlIgnoreAttribute>, и <xref:System.Xml.Serialization.XmlSerializer> его пропустит.  
  
## См. также  
 [Атрибуты управления XML\-сериализацией](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md)   
 [Атрибуты управления SOAP\-сериализацией с кодировкой](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [Введение в XML\-сериализацию](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [Примеры XML\-сериализации](../../../docs/framework/serialization/examples-of-xml-serialization.md)   
 [Как указать имя альтернативного элемента для потока XML](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [Как сериализовать объект](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Как десериализовать объект](../../../docs/framework/serialization/how-to-deserialize-an-object.md)