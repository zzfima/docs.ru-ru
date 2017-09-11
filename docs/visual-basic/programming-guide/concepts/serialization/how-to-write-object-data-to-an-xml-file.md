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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 27131f357c1f5afc75645bff88ae5d7cd2395617
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="7da5c-102">Практическое руководство: запись данных объекта в XML-файл (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7da5c-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="7da5c-103">Этот пример записывает объект из класса в XML-файл с помощью <xref:System.Xml.Serialization.XmlSerializer>класса.</xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="7da5c-103">TThis example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7da5c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7da5c-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="7da5c-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7da5c-105">Compiling the Code</span></span>  
 <span data-ttu-id="7da5c-106">Класс должен иметь открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="7da5c-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7da5c-107">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="7da5c-107">Robust Programming</span></span>  
 <span data-ttu-id="7da5c-108">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="7da5c-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="7da5c-109">Сериализуемый класс не имеет открытого конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="7da5c-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="7da5c-110">Файл существует и доступен только для чтения (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="7da5c-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="7da5c-111">Указан слишком длинный путь (<xref:System.IO.PathTooLongException>).</xref:System.IO.PathTooLongException></span><span class="sxs-lookup"><span data-stu-id="7da5c-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="7da5c-112">Диск заполнен (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="7da5c-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7da5c-113">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7da5c-113">.NET Framework Security</span></span>  
 <span data-ttu-id="7da5c-114">В этом примере создается новый файл, если файл еще не существует.</span><span class="sxs-lookup"><span data-stu-id="7da5c-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="7da5c-115">Если приложению требуется создать файл, оно должно `Create` доступ к папке.</span><span class="sxs-lookup"><span data-stu-id="7da5c-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="7da5c-116">Если файл уже существует, приложению требуется только `Write` доступ меньшие привилегии.</span><span class="sxs-lookup"><span data-stu-id="7da5c-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="7da5c-117">Там, где это возможно, безопаснее создать файл во время развертывания и предоставить `Read` доступа для одного файла, а не `Create` доступ к папке.</span><span class="sxs-lookup"><span data-stu-id="7da5c-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da5c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7da5c-118">See Also</span></span>  
 <span data-ttu-id="7da5c-119"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="7da5c-119"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="7da5c-120"> [Практическое руководство: чтение данных объекта из файла XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="7da5c-120"> [How to: Read Object Data from an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span></span>  
<span data-ttu-id="7da5c-121"> [Сериализация (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)</span><span class="sxs-lookup"><span data-stu-id="7da5c-121"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)</span></span>
