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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3b9697f763a2d781c37960d46cbc7fa4536c84b4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="f9c89-102">Практическое руководство: чтение данных объекта из файла XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9c89-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="f9c89-103">Этот пример считывает данные объектов, которые были предварительно записаны в XML-файл с помощью <xref:System.Xml.Serialization.XmlSerializer>класса.</xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="f9c89-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9c89-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f9c89-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="f9c89-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f9c89-105">Compiling the Code</span></span>  
 <span data-ttu-id="f9c89-106">Замените имя файла «c:\temp\SerializationOverview.xml» с именем файла, содержащего сериализованные данные.</span><span class="sxs-lookup"><span data-stu-id="f9c89-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="f9c89-107">Дополнительные сведения о сериализации данных см. в разделе [как: запись данных объекта в XML-файл (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="f9c89-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="f9c89-108">Класс должен иметь открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="f9c89-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="f9c89-109">Десериализуются только открытые свойства и поля.</span><span class="sxs-lookup"><span data-stu-id="f9c89-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f9c89-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f9c89-110">Robust Programming</span></span>  
 <span data-ttu-id="f9c89-111">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="f9c89-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f9c89-112">Сериализуемый класс не имеет открытого конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="f9c89-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="f9c89-113">Данные в файле не являются данными из десериализованного класса.</span><span class="sxs-lookup"><span data-stu-id="f9c89-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="f9c89-114">Файл не существует (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="f9c89-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f9c89-115">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9c89-115">.NET Framework Security</span></span>  
 <span data-ttu-id="f9c89-116">Всегда следует проверять ввод и никогда не стоит десериализовывать данные из непроверенных источников.</span><span class="sxs-lookup"><span data-stu-id="f9c89-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="f9c89-117">Созданный заново объект выполняется на локальном компьютере с разрешениями кода, который его десериализации.</span><span class="sxs-lookup"><span data-stu-id="f9c89-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="f9c89-118">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="f9c89-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9c89-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f9c89-119">See Also</span></span>  
 <span data-ttu-id="f9c89-120"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="f9c89-120"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="f9c89-121"> [Практическое руководство: запись данных объекта в XML-файл (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="f9c89-121"> [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span></span>  
<span data-ttu-id="f9c89-122"> [Сериализация (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span><span class="sxs-lookup"><span data-stu-id="f9c89-122"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span></span>  
<span data-ttu-id="f9c89-123"> [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="f9c89-123"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md)</span></span>
