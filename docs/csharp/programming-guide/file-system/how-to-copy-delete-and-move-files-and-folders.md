---
title: Руководство по программированию на C#. Как копировать, удалять, перемещать файлы и папки
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 662f0ab3b9e69aa8bfb0085f42f577b850029e4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712277"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="bacfa-102">Руководство по программированию на C#. Копирование, удаление, перемещение файлов и папок</span><span class="sxs-lookup"><span data-stu-id="bacfa-102">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>
<span data-ttu-id="bacfa-103">В следующих примерах показано, как синхронно копировать, перемещать и удалять файлы и папки с помощью классов <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, и <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> из пространства имен <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bacfa-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="bacfa-104">В этих примерах не используется индикатор хода выполнения или какой-либо иной пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bacfa-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="bacfa-105">Если нужно использовать стандартное диалоговое окна хода выполнения, см. практическое руководство [Отображение диалогового окна хода выполнения для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="bacfa-105">If you want to provide a standard progress dialog box, see [How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="bacfa-106">Используйте <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> для предоставления событий, которые позволяют вычислять ход выполнения при работе с несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="bacfa-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="bacfa-107">Другим подходом является использование вызова неуправляемого кода для вызова в Windows Shell методов, относящихся к обработке файлов.</span><span class="sxs-lookup"><span data-stu-id="bacfa-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="bacfa-108">Сведения о способах асинхронного выполнения таких операций над файлами см. в разделе [Асинхронный файловый ввод-вывод](../../../standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="bacfa-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bacfa-109">Пример</span><span class="sxs-lookup"><span data-stu-id="bacfa-109">Example</span></span>  
 <span data-ttu-id="bacfa-110">В следующем примере показано, как копировать файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="bacfa-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="bacfa-111">Пример</span><span class="sxs-lookup"><span data-stu-id="bacfa-111">Example</span></span>  
 <span data-ttu-id="bacfa-112">В следующем примере показано, как перемещать файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="bacfa-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="bacfa-113">Пример</span><span class="sxs-lookup"><span data-stu-id="bacfa-113">Example</span></span>  
 <span data-ttu-id="bacfa-114">В следующем примере показано, как удалять файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="bacfa-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="bacfa-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bacfa-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="bacfa-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bacfa-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bacfa-117">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="bacfa-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="bacfa-118">Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами</span><span class="sxs-lookup"><span data-stu-id="bacfa-118">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="bacfa-119">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="bacfa-119">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="bacfa-120">Распространенные задачи ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="bacfa-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
