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
# <a name="how-to-compress-and-extract-files"></a>Практическое руководство. Сжатие и извлечение файлов
Пространство имен <xref:System.IO.Compression> предоставляет следующие типы для сжатия и распаковки файлов и потоков. Вы также можете использовать эти типы для чтения и изменения содержимого сжатого файла:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 В примерах ниже показано несколько функций для работы со сжатыми файлами.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как создавать и извлекать сжатый файл с расширением .zip с помощью класса <xref:System.IO.Compression.ZipFile>. Он сжимает содержимое папки в новый ZIP-файл и затем извлекает это содержимое в новую папку. Чтобы использовать класс <xref:System.IO.Compression.ZipFile>, укажите в проекте ссылку на сборку `System.IO.Compression.FileSystem`.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a>Пример  
 В этом примере показано, как просмотреть в цикле содержимое существующего ZIP-файла и извлечь из него файлы с расширением .txt. Он использует класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP-файлу, а также класс <xref:System.IO.Compression.ZipArchiveEntry> для проверки элементов в сжатом файле. Он использует метод расширения (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) для объекта <xref:System.IO.Compression.ZipArchiveEntry>. Метод расширения доступен в классе <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>. Чтобы использовать класс <xref:System.IO.Compression.ZipFileExtensions>, укажите в проекте ссылку на сборку `System.IO.Compression.FileSystem`.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a>Пример  
 В этом примере используется класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP-файлу и добавляется в него новый файл. Новый файл сжимается при добавлении в существующий ZIP-файл.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a>Пример  
 Также вы можете использовать классы <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> для сжатия и распаковки данных. Они применяют тот же алгоритм сжатия. Сжатые объекты <xref:System.IO.Compression.GZipStream>, которые записаны в файл с расширением .gz, можно распаковать с помощью методов, предоставляемых <xref:System.IO.Compression.GZipStream>, и многих других распространенных средств. В этом примере показано, как использовать класс <xref:System.IO.Compression.GZipStream> для сжатия и распаковки каталога файлов.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
