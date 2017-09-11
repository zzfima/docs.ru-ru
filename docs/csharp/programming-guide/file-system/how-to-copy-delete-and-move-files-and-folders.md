---
title: "Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
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
ms.openlocfilehash: a4cfec46e0af0056a0de20a1ed83a370cd010055
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="5358b-102">Практическое руководство. Копирование, удаление и перемещение файлов и папок (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="5358b-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="5358b-103">В следующих примерах показано, как синхронно копировать, перемещать и удалять файлы и папки с помощью классов <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName>, и <xref:System.IO.DirectoryInfo?displayProperty=fullName> из пространства имен <xref:System.IO?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5358b-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName>, and <xref:System.IO.DirectoryInfo?displayProperty=fullName> classes from the <xref:System.IO?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="5358b-104">В этих примерах не используется индикатор хода выполнения или какой-либо иной пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5358b-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="5358b-105">Если нужно использовать стандартное диалоговое окна хода выполнения, см. раздел [Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5358b-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="5358b-106">Используйте <xref:System.IO.FileSystemWatcher?displayProperty=fullName> для предоставления событий, которые позволяют вычислять ход выполнения при работе с несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="5358b-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=fullName> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="5358b-107">Другим подходом является использование вызова неуправляемого кода для вызова в Windows Shell методов, относящихся к обработке файлов.</span><span class="sxs-lookup"><span data-stu-id="5358b-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="5358b-108">Сведения о способах асинхронного выполнения таких операций над файлами см. в разделе [Асинхронный файловый ввод-вывод](https://msdn.microsoft.com/library/kztecsys).</span><span class="sxs-lookup"><span data-stu-id="5358b-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5358b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5358b-109">Example</span></span>  
 <span data-ttu-id="5358b-110">В следующем примере показано, как копировать файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="5358b-110">The following example shows how to copy files and directories.</span></span>  
  
 <span data-ttu-id="5358b-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5358b-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5358b-112">Пример</span><span class="sxs-lookup"><span data-stu-id="5358b-112">Example</span></span>  
 <span data-ttu-id="5358b-113">В следующем примере показано, как перемещать файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="5358b-113">The following example shows how to move files and directories.</span></span>  
  
 <span data-ttu-id="5358b-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5358b-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5358b-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5358b-115">Example</span></span>  
 <span data-ttu-id="5358b-116">В следующем примере показано, как удалять файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="5358b-116">The following example shows how to delete files and directories.</span></span>  
  
 <span data-ttu-id="5358b-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5358b-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5358b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5358b-118">See Also</span></span>  
 <span data-ttu-id="5358b-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5358b-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="5358b-120">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5358b-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5358b-121">[Файловая система и реестр (руководство по программированию на C#)](index.md) </span><span class="sxs-lookup"><span data-stu-id="5358b-121">[File System and the Registry (C# Programming Guide)](index.md) </span></span>  
 <span data-ttu-id="5358b-122">[Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span><span class="sxs-lookup"><span data-stu-id="5358b-122">[How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span></span>  
 <span data-ttu-id="5358b-123">[Файловый и потоковый ввод-вывод](https://msdn.microsoft.com/library/k3352a4t) </span><span class="sxs-lookup"><span data-stu-id="5358b-123">[File and Stream I/O](https://msdn.microsoft.com/library/k3352a4t) </span></span>  
 [<span data-ttu-id="5358b-124">Распространенные задачи ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="5358b-124">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)

