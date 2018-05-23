---
title: Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 5debb2cbfa5ada45447e280169b9fe66d1a15a53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="e5c2e-102">Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="e5c2e-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="e5c2e-103">В следующих примерах показано, как синхронно копировать, перемещать и удалять файлы и папки с помощью классов <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, и <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> из пространства имен <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e5c2e-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="e5c2e-104">В этих примерах не используется индикатор хода выполнения или какой-либо иной пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e5c2e-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="e5c2e-105">Если нужно использовать стандартное диалоговое окна хода выполнения, см. раздел [Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e5c2e-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="e5c2e-106">Используйте <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> для предоставления событий, которые позволяют вычислять ход выполнения при работе с несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="e5c2e-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="e5c2e-107">Другим подходом является использование вызова неуправляемого кода для вызова в Windows Shell методов, относящихся к обработке файлов.</span><span class="sxs-lookup"><span data-stu-id="e5c2e-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="e5c2e-108">Сведения о способах асинхронного выполнения таких операций над файлами см. в разделе [Асинхронный файловый ввод-вывод](https://msdn.microsoft.com/library/kztecsys).</span><span class="sxs-lookup"><span data-stu-id="e5c2e-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5c2e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e5c2e-109">Example</span></span>  
 <span data-ttu-id="e5c2e-110">В следующем примере показано, как копировать файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="e5c2e-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="e5c2e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="e5c2e-111">Example</span></span>  
 <span data-ttu-id="e5c2e-112">В следующем примере показано, как перемещать файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="e5c2e-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="e5c2e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="e5c2e-113">Example</span></span>  
 <span data-ttu-id="e5c2e-114">В следующем примере показано, как удалять файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="e5c2e-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e5c2e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e5c2e-115">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="e5c2e-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e5c2e-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e5c2e-117">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e5c2e-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)  
 [<span data-ttu-id="e5c2e-118">Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами</span><span class="sxs-lookup"><span data-stu-id="e5c2e-118">How to: Provide a Progress Dialog Box for File Operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
 [<span data-ttu-id="e5c2e-119">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="e5c2e-119">File and Stream I/O</span></span>](https://msdn.microsoft.com/library/k3352a4t)  
 [<span data-ttu-id="e5c2e-120">Распространенные задачи ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="e5c2e-120">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)
