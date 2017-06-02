---
title: "Практическое руководство. Сжатие и извлечение файлов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ввод-вывод [платформа .NET Framework], сжатие"
  - "сжатие"
  - "сжатие файлов"
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Сжатие и извлечение файлов
Пространство имен <xref:System.IO.Compression> содержит следующие типы для сжатия и распаковки файлов и потоков.  Можно также использовать эти типы для чтения и модификации содержимого сжатого файла:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 В следующих примерах показаны некоторые функций, которые можно выполнить при работе со сжатыми файлами.  
  
## Пример  
 В этом примере показано, как создать и извлечь сжатый файл, имеющий расширение ZIP\-файла с помощью класса <xref:System.IO.Compression.ZipFile>.  Он сжимает содержимое папки в новый ZIP\-файл, а затем извлекает это содержимое в новую папку.  Для использования класса <xref:System.IO.Compression.ZipFile> необходимо сослаться на сборку `System.IO.Compression.FileSystem` в проекте.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## Пример  
 В следующем примере показано, как выполнить итерацию содержимого существующего ZIP\-файла и извлечение файлов, имеющих расширение .txt.  Он использует класс <xref:System.IO.Compression.ZipArchive> для доступа к существующим ZIP\-файлам и класс <xref:System.IO.Compression.ZipArchiveEntry> для проверки отдельных записей в сжатом файле.  Он использует метод расширения \(<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>\) для объекта <xref:System.IO.Compression.ZipArchiveEntry>.  Метод расширения доступен в классе <xref:System.IO.Compression.ZipFileExtensions?displayProperty=fullName>.  Для использования класса <xref:System.IO.Compression.ZipFileExtensions> необходимо сослаться на сборку `System.IO.Compression.FileSystem` в проекте.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## Пример  
 В следующем примере используется класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему ZIP\-файлу и добавляется новый файл к сжатому файлу.  Новый файл сжат при его добавлении к существующему файлу .zip.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## Пример  
 Можно также использовать классы <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> для сжатия и распаковки данных.  Они используют тот же алгоритм сжатия.  Сжатые объекты <xref:System.IO.Compression.GZipStream>, записанные в файл с расширением .gz, могут быть распакованы с помощью общих инструментов в дополнение к методам, реализованным с помощью <xref:System.IO.Compression.GZipStream>.  В следующем примере демонстрируется использование класса <xref:System.IO.Compression.GZipStream> для сжатия и распаковки каталога файлов.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## См. также  
 <xref:System.IO.Compression.ZipArchive>   
 <xref:System.IO.Compression.ZipFile>   
 <xref:System.IO.Compression.ZipArchiveEntry>   
 <xref:System.IO.Compression.DeflateStream>   
 <xref:System.IO.Compression.GZipStream>   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)