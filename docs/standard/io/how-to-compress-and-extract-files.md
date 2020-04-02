---
title: Практическое руководство. Сжатие и извлечение файлов
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
ms.openlocfilehash: 10f990401830bc5f77176f4e586f15f7dd75ff14
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248021"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="61639-102">Практическое руководство. Сжатие и извлечение файлов</span><span class="sxs-lookup"><span data-stu-id="61639-102">How to: Compress and extract files</span></span>

<span data-ttu-id="61639-103">Пространство имен <xref:System.IO.Compression> предоставляет следующие типы для сжатия и распаковки файлов и потоков.</span><span class="sxs-lookup"><span data-stu-id="61639-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="61639-104">Вы также можете использовать эти типы для чтения и изменения содержимого сжатого файла.</span><span class="sxs-lookup"><span data-stu-id="61639-104">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="61639-105">В примерах ниже показано несколько операций для работы со сжатыми файлами.</span><span class="sxs-lookup"><span data-stu-id="61639-105">The following examples show some of the operations you can perform with compressed files.</span></span> <span data-ttu-id="61639-106">Для этих примеров требуется добавить в проект следующие пакеты NuGet:</span><span class="sxs-lookup"><span data-stu-id="61639-106">These examples require the following NuGet packages to be added to your project:</span></span>

- <span data-ttu-id="61639-107">[System.IO.Compression](https://www.nuget.org/packages/System.IO.Compression);</span><span class="sxs-lookup"><span data-stu-id="61639-107">[System.IO.Compression](https://www.nuget.org/packages/System.IO.Compression)</span></span>
- <span data-ttu-id="61639-108">[System.IO.Compression.ZipFile](https://www.nuget.org/packages/System.IO.Compression.ZipFile).</span><span class="sxs-lookup"><span data-stu-id="61639-108">[System.IO.Compression.ZipFile](https://www.nuget.org/packages/System.IO.Compression.ZipFile)</span></span>

<span data-ttu-id="61639-109">Если вы используете .NET Framework, добавьте в проект ссылки на эти две библиотеки:</span><span class="sxs-lookup"><span data-stu-id="61639-109">If you're using .NET Framework, add references to these two libraries to your project:</span></span>

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="61639-110">Пример 1: Создание и извлечение ZIP-файла</span><span class="sxs-lookup"><span data-stu-id="61639-110">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="61639-111">В следующем примере показано, как создавать и извлекать сжатый файл *.zip* с помощью класса <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="61639-111">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="61639-112">Он сжимает содержимое папки в новый *ZIP*-файл и затем извлекает его в новую папку.</span><span class="sxs-lookup"><span data-stu-id="61639-112">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="61639-113">Чтобы запустить пример, создайте папку *start* в папке программы и заполните ее файлами для сжатия.</span><span class="sxs-lookup"><span data-stu-id="61639-113">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="61639-114">Пример 2: Извлечение файлов с определенными расширениями</span><span class="sxs-lookup"><span data-stu-id="61639-114">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="61639-115">В этом примере выполняется итерация по содержимому существующего *ZIP*-файла и извлекаются файлы с расширением *.txt*.</span><span class="sxs-lookup"><span data-stu-id="61639-115">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="61639-116">Здесь используется класс <xref:System.IO.Compression.ZipArchive> для доступа к ZIP-файлу и класс <xref:System.IO.Compression.ZipArchiveEntry> для проверки отдельных элементов.</span><span class="sxs-lookup"><span data-stu-id="61639-116">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="61639-117">Метод расширения <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> для объекта <xref:System.IO.Compression.ZipArchiveEntry> доступен в классе <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="61639-117">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="61639-118">Чтобы запустить пример, поместите *ZIP*-файл с именем *result.zip* в папку программы.</span><span class="sxs-lookup"><span data-stu-id="61639-118">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="61639-119">По запросу укажите имя папки для извлечения.</span><span class="sxs-lookup"><span data-stu-id="61639-119">When prompted, provide a folder name to extract to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61639-120">При распаковке файлов важно убедиться в отсутствии вредоносных путей, которые могут вести за пределы каталога, в который вы извлекаете файлы.</span><span class="sxs-lookup"><span data-stu-id="61639-120">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="61639-121">Такая атака известна как обход путей.</span><span class="sxs-lookup"><span data-stu-id="61639-121">This is known as a path traversal attack.</span></span> <span data-ttu-id="61639-122">В следующем примере показано, как правильно проверить наличие вредоносных путей и безопасно извлечь файлы.</span><span class="sxs-lookup"><span data-stu-id="61639-122">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="61639-123">Пример 3. Добавление файла в существующий ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="61639-123">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="61639-124">В следующем примере используется класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему *ZIP*-файлу и добавления в него файла.</span><span class="sxs-lookup"><span data-stu-id="61639-124">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="61639-125">Новый файл сжимается при добавлении в существующий ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="61639-125">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="61639-126">Пример 4. Сжатие и распаковка GZ-файлов</span><span class="sxs-lookup"><span data-stu-id="61639-126">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="61639-127">Также вы можете использовать классы <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> для сжатия и распаковки данных.</span><span class="sxs-lookup"><span data-stu-id="61639-127">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="61639-128">Они применяют тот же алгоритм сжатия.</span><span class="sxs-lookup"><span data-stu-id="61639-128">They use the same compression algorithm.</span></span> <span data-ttu-id="61639-129">Вы можете распаковать объекты <xref:System.IO.Compression.GZipStream>, которые записаны в *GZ*-файл, с помощью многих распространенных средств.</span><span class="sxs-lookup"><span data-stu-id="61639-129">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="61639-130">В следующем примере показано, как использовать класс <xref:System.IO.Compression.GZipStream> для сжатия и распаковки каталога файлов.</span><span class="sxs-lookup"><span data-stu-id="61639-130">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="61639-131">См. также</span><span class="sxs-lookup"><span data-stu-id="61639-131">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="61639-132">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="61639-132">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
