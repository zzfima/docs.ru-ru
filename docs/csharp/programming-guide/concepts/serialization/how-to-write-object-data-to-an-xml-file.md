---
title: Запись данных объекта в XML-файл (C#)
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: 475e9398f20a2a4db9fb537d0b8d44f0273e980b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346447"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="1b59e-102">Запись данных объекта в XML-файл (C#)</span><span class="sxs-lookup"><span data-stu-id="1b59e-102">How to write object data to an XML file (C#)</span></span>
<span data-ttu-id="1b59e-103">Показывает, как записать объект из класса в XML-файл с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1b59e-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b59e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1b59e-104">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;   
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =   
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1b59e-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1b59e-105">Compiling the Code</span></span>  
 <span data-ttu-id="1b59e-106">В сериализуемом классе должен быть открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="1b59e-106">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1b59e-107">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="1b59e-107">Robust Programming</span></span>  
 <span data-ttu-id="1b59e-108">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="1b59e-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="1b59e-109">В сериализуемом классе нет открытого конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="1b59e-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="1b59e-110">Файл существует и является файлом только для чтения (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="1b59e-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="1b59e-111">Слишком длинный путь (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="1b59e-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="1b59e-112">Диск заполнен (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="1b59e-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1b59e-113">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1b59e-113">.NET Framework Security</span></span>  
 <span data-ttu-id="1b59e-114">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="1b59e-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="1b59e-115">Если приложению требуется создать файл, оно должно иметь доступ к каталогу для создания файлов (`Create`).</span><span class="sxs-lookup"><span data-stu-id="1b59e-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="1b59e-116">Если файл уже существует, то приложению достаточно иметь лишь доступ для записи файлов (`Write`), т. е. меньшие привилегии.</span><span class="sxs-lookup"><span data-stu-id="1b59e-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="1b59e-117">Безопаснее создавать файл во время развертывания, если это возможно, а также предоставлять доступ `Read` к отдельному файлу вместо доступа `Create` к папке.</span><span class="sxs-lookup"><span data-stu-id="1b59e-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b59e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1b59e-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="1b59e-119">Практическое руководство. Чтение данных объекта из XML-файла (C#)</span><span class="sxs-lookup"><span data-stu-id="1b59e-119">How to read object data from an XML file (C#)</span></span>](./how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="1b59e-120">Сериализация (C#)</span><span class="sxs-lookup"><span data-stu-id="1b59e-120">Serialization (C#)</span></span>](./index.md)
