---
title: Руководство по программированию на C#. Создание файла или папки
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: e0d0a7fbbc7e6a5c9a0bd00dec1188c5cfdcf896
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705253"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="cd1fa-102">Руководство по программированию на C#. Создание файла или папки</span><span class="sxs-lookup"><span data-stu-id="cd1fa-102">How to create a file or folder (C# Programming Guide)</span></span>
<span data-ttu-id="cd1fa-103">Вы можете программно создать на компьютере папку, вложенную папку и файл во вложенной папке, а затем записать данные в этот файл.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd1fa-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cd1fa-104">Example</span></span>  
 [!code-csharp[csFilesandFolders#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#10)]  
  
 <span data-ttu-id="cd1fa-105">Если папка уже существует, <xref:System.IO.Directory.CreateDirectory%2A> не выполняет никаких действий и исключение не возникает.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-105">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="cd1fa-106">Но <xref:System.IO.File.Create%2A?displayProperty=nameWithType> заменяет существующий файл новым.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-106">However, <xref:System.IO.File.Create%2A?displayProperty=nameWithType> replaces an existing file with a new file.</span></span> <span data-ttu-id="cd1fa-107">Для того чтобы этого избежать, в примере используется оператор `if`-`else`.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-107">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="cd1fa-108">Изменив пример указанным ниже образом, вы можете задать различные результаты в зависимости от того, существует ли файл с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-108">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="cd1fa-109">Если файл не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-109">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="cd1fa-110">Если файл существует, код добавляет в него данные.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-110">If such a file exists, the code appends data to that file.</span></span>  
  
- <span data-ttu-id="cd1fa-111">Укажите конкретное имя файла.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-111">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
- <span data-ttu-id="cd1fa-112">В следующем коде замените оператор `if`-`else` на `using`.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-112">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="cd1fa-113">Выполните код в примере несколько раз, чтобы убедиться, что каждый раз данные добавляются в файл.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-113">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="cd1fa-114">Другие значения `FileMode`, которые можно использовать для проверки, см. в разделе <xref:System.IO.FileMode>.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-114">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="cd1fa-115">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="cd1fa-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="cd1fa-116">Имя папки недопустимо,</span><span class="sxs-lookup"><span data-stu-id="cd1fa-116">The folder name is malformed.</span></span> <span data-ttu-id="cd1fa-117">Например, оно содержит недопустимые символы или состоит из одних пробелов (класс <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="cd1fa-117">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="cd1fa-118">Используйте класс <xref:System.IO.Path>, чтобы создавать допустимые пути.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-118">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
- <span data-ttu-id="cd1fa-119">Родительская папка создаваемой папки доступна только для чтения (класс <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="cd1fa-119">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="cd1fa-120">Имя папки — `null` (класс <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="cd1fa-120">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="cd1fa-121">Имя папки слишком длинное (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="cd1fa-121">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="cd1fa-122">Имя папки состоит из одного двоеточия ":" (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="cd1fa-122">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cd1fa-123">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cd1fa-123">.NET Framework Security</span></span>  
 <span data-ttu-id="cd1fa-124">Экземпляр класса <xref:System.Security.SecurityException> может быть порожден как исключение в ситуации частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-124">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="cd1fa-125">Если у вас нет разрешения на создание папки, код в приведенном примере породит как исключение экземпляр класса <xref:System.UnauthorizedAccessException>.</span><span class="sxs-lookup"><span data-stu-id="cd1fa-125">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1fa-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cd1fa-126">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="cd1fa-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cd1fa-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cd1fa-128">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="cd1fa-128">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
