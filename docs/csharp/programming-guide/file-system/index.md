---
title: Руководство по программированию на C#. Файловая система и реестр
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: ef6c1da09ea0435643caba0f5e2819c064f8db01
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589913"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="ff72b-102">Файловая система и реестр (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ff72b-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="ff72b-103">Перечисленные здесь статьи демонстрируют, как использовать C# и .NET Framework для выполнения различных базовых операций над файлами, папками и реестром.</span><span class="sxs-lookup"><span data-stu-id="ff72b-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff72b-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ff72b-104">In This Section</span></span>  
  
|<span data-ttu-id="ff72b-105">**Заголовок**</span><span class="sxs-lookup"><span data-stu-id="ff72b-105">**Title**</span></span>|<span data-ttu-id="ff72b-106">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ff72b-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="ff72b-107">Практическое руководство. Итерация дерева каталогов</span><span class="sxs-lookup"><span data-stu-id="ff72b-107">How to: Iterate Through a Directory Tree</span></span>](./how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="ff72b-108">Демонстрирует ручной перебор дерева каталогов.</span><span class="sxs-lookup"><span data-stu-id="ff72b-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="ff72b-109">Практическое руководство. Получение сведений о файлах, папках и дисках</span><span class="sxs-lookup"><span data-stu-id="ff72b-109">How to: Get Information About Files, Folders, and Drives</span></span>](./how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="ff72b-110">Демонстрирует, как получить сведения о файлах, папках и дисках, например время создания и размер.</span><span class="sxs-lookup"><span data-stu-id="ff72b-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="ff72b-111">Практическое руководство. Создание файла или папки</span><span class="sxs-lookup"><span data-stu-id="ff72b-111">How to: Create a File or Folder</span></span>](./how-to-create-a-file-or-folder.md)|<span data-ttu-id="ff72b-112">Демонстрирует создание нового файла и новой папки.</span><span class="sxs-lookup"><span data-stu-id="ff72b-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="ff72b-113">Практическое руководство. Руководство по программированию в C#. Копирование, удаление и перемещение файлов и папок</span><span class="sxs-lookup"><span data-stu-id="ff72b-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="ff72b-114">Демонстрирует копирование, удаление и перемещение файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="ff72b-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="ff72b-115">Практическое руководство. Отображение диалогового окна "Ход выполнения" для операций с файлами</span><span class="sxs-lookup"><span data-stu-id="ff72b-115">How to: Provide a Progress Dialog Box for File Operations</span></span>](./how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="ff72b-116">Объясняет, как отобразить стандартное диалоговое окно Windows для хода выполнения определенных файловых операций.</span><span class="sxs-lookup"><span data-stu-id="ff72b-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="ff72b-117">Практическое руководство. Запись в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="ff72b-117">How to: Write to a Text File</span></span>](./how-to-write-to-a-text-file.md)|<span data-ttu-id="ff72b-118">Демонстрирует запись в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="ff72b-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="ff72b-119">Практическое руководство. Чтение из текстового файла</span><span class="sxs-lookup"><span data-stu-id="ff72b-119">How to: Read From a Text File</span></span>](./how-to-read-from-a-text-file.md)|<span data-ttu-id="ff72b-120">Демонстрирует чтение из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="ff72b-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="ff72b-121">Практическое руководство. Построчное чтение текстового файла</span><span class="sxs-lookup"><span data-stu-id="ff72b-121">How to: Read a Text File One Line at a Time</span></span>](./how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="ff72b-122">Демонстрирует извлечение текста из файла по одной строке.</span><span class="sxs-lookup"><span data-stu-id="ff72b-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="ff72b-123">Практическое руководство. Создание раздела в реестре</span><span class="sxs-lookup"><span data-stu-id="ff72b-123">How to: Create a Key In the Registry</span></span>](./how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="ff72b-124">Демонстрирует запись раздела в системный реестр.</span><span class="sxs-lookup"><span data-stu-id="ff72b-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="ff72b-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ff72b-125">Related Sections</span></span>  
 [<span data-ttu-id="ff72b-126">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="ff72b-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="ff72b-127">Практическое руководство. Руководство по программированию в C#. Копирование, удаление и перемещение файлов и папок</span><span class="sxs-lookup"><span data-stu-id="ff72b-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="ff72b-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ff72b-128">C# Programming Guide</span></span>](../index.md)  
  
 [<span data-ttu-id="ff72b-129">Файлы, папки и диски</span><span class="sxs-lookup"><span data-stu-id="ff72b-129">Files, Folders and Drives</span></span>](./index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
