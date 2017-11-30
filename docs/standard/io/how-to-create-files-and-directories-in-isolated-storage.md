---
title: "Практическое руководство. Создание файлов и каталогов в изолированном хранилище"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="ea998-102">Практическое руководство. Создание файлов и каталогов в изолированном хранилище</span><span class="sxs-lookup"><span data-stu-id="ea998-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="ea998-103">После получения изолированного хранилища, можно создать файлы и папки для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="ea998-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="ea998-104">Внутри хранилища имена файлов и каталогов указываются относительно корневого каталога виртуальной файловой системы.</span><span class="sxs-lookup"><span data-stu-id="ea998-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="ea998-105">Чтобы создать каталог, используйте <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ea998-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="ea998-106">Если указать подкаталог каталога, который не существует, создаются обоих служб каталогов.</span><span class="sxs-lookup"><span data-stu-id="ea998-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="ea998-107">Если задан каталог, который уже существует, метод возвращается без создания каталога и исключение не возникает.</span><span class="sxs-lookup"><span data-stu-id="ea998-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="ea998-108">Тем не менее, если указать имя каталога, которое содержит недопустимые знаки <xref:System.IO.IsolatedStorage.IsolatedStorageException> исключения.</span><span class="sxs-lookup"><span data-stu-id="ea998-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="ea998-109">Для создания файла используется метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea998-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ea998-110">В операционной системе Windows, изолированное хранилище файлов и каталогов именах не учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="ea998-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="ea998-111">То есть если создается файл с именем `ThisFile.txt`и создайте другой файл с именем `THISFILE.TXT`, создается только один файл.</span><span class="sxs-lookup"><span data-stu-id="ea998-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="ea998-112">Имя файла сохраняется исходный регистр в целях отображения.</span><span class="sxs-lookup"><span data-stu-id="ea998-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea998-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ea998-113">Example</span></span>  
 <span data-ttu-id="ea998-114">В следующем примере кода показано создание файлов и каталогов в изолированном хранилище.</span><span class="sxs-lookup"><span data-stu-id="ea998-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ea998-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ea998-115">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [<span data-ttu-id="ea998-116">Изолированное хранилище</span><span class="sxs-lookup"><span data-stu-id="ea998-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
