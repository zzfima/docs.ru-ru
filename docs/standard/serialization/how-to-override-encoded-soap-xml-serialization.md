---
title: "Практическое руководство. Переопределение сериализации XML с кодировкой SOAP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- overriding XML serialization
- SOAP, overriding encoded XML serialization
ms.assetid: d0791df8-04e3-46b4-a6be-fe0ed09267e8
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 0dea6233f2a13bd3b6c7e33ebf9ee1c96dae7577
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-override-encoded-soap-xml-serialization"></a>Практическое руководство. Переопределение сериализации XML с кодировкой SOAP
[Пример кода](#tskhowtooverrideencodedsoapxmlserializationanchor1)  
  
 Процесс переопределения сериализации XML объектов как сообщений SOAP аналогичен процессу переопределения стандартной сериализации XML. Сведения о том, как переопределить стандартную сериализацию XML, см. в разделе [Практическое руководство. Указание имени альтернативного элемента для потока XML](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md).  
  
### <a name="to-override-serialization-of-objects-as-soap-messages"></a>Переопределение сериализации объектов как сообщений SOAP  
  
1.  Создайте экземпляр класса <xref:System.Xml.Serialization.SoapAttributeOverrides>.  
  
2.  Создайте `SoapAttributes` для каждого сериализуемого члена класса.  
  
3.  Создайте экземпляр одного или нескольких атрибутов, влияющих на XML-сериализацию соответствующим образом, для сериализуемого члена. Дополнительные сведения см. в разделе "Атрибуты управления сериализацией с кодировкой SOAP".  
  
4.  Задайте соответствующее свойство `SoapAttributes` для атрибута, созданного на шаге 3.  
  
5.  Добавьте `SoapAttributes` в `SoapAttributeOverrides`.  
  
6.  Создайте `XmlTypeMapping` с использованием `SoapAttributeOverrides`. Воспользуйтесь методом `SoapReflectionImporter.ImportTypeMapping`.  
  
7.  Создайте `XmlSerializer` с использованием `XmlTypeMapping`.  
  
8.  Сериализуйте или десериализуйте объект.  
  
## <a name="example"></a>Пример  
 В следующем примере кода файл сериализуется двумя способами: сначала без переопределения поведения класса `XmlSerializer`, а затем с переопределением поведения. В примере содержится класс с именем `Group` с несколькими членами. К членам классов применены различные атрибуты, например `SoapElementAttribute`. Когда класс сериализуется методом `SerializeOriginal`, атрибуты управляют содержимым сообщения SOAP. При вызове метода `SerializeOverride` поведение `XmlSerializer` переопределяется путем создания различных атрибутов и настройкой свойств `SoapAttributes` для таких атрибутов соответствующим образом.  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Serialization;  
using System.Xml.Schema;  
  
public class Group  
{  
    [SoapAttribute (Namespace = "http://www.cpandl.com")]  
    public string GroupName;  
  
    [SoapAttribute(DataType = "base64Binary")]  
    public Byte [] GroupNumber;  
  
    [SoapAttribute(DataType = "date", AttributeName = "CreationDate")]  
    public DateTime Today;  
    [SoapElement(DataType = "nonNegativeInteger", ElementName = "PosInt")]  
    public string PostitiveInt;  
    // This is ignored when serialized unless it is overridden.  
    [SoapIgnore]   
    public bool IgnoreThis;  
  
    public GroupType Grouptype;  
  
    [SoapInclude(typeof(Car))]  
    public Vehicle myCar(string licNumber)  
    {  
        Vehicle v;  
        if(licNumber == "")  
            {  
                v = new Car();  
            v.licenseNumber = "!!!!!!";  
        }  
        else  
        {  
            v = new Car();  
            v.licenseNumber = licNumber;  
        }  
        return v;  
    }  
}  
  
public abstract class Vehicle  
{  
    public string licenseNumber;  
    public DateTime makeDate;  
}  
  
public class Car: Vehicle  
{  
}  
  
public enum GroupType  
{  
    // These enums can be overridden.  
    small,  
    large  
}  
  
public class Run  
{  
    public static void Main()  
    {  
        Run test = new Run();  
        test.SerializeOriginal("SoapOriginal.xml");  
        test.SerializeOverride("SoapOverrides.xml");  
        test.DeserializeOriginal("SoapOriginal.xml");  
        test.DeserializeOverride("SoapOverrides.xml");  
  
    }  
    public void SerializeOriginal(string filename)  
    {  
        // Creates an instance of the XmlSerializer class.  
        XmlTypeMapping myMapping =   
        (new SoapReflectionImporter().ImportTypeMapping(  
        typeof(Group)));  
        XmlSerializer mySerializer =    
        new XmlSerializer(myMapping);  
  
        // Writing the file requires a TextWriter.  
        TextWriter writer = new StreamWriter(filename);  
  
        // Creates an instance of the class that will be serialized.  
        Group myGroup = new Group();  
  
        // Sets the object properties.  
        myGroup.GroupName = ".NET";  
  
        Byte [] hexByte = new Byte[2]{Convert.ToByte(100),  
        Convert.ToByte(50)};  
        myGroup.GroupNumber = hexByte;  
  
        DateTime myDate = new DateTime(2002,5,2);  
        myGroup.Today = myDate;  
  
        myGroup.PostitiveInt= "10000";  
        myGroup.IgnoreThis=true;  
        myGroup.Grouptype= GroupType.small;  
        Car thisCar =(Car)  myGroup.myCar("1234566");  
  
        // Prints the license number just to prove the car was created.  
        Console.WriteLine("License#: " + thisCar.licenseNumber + "\n");  
  
        // Serializes the class and closes the TextWriter.  
        mySerializer.Serialize(writer, myGroup);  
        writer.Close();  
    }  
  
    public void SerializeOverride(string filename)  
    {  
        // Creates an instance of the XmlSerializer class  
        // that overrides the serialization.  
        XmlSerializer overRideSerializer = CreateOverrideSerializer();  
  
        // Writing the file requires a TextWriter.  
        TextWriter writer = new StreamWriter(filename);  
  
        // Creates an instance of the class that will be serialized.  
        Group myGroup = new Group();  
  
        // Sets the object properties.  
        myGroup.GroupName = ".NET";  
  
        Byte [] hexByte = new Byte[2]{Convert.ToByte(100),  
        Convert.ToByte(50)};  
        myGroup.GroupNumber = hexByte;  
  
        DateTime myDate = new DateTime(2002,5,2);  
        myGroup.Today = myDate;  
  
        myGroup.PostitiveInt= "10000";  
        myGroup.IgnoreThis=true;  
        myGroup.Grouptype= GroupType.small;  
        Car thisCar =(Car)  myGroup.myCar("1234566");  
  
        // Serializes the class and closes the TextWriter.  
        overRideSerializer.Serialize(writer, myGroup);  
         writer.Close();  
    }  
  
    public void DeserializeOriginal(string filename)  
    {  
        // Creates an instance of the XmlSerializer class.  
        XmlTypeMapping myMapping =   
        (new SoapReflectionImporter().ImportTypeMapping(  
        typeof(Group)));  
        XmlSerializer mySerializer =    
        new XmlSerializer(myMapping);  
  
        TextReader reader = new StreamReader(filename);  
  
        // Deserializes and casts the object.  
        Group myGroup;   
        myGroup = (Group) mySerializer.Deserialize(reader);  
  
        Console.WriteLine(myGroup.GroupName);  
        Console.WriteLine(myGroup.GroupNumber[0]);  
        Console.WriteLine(myGroup.GroupNumber[1]);  
        Console.WriteLine(myGroup.Today);  
        Console.WriteLine(myGroup.PostitiveInt);  
        Console.WriteLine(myGroup.IgnoreThis);  
        Console.WriteLine();  
    }  
  
    public void DeserializeOverride(string filename)  
    {  
        // Creates an instance of the XmlSerializer class.  
        XmlSerializer overRideSerializer = CreateOverrideSerializer();  
        // Reading the file requires a TextReader.  
        TextReader reader = new StreamReader(filename);  
  
        // Deserializes and casts the object.  
        Group myGroup;   
        myGroup = (Group) overRideSerializer.Deserialize(reader);  
  
        Console.WriteLine(myGroup.GroupName);  
        Console.WriteLine(myGroup.GroupNumber[0]);  
        Console.WriteLine(myGroup.GroupNumber[1]);  
        Console.WriteLine(myGroup.Today);  
        Console.WriteLine(myGroup.PostitiveInt);  
        Console.WriteLine(myGroup.IgnoreThis);  
    }  
  
    private XmlSerializer CreateOverrideSerializer()  
    {  
        SoapAttributeOverrides mySoapAttributeOverrides =   
        new SoapAttributeOverrides();  
        SoapAttributes soapAtts = new SoapAttributes();  
  
        SoapElementAttribute mySoapElement = new SoapElementAttribute();  
        mySoapElement.ElementName = "xxxx";  
        soapAtts.SoapElement = mySoapElement;  
        mySoapAttributeOverrides.Add(typeof(Group), "PostitiveInt",   
        soapAtts);  
  
        // Overrides the IgnoreThis property.  
        SoapIgnoreAttribute myIgnore = new SoapIgnoreAttribute();  
        soapAtts = new SoapAttributes();  
        soapAtts.SoapIgnore = false;        
        mySoapAttributeOverrides.Add(typeof(Group), "IgnoreThis",   
        soapAtts);  
  
        // Overrides the GroupType enumeration.  
        soapAtts = new SoapAttributes();  
        SoapEnumAttribute xSoapEnum = new SoapEnumAttribute();  
        xSoapEnum.Name = "Over1000";  
        soapAtts.SoapEnum = xSoapEnum;  
  
        // Adds the SoapAttributes to the   
        // mySoapAttributeOverridesrides.  
        mySoapAttributeOverrides.Add(typeof(GroupType), "large",   
        soapAtts);  
  
        // Creates a second enumeration and adds it.  
        soapAtts = new SoapAttributes();  
        xSoapEnum = new SoapEnumAttribute();  
        xSoapEnum.Name = "ZeroTo1000";  
        soapAtts.SoapEnum = xSoapEnum;  
        mySoapAttributeOverrides.Add(typeof(GroupType), "small",   
        soapAtts);  
  
        // Overrides the Group type.  
        soapAtts = new SoapAttributes();  
        SoapTypeAttribute soapType = new SoapTypeAttribute();  
        soapType.TypeName = "Team";  
        soapAtts.SoapType = soapType;  
        mySoapAttributeOverrides.Add(typeof(Group),soapAtts);  
  
        // Creates an XmlTypeMapping that is used to create an instance   
        // of the XmlSerializer class. Then returns the XmlSerializer.  
        XmlTypeMapping myMapping = (new SoapReflectionImporter(  
        mySoapAttributeOverrides)).ImportTypeMapping(typeof(Group));  
  
        XmlSerializer ser = new XmlSerializer(myMapping);  
        return ser;  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)   
 [Атрибуты управления сериализацией с кодировкой SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [Сериализация XML с использованием XML-веб-служб](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)   
 [Практическое руководство. Сериализация объекта](../../../docs/standard/serialization/how-to-serialize-an-object.md)   
 [Практическое руководство. Десериализация объекта](../../../docs/standard/serialization/how-to-deserialize-an-object.md)   
 [Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)

