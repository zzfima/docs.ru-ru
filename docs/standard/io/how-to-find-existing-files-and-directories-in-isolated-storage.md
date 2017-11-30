---
title: "Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище"
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
- cpp
helpviewer_keywords:
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 656c390358b6f6a671cf3ef11ea7be75f897d21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a><span data-ttu-id="aded9-102">Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище</span><span class="sxs-lookup"><span data-stu-id="aded9-102">How to: Find Existing Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="aded9-103">Поиск каталогов в изолированном хранилище, используйте <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="aded9-103">To search for a directory in isolated storage, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="aded9-104">Этот метод принимает строку, представляющую шаблон поиска.</span><span class="sxs-lookup"><span data-stu-id="aded9-104">This method takes a string that represents a search pattern.</span></span> <span data-ttu-id="aded9-105">Можно использовать одного знака (?) и нескольких символов (*) подстановочные знаки в шаблон поиска, но символы-шаблоны, должен быть указан в последней части имени.</span><span class="sxs-lookup"><span data-stu-id="aded9-105">You can use both single-character (?) and multi-character (*) wildcard characters in the search pattern, but the wildcard characters must appear in the final portion of the name.</span></span> <span data-ttu-id="aded9-106">Например `directory1/*ect*` имеет допустимую строку поиска, но `*ect*/directory2` не является.</span><span class="sxs-lookup"><span data-stu-id="aded9-106">For example, `directory1/*ect*` is a valid search string, but `*ect*/directory2` is not.</span></span>  
  
 <span data-ttu-id="aded9-107">Чтобы найти файл, используйте <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="aded9-107">To search for a file, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="aded9-108">Ограничения проверки подстановочные знаки в строке поиска, к которым применяется <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> также применяется к <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span><span class="sxs-lookup"><span data-stu-id="aded9-108">The restriction for wildcard characters in search strings that applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> also applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span></span>  
  
 <span data-ttu-id="aded9-109">Ни один из этих методов является рекурсивной. <xref:System.IO.IsolatedStorage.IsolatedStorageFile> класс не предоставляет методы для перечисления всех каталогов или файлов в хранилище.</span><span class="sxs-lookup"><span data-stu-id="aded9-109">Neither of these methods is recursive; the <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class does not supply any methods for listing all directories or files in your store.</span></span> <span data-ttu-id="aded9-110">Тем не менее в следующем примере кода показаны методы рекурсивной.</span><span class="sxs-lookup"><span data-stu-id="aded9-110">However, recursive methods are shown in the following code example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aded9-111">Пример</span><span class="sxs-lookup"><span data-stu-id="aded9-111">Example</span></span>  
 <span data-ttu-id="aded9-112">В следующем примере кода показано создание файлов и каталогов в изолированном хранилище.</span><span class="sxs-lookup"><span data-stu-id="aded9-112">The following code example illustrates how to create files and directories in an isolated store.</span></span> <span data-ttu-id="aded9-113">Во-первых, извлекается и помещен в хранилище, — изолированное по пользователю, домену и сборке `isoStore` переменной.</span><span class="sxs-lookup"><span data-stu-id="aded9-113">First, a store that is isolated for user, domain, and assembly is retrieved and placed in the `isoStore` variable.</span></span> <span data-ttu-id="aded9-114"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> Метод используется для настройки нескольких разных каталогах и <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> конструктор создает некоторые файлы в этих каталогах.</span><span class="sxs-lookup"><span data-stu-id="aded9-114">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> method is used to set up a few different directories, and the <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> constructor creates some files in these directories.</span></span> <span data-ttu-id="aded9-115">Затем код выполняет цикл по результатам `GetAllDirectories` метод.</span><span class="sxs-lookup"><span data-stu-id="aded9-115">The code then loops through the results of the `GetAllDirectories` method.</span></span> <span data-ttu-id="aded9-116">Этот метод использует <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> для поиска всех имен каталогов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="aded9-116">This method uses <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> to find all the directory names in the current directory.</span></span> <span data-ttu-id="aded9-117">Эти имена хранятся в виде массива, а затем `GetAllDirectories` вызывает себя, передавая в каждом каталоге, он найден.</span><span class="sxs-lookup"><span data-stu-id="aded9-117">These names are stored in an array, and then `GetAllDirectories` calls itself, passing in each directory it has found.</span></span> <span data-ttu-id="aded9-118">В результате всех имен каталогов, возвращаются в виде массива.</span><span class="sxs-lookup"><span data-stu-id="aded9-118">As a result, all the directory names are returned in an array.</span></span> <span data-ttu-id="aded9-119">Затем код вызывает `GetAllFiles` метод.</span><span class="sxs-lookup"><span data-stu-id="aded9-119">Next, the code calls the `GetAllFiles` method.</span></span> <span data-ttu-id="aded9-120">Этот метод вызывает метод `GetAllDirectories` для поиска всех имен каталогов, а затем проверяет каждый каталог для файлов с помощью <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="aded9-120">This method calls `GetAllDirectories` to find out the names of all the directories, and then it checks each directory for files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> method.</span></span> <span data-ttu-id="aded9-121">Результат возвращается в виде массива для вывода.</span><span class="sxs-lookup"><span data-stu-id="aded9-121">The result is returned in an array for display.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="aded9-122">См. также</span><span class="sxs-lookup"><span data-stu-id="aded9-122">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="aded9-123">Изолированное хранилище</span><span class="sxs-lookup"><span data-stu-id="aded9-123">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
