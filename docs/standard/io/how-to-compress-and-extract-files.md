---
title: "Практическое руководство. Сжатие и извлечение файлов"
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
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22a95ce18b602d4e329499c5d36557213e08a8b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="7f1ac-102">Практическое руководство. Сжатие и извлечение файлов</span><span class="sxs-lookup"><span data-stu-id="7f1ac-102">How to: Compress and Extract Files</span></span>
<span data-ttu-id="7f1ac-103"><xref:System.IO.Compression> Пространство имен содержит следующие типы для сжатия и распаковки файлов и потоков.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="7f1ac-104">Можно также использовать эти типы для чтения и изменения содержимого сжатого файла:</span><span class="sxs-lookup"><span data-stu-id="7f1ac-104">You can also use these types to read and modify the contents of a compressed file:</span></span>  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 <span data-ttu-id="7f1ac-105">Некоторые функции, которые можно выполнять при работе с сжатые файлы в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f1ac-106">Пример</span><span class="sxs-lookup"><span data-stu-id="7f1ac-106">Example</span></span>  
 <span data-ttu-id="7f1ac-107">В этом примере показано, как создавать и извлекать сжатый файл с расширением ZIP, используя <xref:System.IO.Compression.ZipFile> класса.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-107">This example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="7f1ac-108">Он сжимает содержимое папки в новый ZIP-файл и затем извлекает это содержимое в новую папку.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="7f1ac-109">Для использования <xref:System.IO.Compression.ZipFile> , должны ссылаться `System.IO.Compression.FileSystem` сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7f1ac-110">Пример</span><span class="sxs-lookup"><span data-stu-id="7f1ac-110">Example</span></span>  
 <span data-ttu-id="7f1ac-111">Следующий пример показано, как возможность просмотра содержимого существующего файла .zip и извлечь файлы, которые имеют расширение txt.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="7f1ac-112">Она использует <xref:System.IO.Compression.ZipArchive> класса для доступа к существующей ZIP-файл и <xref:System.IO.Compression.ZipArchiveEntry> класс отдельные операции в сжатом файле.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="7f1ac-113">Он используется метод расширения (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) для <xref:System.IO.Compression.ZipArchiveEntry> объекта.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="7f1ac-114">Метод расширения доступен в <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="7f1ac-115">Для использования <xref:System.IO.Compression.ZipFileExtensions> , должны ссылаться `System.IO.Compression.FileSystem` сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7f1ac-116">Пример</span><span class="sxs-lookup"><span data-stu-id="7f1ac-116">Example</span></span>  
 <span data-ttu-id="7f1ac-117">В следующем примере используется <xref:System.IO.Compression.ZipArchive> класса для доступа к существующей ZIP-файл и добавляет новый файл для сжатого файла.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-117">The next example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="7f1ac-118">Новый файл получает сжимаются при добавлении существующих ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-118">The new file gets compressed when you add it to the existing .zip file.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7f1ac-119">Пример</span><span class="sxs-lookup"><span data-stu-id="7f1ac-119">Example</span></span>  
 <span data-ttu-id="7f1ac-120">Можно также использовать <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> классы для сжатия и распаковки данных.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-120">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="7f1ac-121">Они используют один и тот же алгоритм сжатия.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-121">They use the same compression algorithm.</span></span> <span data-ttu-id="7f1ac-122">Сжатые <xref:System.IO.Compression.GZipStream> объектов, которые записаны в файл с расширением .gz могут быть извлечены с помощью многих распространенных средств Помимо методов, предоставляемых <xref:System.IO.Compression.GZipStream>.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-122">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="7f1ac-123">В этом примере показано, как для сжатия и распаковки каталог файлов с помощью <xref:System.IO.Compression.GZipStream> класса.</span><span class="sxs-lookup"><span data-stu-id="7f1ac-123">This example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class.</span></span>  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7f1ac-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7f1ac-124">See Also</span></span>  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [<span data-ttu-id="7f1ac-125">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="7f1ac-125">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
