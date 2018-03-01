---
title: "Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 56383873674998fc0d6417a2abf4fa72e498f08f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="0d024-102">Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="0d024-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="0d024-103">В следующих примерах показано, как синхронно копировать, перемещать и удалять файлы и папки с помощью классов <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, и <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> из пространства имен <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0d024-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="0d024-104">В этих примерах не используется индикатор хода выполнения или какой-либо иной пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0d024-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="0d024-105">Если нужно использовать стандартное диалоговое окна хода выполнения, см. раздел [Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0d024-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="0d024-106">Используйте <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> для предоставления событий, которые позволяют вычислять ход выполнения при работе с несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="0d024-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="0d024-107">Другим подходом является использование вызова неуправляемого кода для вызова в Windows Shell методов, относящихся к обработке файлов.</span><span class="sxs-lookup"><span data-stu-id="0d024-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="0d024-108">Сведения о способах асинхронного выполнения таких операций над файлами см. в разделе [Асинхронный файловый ввод-вывод](https://msdn.microsoft.com/library/kztecsys).</span><span class="sxs-lookup"><span data-stu-id="0d024-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d024-109">Пример</span><span class="sxs-lookup"><span data-stu-id="0d024-109">Example</span></span>  
 <span data-ttu-id="0d024-110">В следующем примере показано, как копировать файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="0d024-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="0d024-111">Пример</span><span class="sxs-lookup"><span data-stu-id="0d024-111">Example</span></span>  
 <span data-ttu-id="0d024-112">В следующем примере показано, как перемещать файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="0d024-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="0d024-113">Пример</span><span class="sxs-lookup"><span data-stu-id="0d024-113">Example</span></span>  
 <span data-ttu-id="0d024-114">В следующем примере показано, как удалять файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="0d024-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0d024-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0d024-115">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="0d024-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0d024-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0d024-117">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0d024-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)  
 [<span data-ttu-id="0d024-118">Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами</span><span class="sxs-lookup"><span data-stu-id="0d024-118">How to: Provide a Progress Dialog Box for File Operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
 [<span data-ttu-id="0d024-119">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="0d024-119">File and Stream I/O</span></span>](https://msdn.microsoft.com/library/k3352a4t)  
 [<span data-ttu-id="0d024-120">Распространенные задачи ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="0d024-120">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)
