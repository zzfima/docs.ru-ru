---
title: "Практическое руководство: запись данных объекта в XML-файл (Visual Basic) | Документы Microsoft"
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
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
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
ms.openlocfilehash: 146ccb7b1999049106d5f0be1ce78e740dfcf060
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a>Практическое руководство: запись данных объекта в XML-файл (Visual Basic)
Этот пример записывает объект из класса в XML-файл с помощью <xref:System.Xml.Serialization.XmlSerializer>класса.</xref:System.Xml.Serialization.XmlSerializer>  
  
## <a name="example"></a>Пример  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Класс должен иметь открытый конструктор без параметров.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Сериализуемый класс не имеет открытого конструктора без параметров.  
  
-   Файл существует и доступен только для чтения (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
-   Указан слишком длинный путь (<xref:System.IO.PathTooLongException>).</xref:System.IO.PathTooLongException>  
  
-   Диск заполнен (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 В этом примере создается новый файл, если файл еще не существует. Если приложению требуется создать файл, оно должно `Create` доступ к папке. Если файл уже существует, приложению требуется только `Write` доступ меньшие привилегии. Там, где это возможно, безопаснее создать файл во время развертывания и предоставить `Read` доступа для одного файла, а не `Create` доступ к папке.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.StreamWriter></xref:System.IO.StreamWriter>   
 [Практическое руководство: чтение данных объекта из файла XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)   
 [Сериализация (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
