---
title: "Практическое руководство. Сериализация объекта"
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
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: e988b7b56fca3f7e71c94155086bd242f8f9637b
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-serialize-an-object"></a>Практическое руководство. Сериализация объекта
Для сериализации объекта сначала следует создать сериализуемый объект и задать открытые свойства и поля. Для этого необходимо выбрать формат передачи, в котором будет храниться поток XML: поток или файл. Например, если поток XML должен храниться в неизменном виде, создайте объект <xref:System.IO.FileStream>.  
  
> [!NOTE]
>  Дополнительные примеры XML-сериализации см. в разделе [Примеры сериализации XML](../../../docs/standard/serialization/examples-of-xml-serialization.md).  
  
### <a name="to-serialize-an-object"></a>Сериализация объекта  
  
1.  Создайте объект и задайте его открытые поля и свойства.  
  
2.  Постройте <xref:System.Xml.Serialization.XmlSerializer> с использованием типа объекта. Дополнительные сведения см. в разделе конструкторов класса <xref:System.Xml.Serialization.XmlSerializer>.  
  
3.  Вызовите метод <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>, чтобы создать либо поток XML, либо файловое представление открытых свойств и полей объекта. В следующем примере создается файл.  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a>См. также  
 [Введение в сериализацию XML](../../../docs/standard/serialization/introducing-xml-serialization.md)   
 [Практическое руководство. Десериализация объекта](../../../docs/standard/serialization/how-to-deserialize-an-object.md)

