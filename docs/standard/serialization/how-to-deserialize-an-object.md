---
title: Практическое руководство. Десериализация объекта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: e1a960d39319beee1c3c257fcd3ade207de11010
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881144"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="df559-102">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="df559-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="df559-103">При десериализации объекта формат передачи определяет, создается поток или объект файла.</span><span class="sxs-lookup"><span data-stu-id="df559-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="df559-104">Определив формат передачи, можно вызвать методы <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> или <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> в зависимости от необходимости.</span><span class="sxs-lookup"><span data-stu-id="df559-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="df559-105">Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="df559-105">To deserialize an object</span></span>  
  
1. <span data-ttu-id="df559-106">Постройте <xref:System.Xml.Serialization.XmlSerializer> с использованием типа сериализуемого объекта.</span><span class="sxs-lookup"><span data-stu-id="df559-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2. <span data-ttu-id="df559-107">Вызовите метод <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, чтобы создать реплику объекта.</span><span class="sxs-lookup"><span data-stu-id="df559-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="df559-108">При десериализации, необходимо привести возвращенный объект к типу исходного, как показано в следующем примере, который десериализует объект из файла (несмотря на то, что он может быть десериализован из потока).</span><span class="sxs-lookup"><span data-stu-id="df559-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object from a file (although it could also be deserialized from a stream).</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="df559-109">См. также</span><span class="sxs-lookup"><span data-stu-id="df559-109">See also</span></span>

- [<span data-ttu-id="df559-110">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="df559-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="df559-111">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="df559-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
