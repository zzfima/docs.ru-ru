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
ms.openlocfilehash: 53b4a3e3848c1aa92bfa9fbd80bb031125257fc2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298140"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="32f91-102">Практическое руководство. Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="32f91-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="32f91-103">При десериализации объекта формат передачи определяет, создается поток или объект файла.</span><span class="sxs-lookup"><span data-stu-id="32f91-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="32f91-104">Определив формат передачи, можно вызвать методы <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> или <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> в зависимости от необходимости.</span><span class="sxs-lookup"><span data-stu-id="32f91-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="32f91-105">Десериализация объекта</span><span class="sxs-lookup"><span data-stu-id="32f91-105">To deserialize an object</span></span>  
  
1. <span data-ttu-id="32f91-106">Постройте <xref:System.Xml.Serialization.XmlSerializer> с использованием типа сериализуемого объекта.</span><span class="sxs-lookup"><span data-stu-id="32f91-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2. <span data-ttu-id="32f91-107">Вызовите метод <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, чтобы создать реплику объекта.</span><span class="sxs-lookup"><span data-stu-id="32f91-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="32f91-108">При десериализации следует приводить возвращенный объект к типу исходного, как показано в следующем примере, десериализующем объект в файл (хотя его также десериализовать и в поток).</span><span class="sxs-lookup"><span data-stu-id="32f91-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object into a file (although it could also be deserialized into a stream).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="32f91-109">См. также</span><span class="sxs-lookup"><span data-stu-id="32f91-109">See also</span></span>

- [<span data-ttu-id="32f91-110">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="32f91-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="32f91-111">Практическое руководство. Сериализация объекта</span><span class="sxs-lookup"><span data-stu-id="32f91-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
