---
title: "Практическое руководство. Чтение данных объекта из XML-файла (C#)"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 02ff7a209cd78c70c6e3c443105d27b33c6f0af4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="8bbd9-102">Практическое руководство. Чтение данных объекта из XML-файла (C#)</span><span class="sxs-lookup"><span data-stu-id="8bbd9-102">How to: Read Object Data from an XML File (C#)</span></span>
<span data-ttu-id="8bbd9-103">В этом примере демонстрируется считывание данных объекта, которые ранее были записаны в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bbd9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8bbd9-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="8bbd9-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8bbd9-105">Compiling the Code</span></span>  
 <span data-ttu-id="8bbd9-106">Замените имя файла "c:\temp\SerializationOverview.xml" на имя файла, в котором содержатся сериализованные данные.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="8bbd9-107">Дополнительные сведения о сериализации данных см. в разделе [Практическое руководство. Запись данных объекта в XML-файл (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="8bbd9-107">For more information about serializing data, see [How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="8bbd9-108">У класса должен быть открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="8bbd9-109">Десериализуются только открытые свойства и поля.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8bbd9-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="8bbd9-110">Robust Programming</span></span>  
 <span data-ttu-id="8bbd9-111">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="8bbd9-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8bbd9-112">В сериализуемом классе нет открытого конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="8bbd9-113">Данные в файле не являются данными из класса, который десериализуется.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="8bbd9-114">Файл не существует (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="8bbd9-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8bbd9-115">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8bbd9-115">.NET Framework Security</span></span>  
 <span data-ttu-id="8bbd9-116">Всегда проверяйте входные данные и никогда не десериализуйте данные из непроверенных источников.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="8bbd9-117">Созданный заново объект выполняется на локальном компьютере с разрешениями кода, который его десериализовал.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="8bbd9-118">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="8bbd9-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bbd9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8bbd9-119">See Also</span></span>  
 <span data-ttu-id="8bbd9-120"><xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="8bbd9-120"><xref:System.IO.StreamWriter></span></span>   
 <span data-ttu-id="8bbd9-121">[Практическое руководство. Запись данных объекта в XML-файл (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="8bbd9-121">[How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span></span>  
 <span data-ttu-id="8bbd9-122">[Сериализация (C#)](../../../../csharp/programming-guide/concepts/serialization/index.md) </span><span class="sxs-lookup"><span data-stu-id="8bbd9-122">[Serialization (C# )](../../../../csharp/programming-guide/concepts/serialization/index.md) </span></span>  
 [<span data-ttu-id="8bbd9-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8bbd9-123">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)

