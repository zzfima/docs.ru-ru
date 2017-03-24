---
title: "Практическое руководство: чтение данных объекта из файла XML (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c448d79a88517925712f79ed061aa90933e3f6d1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>Практическое руководство: чтение данных объекта из файла XML (Visual Basic)
Этот пример считывает данные объектов, которые были предварительно записаны в XML-файл с помощью <xref:System.Xml.Serialization.XmlSerializer>класса.</xref:System.Xml.Serialization.XmlSerializer>  
  
## <a name="example"></a>Пример  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Замените имя файла «c:\temp\SerializationOverview.xml» с именем файла, содержащего сериализованные данные. Дополнительные сведения о сериализации данных см. в разделе [как: запись данных объекта в XML-файл (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
 Класс должен иметь открытый конструктор без параметров.  
  
 Десериализуются только открытые свойства и поля.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Сериализуемый класс не имеет открытого конструктора без параметров.  
  
-   Данные в файле не являются данными из десериализованного класса.  
  
-   Файл не существует (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда следует проверять ввод и никогда не стоит десериализовывать данные из непроверенных источников. Созданный заново объект выполняется на локальном компьютере с разрешениями кода, который его десериализации. Следует проверять все входные данные перед использованием их в приложении.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.StreamWriter></xref:System.IO.StreamWriter>   
 [Практическое руководство: запись данных объекта в XML-файл (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)   
 [Сериализация (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)   
 [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)
