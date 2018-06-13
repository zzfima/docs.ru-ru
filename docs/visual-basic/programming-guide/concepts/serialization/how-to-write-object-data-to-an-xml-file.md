---
title: 'Как: запись данных объекта в XML-файл (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: 434706383c50e5df8e419e3988da8dc7cce87c83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652553"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="a467f-102">Как: запись данных объекта в XML-файл (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a467f-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="a467f-103">Показывает, как записать объект из класса в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a467f-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a467f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a467f-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="a467f-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a467f-105">Compiling the Code</span></span>  
 <span data-ttu-id="a467f-106">У класса должен быть открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="a467f-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a467f-107">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="a467f-107">Robust Programming</span></span>  
 <span data-ttu-id="a467f-108">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="a467f-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="a467f-109">В сериализуемом классе нет открытого конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="a467f-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="a467f-110">Файл существует и является файлом только для чтения (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a467f-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="a467f-111">Слишком длинный путь (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="a467f-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="a467f-112">Диск заполнен (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a467f-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a467f-113">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a467f-113">.NET Framework Security</span></span>  
 <span data-ttu-id="a467f-114">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="a467f-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="a467f-115">Если приложению требуется создать файл, оно должно иметь доступ к каталогу для создания файлов (`Create`).</span><span class="sxs-lookup"><span data-stu-id="a467f-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="a467f-116">Если файл уже существует, то приложению достаточно иметь лишь доступ для записи файлов (`Write`), т. е. меньшие привилегии.</span><span class="sxs-lookup"><span data-stu-id="a467f-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="a467f-117">Безопаснее создавать файл во время развертывания, если это возможно, а также предоставлять доступ `Read` к отдельному файлу вместо доступа `Create` к папке.</span><span class="sxs-lookup"><span data-stu-id="a467f-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a467f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a467f-118">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <span data-ttu-id="a467f-119">[How to: Read Object Data from an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) (Практическое руководство. Чтение данных объекта из XML-файла (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="a467f-119">[How to: Read Object Data from an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)</span></span>  
 [<span data-ttu-id="a467f-120">Сериализация (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a467f-120">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
