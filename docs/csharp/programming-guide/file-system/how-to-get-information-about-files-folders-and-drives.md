---
title: "Практическое руководство. Получение сведений о файлах, папках и дисках (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6067ea9d51c31c9398c7b1fcd83ca8fa3a4fec76
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a><span data-ttu-id="96b02-102">Практическое руководство. Получение сведений о файлах, папках и дисках (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="96b02-102">How to: Get Information About Files, Folders, and Drives  (C# Programming Guide)</span></span>
<span data-ttu-id="96b02-103">В платформе .NET Framework доступ к сведениям о файловой системе можно получить, используя следующие классы:</span><span class="sxs-lookup"><span data-stu-id="96b02-103">In the .NET Framework, you can access file system information by using the following classes:</span></span>  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 <span data-ttu-id="96b02-104">Классы <xref:System.IO.FileInfo> и <xref:System.IO.DirectoryInfo> представляют файл или каталог и содержат свойства, представляющие многие атрибуты файла, поддерживаемые файловой системой NTFS.</span><span class="sxs-lookup"><span data-stu-id="96b02-104">The <xref:System.IO.FileInfo> and <xref:System.IO.DirectoryInfo> classes represent a file or directory and contain properties that expose many of the file attributes that are supported by the NTFS file system.</span></span> <span data-ttu-id="96b02-105">Они также содержат методы для открытия, закрытия, перемещения и удаления файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="96b02-105">They also contain methods for opening, closing, moving, and deleting files and folders.</span></span> <span data-ttu-id="96b02-106">Экземпляры этих классов можно создать, передав в конструктор строку, представляющую имя файла, папки или диска.</span><span class="sxs-lookup"><span data-stu-id="96b02-106">You can create instances of these classes by passing a string that represents the name of the file, folder, or drive in to the constructor:</span></span>  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <span data-ttu-id="96b02-107">Имена файлов, папок или дисков можно также получить с помощью вызова <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName> и <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="96b02-107">You can also obtain the names of files, folders, or drives by using calls to <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName>, and <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="96b02-108">Классы <xref:System.IO.Directory?displayProperty=fullName> и <xref:System.IO.File?displayProperty=fullName> предоставляют статические методы для получения сведений о каталогах и файлах.</span><span class="sxs-lookup"><span data-stu-id="96b02-108">The <xref:System.IO.Directory?displayProperty=fullName> and <xref:System.IO.File?displayProperty=fullName> classes provide static methods for retrieving information about directories and files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96b02-109">Пример</span><span class="sxs-lookup"><span data-stu-id="96b02-109">Example</span></span>  
 <span data-ttu-id="96b02-110">В следующем примере показаны различные способы доступа к сведениям о файлах и папках.</span><span class="sxs-lookup"><span data-stu-id="96b02-110">The following example shows various ways to access information about files and folders.</span></span>  
  
 <span data-ttu-id="96b02-111">[!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="96b02-111">[!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="96b02-112">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="96b02-112">Robust Programming</span></span>  
 <span data-ttu-id="96b02-113">При обработке заданных пользователем строк, определяющих пути, необходимо также обрабатывать исключения для следующих условий:</span><span class="sxs-lookup"><span data-stu-id="96b02-113">When you process user-specified path strings, you should also handle exceptions for the following conditions:</span></span>  
  
-   <span data-ttu-id="96b02-114">Неверное имя файла.</span><span class="sxs-lookup"><span data-stu-id="96b02-114">The file name is malformed.</span></span> <span data-ttu-id="96b02-115">Например, оно содержит недопустимые символы или состоит из одних пробелов.</span><span class="sxs-lookup"><span data-stu-id="96b02-115">For example, it contains invalid characters or only white space.</span></span>  
  
-   <span data-ttu-id="96b02-116">Имя файла имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="96b02-116">The file name is null.</span></span>  
  
-   <span data-ttu-id="96b02-117">Имя файла больше максимальной длины, определенной системой.</span><span class="sxs-lookup"><span data-stu-id="96b02-117">The file name is longer than the system-defined maximum length.</span></span>  
  
-   <span data-ttu-id="96b02-118">Имя файла содержит двоеточие (:).</span><span class="sxs-lookup"><span data-stu-id="96b02-118">The file name contains a colon (:).</span></span>  
  
 <span data-ttu-id="96b02-119">Если у приложения недостаточно прав для чтения указанного файла, метод `Exists` возвратит значение `false` независимо от существования указанного пути. Исключений этот метод не вызывает.</span><span class="sxs-lookup"><span data-stu-id="96b02-119">If the application does not have sufficient permissions to read the specified file, the `Exists` method returns `false` regardless of whether a path exists; the method does not throw an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b02-120">См. также</span><span class="sxs-lookup"><span data-stu-id="96b02-120">See Also</span></span>  
 <span data-ttu-id="96b02-121"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="96b02-121"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="96b02-122">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="96b02-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="96b02-123">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="96b02-123">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

