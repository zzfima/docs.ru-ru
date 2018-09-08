---
title: Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: cdfa2c8c7a27806873217495ac09f7f20e82b6bc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44209307"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="4748e-102">Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="4748e-102">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="4748e-103">Поскольку сообщение SOAP сформировано с использованием XML, можно использовать <xref:System.Xml.Serialization.XmlSerializer> для сериализации классов и генерации сообщений с кодировкой SOAP.</span><span class="sxs-lookup"><span data-stu-id="4748e-103">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="4748e-104">Полученный в результате код XML соответствует [разделу 5 документа "Simple Object Access Protocol (SOAP) 1.1", разработанного консорциумом W3С](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="4748e-104">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="4748e-105">При создании XML-веб-службы, которая осуществляет связь посредством сообщений SOAP, можно настроить поток XML, применив к классам и членам классов набор специальных атрибутов SOAP.</span><span class="sxs-lookup"><span data-stu-id="4748e-105">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="4748e-106">Список атрибутов см. в разделе [Атрибуты, которые управляют сериализацией с кодировкой SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="4748e-106">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="4748e-107">Чтобы сериализовать объект как поток XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="4748e-107">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1.  <span data-ttu-id="4748e-108">Создайте класс с помощью [средства определения схемы XML (xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4748e-108">Create the class using the [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2.  <span data-ttu-id="4748e-109">Примените один или несколько специальных атрибутов из `System.Xml.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="4748e-109">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="4748e-110">Список атрибутов см. в разделе "Атрибуты управления сериализацией с кодировкой SOAP".</span><span class="sxs-lookup"><span data-stu-id="4748e-110">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3.  <span data-ttu-id="4748e-111">Создайте `XmlTypeMapping` путем создания нового `SoapReflectionImporter` и вызова метода `ImportTypeMapping` с типом сериализуемого класса.</span><span class="sxs-lookup"><span data-stu-id="4748e-111">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="4748e-112">В следующем примере кода вызывается метод `ImportTypeMapping` класса `SoapReflectionImporter` для создания `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="4748e-112">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4.  <span data-ttu-id="4748e-113">Создайте экземпляр класса `XmlSerializer`, передав `XmlTypeMapping` конструктору <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.</span><span class="sxs-lookup"><span data-stu-id="4748e-113">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  <span data-ttu-id="4748e-114">Вызовите метод `Serialize` или `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="4748e-114">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4748e-115">Пример</span><span class="sxs-lookup"><span data-stu-id="4748e-115">Example</span></span>  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a><span data-ttu-id="4748e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4748e-116">See also</span></span>

- [<span data-ttu-id="4748e-117">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="4748e-117">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
- [<span data-ttu-id="4748e-118">Атрибуты управления сериализацией с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="4748e-118">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
- [<span data-ttu-id="4748e-119">Сериализация XML с использованием XML-веб-служб</span><span class="sxs-lookup"><span data-stu-id="4748e-119">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
- [<span data-ttu-id="4748e-120">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="4748e-120">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
- [<span data-ttu-id="4748e-121">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="4748e-121">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
- [<span data-ttu-id="4748e-122">Практическое руководство. Переопределение сериализации XML с кодировкой SOAP</span><span class="sxs-lookup"><span data-stu-id="4748e-122">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)
