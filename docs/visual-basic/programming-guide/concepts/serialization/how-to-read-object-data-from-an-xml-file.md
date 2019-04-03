---
title: Практическое руководство. Чтение данных объекта из XML-файл (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: f6233fc7ce74cbd39237bab07cfd2ed22b9c2240
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834898"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>Практическое руководство. Чтение данных объекта из XML-файл (Visual Basic)
В этом примере демонстрируется считывание данных объекта, которые ранее были записаны в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.  
  
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
 Замените имя файла "c:\temp\SerializationOverview.xml" на имя файла, в котором содержатся сериализованные данные. Дополнительные сведения о сериализации данных см. в разделе [Практическое руководство. Запись данных объекта в XML-файл (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
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

- <xref:System.IO.StreamWriter>
- [Практическое руководство. Запись данных объекта в XML-файл (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
- [Сериализация (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
- [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)
