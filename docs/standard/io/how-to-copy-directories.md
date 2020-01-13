---
title: Практическое руководство. Копирование каталогов
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: 223e83a5ff6a73825985ec4e3b6b601fb196fe5e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75707904"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="c53fd-102">Практическое руководство. Копирование каталогов</span><span class="sxs-lookup"><span data-stu-id="c53fd-102">How to: Copy directories</span></span>
<span data-ttu-id="c53fd-103">В этом разделе демонстрируется использование классов ввода-вывода для синхронного копирования содержимого каталога в другое место.</span><span class="sxs-lookup"><span data-stu-id="c53fd-103">This topic demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span> 

<span data-ttu-id="c53fd-104">Пример асинхронного копирования файлов см. в разделе [Асинхронный файловый ввод-вывод](../../../docs/standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="c53fd-104">For an example of asynchronous file copy, see [Asynchronous file I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span> 

<span data-ttu-id="c53fd-105">В этом примере для копирования подкаталогов объекту `copySubDirs` метода `DirectoryCopy` присваивается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="c53fd-105">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="c53fd-106">Метод `DirectoryCopy` выполняет рекурсивное копирование подкаталогов путем вызова самого себя для каждого последующего подкаталога, пока не будет скопировано все.</span><span class="sxs-lookup"><span data-stu-id="c53fd-106">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c53fd-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c53fd-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c53fd-108">См. также</span><span class="sxs-lookup"><span data-stu-id="c53fd-108">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="c53fd-109">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="c53fd-109">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
- [<span data-ttu-id="c53fd-110">Распространенные задачи ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="c53fd-110">Common I/O tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)
- [<span data-ttu-id="c53fd-111">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="c53fd-111">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
