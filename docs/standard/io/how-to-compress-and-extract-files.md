---
title: Как выполнить Сжатие и извлечение файлов
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
ms.openlocfilehash: c35bf549dc4dcd5e12e3580c2357b64dcc42905b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650945"
---
# <a name="how-to-compress-and-extract-files"></a>Как выполнить Сжатие и извлечение файлов

Пространство имен <xref:System.IO.Compression> предоставляет следующие типы для сжатия и распаковки файлов и потоков. Вы также можете использовать эти типы для чтения и изменения содержимого сжатого файла:

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

В примерах ниже показано несколько функций для работы со сжатыми файлами.

## <a name="example-1---create-and-extract-a-zip-file"></a>Пример 1. Создание и извлечение ZIP-файла

В следующем примере показано, как создавать и извлекать сжатый файл с расширением .zip с помощью класса <xref:System.IO.Compression.ZipFile>. Он сжимает содержимое папки в новый ZIP-файл и затем извлекает это содержимое в новую папку. Чтобы использовать класс <xref:System.IO.Compression.ZipFile>, укажите в проекте ссылку на сборку `System.IO.Compression.FileSystem`.

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a>Пример 2. Извлечение файлов с определенными расширениями

В этом примере показано, как просмотреть в цикле содержимое существующего ZIP-файла и извлечь из него файлы с расширением .txt. Он использует класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP-файлу, а также класс <xref:System.IO.Compression.ZipArchiveEntry> для проверки элементов в сжатом файле. Он использует метод расширения (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) для объекта <xref:System.IO.Compression.ZipArchiveEntry>. Метод расширения доступен в классе <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>. Чтобы использовать класс <xref:System.IO.Compression.ZipFileExtensions>, укажите в проекте ссылку на сборку `System.IO.Compression.FileSystem`.

> [!IMPORTANT]
> При распаковке файлов важно убедиться в отсутствии вредоносных путей, которые могут находиться за пределами каталога, в который вы извлекаете файлы. Такая атака известна как обход путей.

В следующем примере показано, как правильно проверить наличие вредоносных путей и безопасно извлечь файлы:

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a>Пример 3. Добавление нового файла в существующий ZIP-файл

В следующем примере используется класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP-файлу и добавления в него нового файла. Новый файл сжимается при добавлении в существующий ZIP-файл.

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a>Пример 4. Сжатие и распаковка каталога с GZ-файлами

Также вы можете использовать классы <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> для сжатия и распаковки данных. Они применяют тот же алгоритм сжатия. Сжатые объекты <xref:System.IO.Compression.GZipStream>, которые записаны в файл с расширением .gz, можно распаковать с помощью методов, предоставляемых <xref:System.IO.Compression.GZipStream>, и многих других распространенных средств. В следующем примере показано, как использовать класс <xref:System.IO.Compression.GZipStream> для сжатия и распаковки каталога файлов.

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a>См. также

- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>
- [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
