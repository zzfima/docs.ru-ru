---
title: Практическое руководство. Сжатие и извлечение файлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3e535e13fe91e1a5cb9c868428f5edbb9eac03f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="349a2-102">Практическое руководство. Сжатие и извлечение файлов</span><span class="sxs-lookup"><span data-stu-id="349a2-102">How to: Compress and Extract Files</span></span>
<span data-ttu-id="349a2-103">Пространство имен <xref:System.IO.Compression> предоставляет следующие типы для сжатия и распаковки файлов и потоков.</span><span class="sxs-lookup"><span data-stu-id="349a2-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="349a2-104">Вы также можете использовать эти типы для чтения и изменения содержимого сжатого файла:</span><span class="sxs-lookup"><span data-stu-id="349a2-104">You can also use these types to read and modify the contents of a compressed file:</span></span>  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 <span data-ttu-id="349a2-105">В примерах ниже показано несколько функций для работы со сжатыми файлами.</span><span class="sxs-lookup"><span data-stu-id="349a2-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="349a2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="349a2-106">Example</span></span>  
 <span data-ttu-id="349a2-107">В этом примере показано, как создавать и извлекать сжатый файл с расширением .zip с помощью класса <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="349a2-107">This example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="349a2-108">Он сжимает содержимое папки в новый ZIP-файл и затем извлекает это содержимое в новую папку.</span><span class="sxs-lookup"><span data-stu-id="349a2-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="349a2-109">Чтобы использовать класс <xref:System.IO.Compression.ZipFile>, укажите в проекте ссылку на сборку `System.IO.Compression.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="349a2-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="349a2-110">Пример</span><span class="sxs-lookup"><span data-stu-id="349a2-110">Example</span></span>  
 <span data-ttu-id="349a2-111">В этом примере показано, как просмотреть в цикле содержимое существующего ZIP-файла и извлечь из него файлы с расширением .txt.</span><span class="sxs-lookup"><span data-stu-id="349a2-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="349a2-112">Он использует класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP-файлу, а также класс <xref:System.IO.Compression.ZipArchiveEntry> для проверки элементов в сжатом файле.</span><span class="sxs-lookup"><span data-stu-id="349a2-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="349a2-113">Он использует метод расширения (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) для объекта <xref:System.IO.Compression.ZipArchiveEntry>.</span><span class="sxs-lookup"><span data-stu-id="349a2-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="349a2-114">Метод расширения доступен в классе <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="349a2-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="349a2-115">Чтобы использовать класс <xref:System.IO.Compression.ZipFileExtensions>, укажите в проекте ссылку на сборку `System.IO.Compression.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="349a2-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="349a2-116">Пример</span><span class="sxs-lookup"><span data-stu-id="349a2-116">Example</span></span>  
 <span data-ttu-id="349a2-117">В этом примере используется класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP-файлу и добавляется в него новый файл.</span><span class="sxs-lookup"><span data-stu-id="349a2-117">The next example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="349a2-118">Новый файл сжимается при добавлении в существующий ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="349a2-118">The new file gets compressed when you add it to the existing .zip file.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="349a2-119">Пример</span><span class="sxs-lookup"><span data-stu-id="349a2-119">Example</span></span>  
 <span data-ttu-id="349a2-120">Также вы можете использовать классы <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> для сжатия и распаковки данных.</span><span class="sxs-lookup"><span data-stu-id="349a2-120">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="349a2-121">Они применяют тот же алгоритм сжатия.</span><span class="sxs-lookup"><span data-stu-id="349a2-121">They use the same compression algorithm.</span></span> <span data-ttu-id="349a2-122">Сжатые объекты <xref:System.IO.Compression.GZipStream>, которые записаны в файл с расширением .gz, можно распаковать с помощью методов, предоставляемых <xref:System.IO.Compression.GZipStream>, и многих других распространенных средств.</span><span class="sxs-lookup"><span data-stu-id="349a2-122">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="349a2-123">В этом примере показано, как использовать класс <xref:System.IO.Compression.GZipStream> для сжатия и распаковки каталога файлов.</span><span class="sxs-lookup"><span data-stu-id="349a2-123">This example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class.</span></span>  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="349a2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="349a2-124">See Also</span></span>  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [<span data-ttu-id="349a2-125">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="349a2-125">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
