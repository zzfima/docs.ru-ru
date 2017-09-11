---
title: "Практическое руководство. Создание файла или папки (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
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
ms.openlocfilehash: 150190eeef829bd0431eeea7789025b9905553e3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="70b54-102">Практическое руководство. Создание файла или папки (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="70b54-102">How to: Create a File or Folder (C# Programming Guide)</span></span>
<span data-ttu-id="70b54-103">Вы можете программно создать на компьютере папку, вложенную папку и файл во вложенной папке, а затем записать данные в этот файл.</span><span class="sxs-lookup"><span data-stu-id="70b54-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70b54-104">Пример</span><span class="sxs-lookup"><span data-stu-id="70b54-104">Example</span></span>  
 <span data-ttu-id="70b54-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="70b54-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span></span>  
  
 <span data-ttu-id="70b54-106">Если папка уже существует, <xref:System.IO.Directory.CreateDirectory%2A> не выполняет никаких действий и исключение не возникает.</span><span class="sxs-lookup"><span data-stu-id="70b54-106">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="70b54-107">Но <xref:System.IO.File.Create%2A?displayProperty=fullName> заменяет существующий файл новым.</span><span class="sxs-lookup"><span data-stu-id="70b54-107">However, <xref:System.IO.File.Create%2A?displayProperty=fullName> replaces an existing file with a new file.</span></span> <span data-ttu-id="70b54-108">Для того чтобы этого избежать, в примере используется оператор `if`-`else`.</span><span class="sxs-lookup"><span data-stu-id="70b54-108">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="70b54-109">Изменив пример указанным ниже образом, вы можете задать различные результаты в зависимости от того, существует ли файл с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="70b54-109">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="70b54-110">Если файл не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="70b54-110">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="70b54-111">Если файл существует, код добавляет в него данные.</span><span class="sxs-lookup"><span data-stu-id="70b54-111">If such a file exists, the code appends data to that file.</span></span>  
  
-   <span data-ttu-id="70b54-112">Укажите конкретное имя файла.</span><span class="sxs-lookup"><span data-stu-id="70b54-112">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   <span data-ttu-id="70b54-113">В следующем коде замените оператор `if`-`else` на `using`.</span><span class="sxs-lookup"><span data-stu-id="70b54-113">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="70b54-114">Выполните код в примере несколько раз, чтобы убедиться, что каждый раз данные добавляются в файл.</span><span class="sxs-lookup"><span data-stu-id="70b54-114">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="70b54-115">Другие значения `FileMode`, которые можно использовать для проверки, см. в разделе <xref:System.IO.FileMode>.</span><span class="sxs-lookup"><span data-stu-id="70b54-115">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="70b54-116">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="70b54-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="70b54-117">Имя папки недопустимо,</span><span class="sxs-lookup"><span data-stu-id="70b54-117">The folder name is malformed.</span></span> <span data-ttu-id="70b54-118">Например, оно содержит недопустимые символы или состоит из одних пробелов (класс <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="70b54-118">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="70b54-119">Используйте класс <xref:System.IO.Path>, чтобы создавать допустимые пути.</span><span class="sxs-lookup"><span data-stu-id="70b54-119">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
-   <span data-ttu-id="70b54-120">Родительская папка создаваемой папки доступна только для чтения (класс <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="70b54-120">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="70b54-121">Имя папки — `null` (класс <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="70b54-121">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="70b54-122">Имя папки слишком длинное (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="70b54-122">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="70b54-123">Имя папки состоит из одного двоеточия ":" (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="70b54-123">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="70b54-124">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="70b54-124">.NET Framework Security</span></span>  
 <span data-ttu-id="70b54-125">Экземпляр класса <xref:System.Security.SecurityException> может быть порожден как исключение в ситуации частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="70b54-125">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="70b54-126">Если у вас нет разрешения на создание папки, код в приведенном примере породит как исключение экземпляр класса <xref:System.UnauthorizedAccessException>.</span><span class="sxs-lookup"><span data-stu-id="70b54-126">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b54-127">См. также</span><span class="sxs-lookup"><span data-stu-id="70b54-127">See Also</span></span>  
 <span data-ttu-id="70b54-128"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="70b54-128"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="70b54-129">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="70b54-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="70b54-130">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="70b54-130">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

