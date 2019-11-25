---
title: Практическое руководство. Чтение данных объекта из XML-файла
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: c997af4729a24a6b5bd5b22d0153860cff3282d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346426"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="79d4a-102">How to: Read Object Data from an XML File (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79d4a-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="79d4a-103">В этом примере демонстрируется считывание данных объекта, которые ранее были записаны в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="79d4a-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79d4a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="79d4a-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="79d4a-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="79d4a-105">Compiling the Code</span></span>  
 <span data-ttu-id="79d4a-106">Замените имя файла "c:\temp\SerializationOverview.xml" на имя файла, в котором содержатся сериализованные данные.</span><span class="sxs-lookup"><span data-stu-id="79d4a-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="79d4a-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="79d4a-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="79d4a-108">У класса должен быть открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="79d4a-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="79d4a-109">Десериализуются только открытые свойства и поля.</span><span class="sxs-lookup"><span data-stu-id="79d4a-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="79d4a-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="79d4a-110">Robust Programming</span></span>  
 <span data-ttu-id="79d4a-111">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="79d4a-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="79d4a-112">В сериализуемом классе нет открытого конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="79d4a-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="79d4a-113">Данные в файле не являются данными из класса, который десериализуется.</span><span class="sxs-lookup"><span data-stu-id="79d4a-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="79d4a-114">Файл не существует (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="79d4a-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="79d4a-115">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="79d4a-115">.NET Framework Security</span></span>  
 <span data-ttu-id="79d4a-116">Всегда проверяйте входные данные и никогда не десериализуйте данные из непроверенных источников.</span><span class="sxs-lookup"><span data-stu-id="79d4a-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="79d4a-117">Созданный заново объект выполняется на локальном компьютере с разрешениями кода, который его десериализовал.</span><span class="sxs-lookup"><span data-stu-id="79d4a-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="79d4a-118">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="79d4a-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d4a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="79d4a-119">See also</span></span>

- <xref:System.IO.StreamWriter>
- <span data-ttu-id="79d4a-120">[How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) (Практическое руководство. Запись данных объекта в XML-файл (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="79d4a-120">[How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)</span></span>
- [<span data-ttu-id="79d4a-121">Сериализация (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79d4a-121">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
- [<span data-ttu-id="79d4a-122">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79d4a-122">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
