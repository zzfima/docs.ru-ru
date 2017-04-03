---
title: "Практическое руководство. Чтение данных объекта из XML-файла (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c5f8c23a86c7a09d6f8d0b8c6f1684a38d0336a3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a>Практическое руководство. Чтение данных объекта из XML-файла (C#)
В этом примере производится чтение данных объекта, которые были предварительно записаны в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="example"></a>Пример  
  
```csharp  
public class Book  
{  
    public String title;  
}         
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =   
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Замените имя файла "c:\temp\SerializationOverview.xml" на имя файла, в котором содержатся сериализованные данные. Дополнительные сведения о сериализации данных см. в разделе [Практическое руководство. Запись данных объекта в XML-файл (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
 У класса должен быть открытый конструктор без параметров.  
  
 Десериализуются только открытые свойства и поля.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   В сериализуемом классе нет открытого конструктора без параметров.  
  
-   Данные в файле не являются данными из класса, который десериализуется.  
  
-   Файл не существует (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда проверяйте входные данные и никогда не десериализуйте данные из непроверенных источников. Созданный заново объект выполняется на локальном компьютере с разрешениями кода, который его десериализовал. Следует проверять все входные данные перед использованием их в приложении.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.StreamWriter>   
 [Практическое руководство. Запись данных объекта в XML-файл (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)   
 [Сериализация (C#)](../../../../csharp/programming-guide/concepts/serialization/index.md)   
 [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)
