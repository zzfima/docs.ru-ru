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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922724"
---
# <a name="how-to-deserialize-an-object"></a>Практическое руководство. Десериализация объекта
При десериализации объекта формат передачи определяет, создается поток или объект файла. Определив формат передачи, можно вызвать методы <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> или <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> в зависимости от необходимости.  
  
### <a name="to-deserialize-an-object"></a>Десериализация объекта  
  
1. Постройте <xref:System.Xml.Serialization.XmlSerializer> с использованием типа сериализуемого объекта.  
  
2. Вызовите метод <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, чтобы создать реплику объекта. При десериализации следует приводить возвращенный объект к типу исходного, как показано в следующем примере, десериализующем объект в файл (хотя его также десериализовать и в поток).  
  
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
  
## <a name="see-also"></a>См. также

- [Введение в сериализацию XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Практическое руководство. Сериализация объекта](../../../docs/standard/serialization/how-to-serialize-an-object.md)
