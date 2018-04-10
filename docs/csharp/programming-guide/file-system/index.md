---
title: Файловая система и реестр (Руководство по программированию на C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d1b4e3fa9b6c6da89abd242be855e9fb7c16dd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="6146d-102">Файловая система и реестр (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6146d-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="6146d-103">Перечисленные здесь статьи демонстрируют, как использовать C# и .NET Framework для выполнения различных базовых операций над файлами, папками и реестром.</span><span class="sxs-lookup"><span data-stu-id="6146d-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6146d-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="6146d-104">In This Section</span></span>  
  
|<span data-ttu-id="6146d-105">**Заголовок**</span><span class="sxs-lookup"><span data-stu-id="6146d-105">**Title**</span></span>|<span data-ttu-id="6146d-106">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6146d-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="6146d-107">Практическое руководство. Перебор дерева папок</span><span class="sxs-lookup"><span data-stu-id="6146d-107">How to: Iterate Through a Directory Tree</span></span>](../../../csharp/programming-guide/file-system/how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="6146d-108">Демонстрирует ручной перебор дерева каталогов.</span><span class="sxs-lookup"><span data-stu-id="6146d-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="6146d-109">Практическое руководство. Получение сведений о файлах, папках и дисках</span><span class="sxs-lookup"><span data-stu-id="6146d-109">How to: Get Information About Files, Folders, and Drives</span></span>](../../../csharp/programming-guide/file-system/how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="6146d-110">Демонстрирует, как получить сведения о файлах, папках и дисках, например время создания и размер.</span><span class="sxs-lookup"><span data-stu-id="6146d-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="6146d-111">Практическое руководство. Создание файла или папки</span><span class="sxs-lookup"><span data-stu-id="6146d-111">How to: Create a File or Folder</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-file-or-folder.md)|<span data-ttu-id="6146d-112">Демонстрирует создание нового файла и новой папки.</span><span class="sxs-lookup"><span data-stu-id="6146d-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="6146d-113">Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="6146d-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="6146d-114">Демонстрирует копирование, удаление и перемещение файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="6146d-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="6146d-115">Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами</span><span class="sxs-lookup"><span data-stu-id="6146d-115">How to: Provide a Progress Dialog Box for File Operations</span></span>](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="6146d-116">Объясняет, как отобразить стандартное диалоговое окно Windows для хода выполнения определенных файловых операций.</span><span class="sxs-lookup"><span data-stu-id="6146d-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="6146d-117">Практическое руководство. Запись в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="6146d-117">How to: Write to a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)|<span data-ttu-id="6146d-118">Демонстрирует запись в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="6146d-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="6146d-119">Практическое руководство. Чтение из текстового файла</span><span class="sxs-lookup"><span data-stu-id="6146d-119">How to: Read From a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-read-from-a-text-file.md)|<span data-ttu-id="6146d-120">Демонстрирует чтение из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="6146d-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="6146d-121">Практическое руководство. Построчное чтение текстового файла</span><span class="sxs-lookup"><span data-stu-id="6146d-121">How to: Read a Text File One Line at a Time</span></span>](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="6146d-122">Демонстрирует извлечение текста из файла по одной строке.</span><span class="sxs-lookup"><span data-stu-id="6146d-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="6146d-123">Практическое руководство. Создание раздела в реестре</span><span class="sxs-lookup"><span data-stu-id="6146d-123">How to: Create a Key In the Registry</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="6146d-124">Демонстрирует запись раздела в системный реестр.</span><span class="sxs-lookup"><span data-stu-id="6146d-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="6146d-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6146d-125">Related Sections</span></span>  
 [<span data-ttu-id="6146d-126">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="6146d-126">File and Stream I/O</span></span>](https://msdn.microsoft.com/library/k3352a4t)  
  
 [<span data-ttu-id="6146d-127">Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="6146d-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="6146d-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6146d-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
  
 [<span data-ttu-id="6146d-129">Файлы, папки и диски</span><span class="sxs-lookup"><span data-stu-id="6146d-129">Files, Folders and Drives</span></span>](../../../csharp/programming-guide/file-system/index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
