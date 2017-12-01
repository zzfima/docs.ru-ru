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
# <a name="how-to-compress-and-extract-files"></a>Практическое руководство. Сжатие и извлечение файлов
<xref:System.IO.Compression> Пространство имен содержит следующие типы для сжатия и распаковки файлов и потоков. Можно также использовать эти типы для чтения и изменения содержимого сжатого файла:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 Некоторые функции, которые можно выполнять при работе с сжатые файлы в следующих примерах.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как создавать и извлекать сжатый файл с расширением ZIP, используя <xref:System.IO.Compression.ZipFile> класса. Он сжимает содержимое папки в новый ZIP-файл и затем извлекает это содержимое в новую папку. Для использования <xref:System.IO.Compression.ZipFile> , должны ссылаться `System.IO.Compression.FileSystem` сборки в проекте.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a>Пример  
 Следующий пример показано, как возможность просмотра содержимого существующего файла .zip и извлечь файлы, которые имеют расширение txt. Она использует <xref:System.IO.Compression.ZipArchive> класса для доступа к существующей ZIP-файл и <xref:System.IO.Compression.ZipArchiveEntry> класс отдельные операции в сжатом файле. Он используется метод расширения (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) для <xref:System.IO.Compression.ZipArchiveEntry> объекта. Метод расширения доступен в <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> класса. Для использования <xref:System.IO.Compression.ZipFileExtensions> , должны ссылаться `System.IO.Compression.FileSystem` сборки в проекте.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.IO.Compression.ZipArchive> класса для доступа к существующей ZIP-файл и добавляет новый файл для сжатого файла. Новый файл получает сжимаются при добавлении существующих ZIP-файл.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a>Пример  
 Можно также использовать <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> классы для сжатия и распаковки данных. Они используют один и тот же алгоритм сжатия. Сжатые <xref:System.IO.Compression.GZipStream> объектов, которые записаны в файл с расширением .gz могут быть извлечены с помощью многих распространенных средств Помимо методов, предоставляемых <xref:System.IO.Compression.GZipStream>. В этом примере показано, как для сжатия и распаковки каталог файлов с помощью <xref:System.IO.Compression.GZipStream> класса.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
