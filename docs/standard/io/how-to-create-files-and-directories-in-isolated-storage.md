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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cf6295e7d58d03e7b4bf4e0a00cfc509d289e071
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="11e32-102">Практическое руководство. Создание файлов и каталогов в изолированном хранилище</span><span class="sxs-lookup"><span data-stu-id="11e32-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="11e32-103">Получив изолированное хранилище, в нем можно создавать файлы и папки для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="11e32-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="11e32-104">В хранилище имена файлов и каталогов указываются относительно корня виртуальной файловой системы.</span><span class="sxs-lookup"><span data-stu-id="11e32-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="11e32-105">Чтобы создать каталог, используйте экземпляр метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11e32-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="11e32-106">Если вы укажете подкаталог в несуществующем каталоге, создаются оба этих каталога.</span><span class="sxs-lookup"><span data-stu-id="11e32-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="11e32-107">Если вы укажете уже существующий каталог, метод сразу завершает работу, не создавая каталог и не вызывая исключений.</span><span class="sxs-lookup"><span data-stu-id="11e32-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="11e32-108">Но если вы укажете в имени каталога недопустимые символы, создастся исключение <xref:System.IO.IsolatedStorage.IsolatedStorageException>.</span><span class="sxs-lookup"><span data-stu-id="11e32-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="11e32-109">Для создания файла используется метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11e32-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="11e32-110">В изолированных хранилищах на операционной системе Windows регистр в именах файлов и каталогов не учитывается.</span><span class="sxs-lookup"><span data-stu-id="11e32-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="11e32-111">Таким образом, если попытаться создать файл с именем `ThisFile.txt` и еще один файл с именем `THISFILE.TXT`, будет создан только один файл.</span><span class="sxs-lookup"><span data-stu-id="11e32-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="11e32-112">Имя файла отображается в том регистре, который был указан при создании файла.</span><span class="sxs-lookup"><span data-stu-id="11e32-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11e32-113">Пример</span><span class="sxs-lookup"><span data-stu-id="11e32-113">Example</span></span>  
 <span data-ttu-id="11e32-114">В следующем примере кода показано, как создавать файлы и каталоги в изолированном хранилище.</span><span class="sxs-lookup"><span data-stu-id="11e32-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="11e32-115">См. также</span><span class="sxs-lookup"><span data-stu-id="11e32-115">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [<span data-ttu-id="11e32-116">Изолированное хранилище</span><span class="sxs-lookup"><span data-stu-id="11e32-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
