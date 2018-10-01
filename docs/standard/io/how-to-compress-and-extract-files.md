---
title: Практическое руководство. Сжатие и извлечение файлов
ms.date: 06/06/2018
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
ms.openlocfilehash: 669936d15cfe1ea125ed36ffdfcfd093b6aacbe1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47424432"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="84185-102">Практическое руководство. Сжатие и извлечение файлов</span><span class="sxs-lookup"><span data-stu-id="84185-102">How to: Compress and extract files</span></span>

<span data-ttu-id="84185-103">Пространство имен <xref:System.IO.Compression> предоставляет следующие типы для сжатия и распаковки файлов и потоков.</span><span class="sxs-lookup"><span data-stu-id="84185-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="84185-104">Вы также можете использовать эти типы для чтения и изменения содержимого сжатого файла:</span><span class="sxs-lookup"><span data-stu-id="84185-104">You can also use these types to read and modify the contents of a compressed file:</span></span>

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="84185-105">В примерах ниже показано несколько функций для работы со сжатыми файлами.</span><span class="sxs-lookup"><span data-stu-id="84185-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>

## <a name="example-1---create-and-extract-a-zip-file"></a><span data-ttu-id="84185-106">Пример 1. Создание и извлечение ZIP-файла</span><span class="sxs-lookup"><span data-stu-id="84185-106">Example 1 - Create and extract a .zip file</span></span>

<span data-ttu-id="84185-107">В следующем примере показано, как создавать и извлекать сжатый файл с расширением .zip с помощью класса <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="84185-107">The following example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="84185-108">Он сжимает содержимое папки в новый ZIP-файл и затем извлекает это содержимое в новую папку.</span><span class="sxs-lookup"><span data-stu-id="84185-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="84185-109">Чтобы использовать класс <xref:System.IO.Compression.ZipFile>, укажите в проекте ссылку на сборку `System.IO.Compression.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="84185-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a><span data-ttu-id="84185-110">Пример 2. Извлечение файлов с определенными расширениями</span><span class="sxs-lookup"><span data-stu-id="84185-110">Example 2 - Extract specific file extensions</span></span>

<span data-ttu-id="84185-111">В этом примере показано, как просмотреть в цикле содержимое существующего ZIP-файла и извлечь из него файлы с расширением .txt.</span><span class="sxs-lookup"><span data-stu-id="84185-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="84185-112">Он использует класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP-файлу, а также класс <xref:System.IO.Compression.ZipArchiveEntry> для проверки элементов в сжатом файле.</span><span class="sxs-lookup"><span data-stu-id="84185-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="84185-113">Он использует метод расширения (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) для объекта <xref:System.IO.Compression.ZipArchiveEntry>.</span><span class="sxs-lookup"><span data-stu-id="84185-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="84185-114">Метод расширения доступен в классе <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84185-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="84185-115">Чтобы использовать класс <xref:System.IO.Compression.ZipFileExtensions>, укажите в проекте ссылку на сборку `System.IO.Compression.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="84185-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84185-116">При распаковке файлов важно убедиться в отсутствии вредоносных путей, которые могут находиться за пределами каталога, в который вы извлекаете файлы.</span><span class="sxs-lookup"><span data-stu-id="84185-116">When unzipping files, you must look for malicious file paths which can escape out of the directory where you want to unzip into.</span></span> <span data-ttu-id="84185-117">Такая атака известна как обход путей.</span><span class="sxs-lookup"><span data-stu-id="84185-117">This is known as a path traversal attack.</span></span>

<span data-ttu-id="84185-118">В следующем примере показано, как правильно проверить наличие вредоносных путей и безопасно извлечь файлы:</span><span class="sxs-lookup"><span data-stu-id="84185-118">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip:</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a><span data-ttu-id="84185-119">Пример 3. Добавление нового файла в существующий ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="84185-119">Example 3 - Add a new file to an existing .zip file</span></span>

<span data-ttu-id="84185-120">В следующем примере используется класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP-файлу и добавления в него нового файла.</span><span class="sxs-lookup"><span data-stu-id="84185-120">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="84185-121">Новый файл сжимается при добавлении в существующий ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="84185-121">The new file gets compressed when you add it to the existing .zip file.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a><span data-ttu-id="84185-122">Пример 4. Сжатие и распаковка каталога с GZ-файлами</span><span class="sxs-lookup"><span data-stu-id="84185-122">Example 4 - Compress and decompress a directory of .gz files</span></span>

<span data-ttu-id="84185-123">Также вы можете использовать классы <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> для сжатия и распаковки данных.</span><span class="sxs-lookup"><span data-stu-id="84185-123">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="84185-124">Они применяют тот же алгоритм сжатия.</span><span class="sxs-lookup"><span data-stu-id="84185-124">They use the same compression algorithm.</span></span> <span data-ttu-id="84185-125">Сжатые объекты <xref:System.IO.Compression.GZipStream>, которые записаны в файл с расширением .gz, можно распаковать с помощью методов, предоставляемых <xref:System.IO.Compression.GZipStream>, и многих других распространенных средств.</span><span class="sxs-lookup"><span data-stu-id="84185-125">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="84185-126">В следующем примере показано, как использовать класс <xref:System.IO.Compression.GZipStream> для сжатия и распаковки каталога файлов.</span><span class="sxs-lookup"><span data-stu-id="84185-126">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="84185-127">См. также</span><span class="sxs-lookup"><span data-stu-id="84185-127">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="84185-128">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="84185-128">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
