---
title: Практическое руководство. Поиск подкаталогов по заданному шаблону
ms.date: 07/20/2015
helpviewer_keywords:
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
ms.openlocfilehash: c8e13598080139cafabffb2e17d0a3b99c37dc5d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348773"
---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="fa62e-102">Практическое руководство. Поиск подкаталогов по шаблону в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa62e-102">How to: Find Subdirectories with a Specific Pattern in Visual Basic</span></span>

<span data-ttu-id="fa62e-103">Метод <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> возвращает доступную только для чтения коллекцию строк, представляющих имена путей к подкаталогам каталога.</span><span class="sxs-lookup"><span data-stu-id="fa62e-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> method returns a read-only collection of strings representing the path names for the subdirectories in a directory.</span></span> <span data-ttu-id="fa62e-104">Для указания определенного шаблона можно использовать параметр `wildCards` .</span><span class="sxs-lookup"><span data-stu-id="fa62e-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="fa62e-105">Если требуется включить в поиск содержимое подкаталогов, присвойте параметру `searchType` значение `SearchOption.SearchAllSubDirectories`.</span><span class="sxs-lookup"><span data-stu-id="fa62e-105">If you would like to include the contents of subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>

<span data-ttu-id="fa62e-106">Если каталоги, соответствующие указанному шаблону, не найдены, возвращается пустая коллекция.</span><span class="sxs-lookup"><span data-stu-id="fa62e-106">An empty collection is returned if no directories matching the specified pattern are found.</span></span>

## <a name="to-find-subdirectories-with-a-specific-pattern"></a><span data-ttu-id="fa62e-107">Поиск подкаталогов по заданному шаблону</span><span class="sxs-lookup"><span data-stu-id="fa62e-107">To find subdirectories with a specific pattern</span></span>

<span data-ttu-id="fa62e-108">Используйте метод `GetDirectories`, указав имя и путь к каталогу для поиска.</span><span class="sxs-lookup"><span data-stu-id="fa62e-108">Use the `GetDirectories` method, supplying the name and path of the directory you want to search.</span></span> <span data-ttu-id="fa62e-109">В следующем примере возвращаются все каталоги в структуре каталогов, имена которых содержат слово "Logs". Затем они добавляются в `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="fa62e-109">The following example returns all the directories in the directory structure that contain the word "Logs" in their name, and adds them to `ListBox1`.</span></span>

[!code-vb[VbVbcnFileAccess#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnFileAccess/VB/Class1.vb#1)]

## <a name="robust-programming"></a><span data-ttu-id="fa62e-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="fa62e-110">Robust Programming</span></span>

<span data-ttu-id="fa62e-111">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="fa62e-111">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="fa62e-112">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="fa62e-113">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="fa62e-114">Один или несколько указанных подстановочных знаков являются `Nothing`, пустой строкой или содержат только пробелы (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-114">One or more of the specified wildcard characters is `Nothing`, an empty string, or contains only spaces (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="fa62e-115">`directory` не существует (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-115">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="fa62e-116">`directory` указывает на существующий файл (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-116">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="fa62e-117">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="fa62e-118">Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-118">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="fa62e-119">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="fa62e-120">У пользователя отсутствуют необходимые разрешения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="fa62e-120">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa62e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fa62e-121">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>
- [<span data-ttu-id="fa62e-122">Практическое руководство. Поиск файлов по конкретному шаблону</span><span class="sxs-lookup"><span data-stu-id="fa62e-122">How to: Find Files with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)
