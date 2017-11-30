---
title: "Практическое руководство. Перечисление каталогов и файлов"
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
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>Практическое руководство. Перечисление каталогов и файлов
Можно перечислить каталоги и файлы с помощью методов, которые возвращают перечисляемую коллекцию строк, представляющих их имена. Можно также использовать методы, которые возвращают перечисляемую коллекцию <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, или <xref:System.IO.FileSystemInfo> объектов. Перечисляемые коллекции обеспечивают лучшую производительность, чем массивы, при работе с большими коллекциями файлов и каталогов.  
  
 Можно также использовать перечислимые коллекции, полученные из этих методов для предоставления <xref:System.Collections.Generic.IEnumerable%601> параметр для конструкторов коллекции классов, таких как <xref:System.Collections.Generic.List%601> класса.  
  
 Если вы хотите получить только имена каталогов или файлов, используйте методы перечисления <xref:System.IO.Directory> класса. Если вы хотите получить другие свойства каталогов или файлов, используйте <xref:System.IO.DirectoryInfo> и <xref:System.IO.FileSystemInfo> классы.  
  
 Ниже приводится руководство по методы, которые возвращают перечислимые коллекции.  
  
|Для перечисления|Перечисляемая коллекция для возврата|Метод, используемый|  
|------------------|-------------------------------------|-------------------|  
|Каталоги|Имена каталогов|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||Сведения о каталоге (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Файлы|Имена файлов|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||Сведения о файлах (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Сведения о файловой системе|Элементы системного файла|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||Файл сведений о системе (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 Несмотря на то, что можно немедленно выполнить перечисление всех файлов во вложенных каталогах родительского каталога с помощью <xref:System.IO.SearchOption.AllDirectories> поиска, предоставляемые параметр <xref:System.IO.SearchOption> перечисления, исключения несанкционированного доступа (<xref:System.UnauthorizedAccessException>) может привести к перечисления не была завершена. Если эти исключения возможны, можно перехватить и продолжить, сначала перечисление каталогов и затем перечисление файлов.  
  
### <a name="to-enumerate-directory-names"></a>Перечисление имен каталогов  
  
-   Используйте <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> метод, чтобы получить список имен каталогов верхнего уровня по указанному пути.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>Перечисление имен файлов в каталоге и подкаталогах  
  
-   Используйте <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> метод для поиска и (необязательно) его подкаталогов каталога и получить список имен файлов, соответствующих указанному шаблону поиска.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>Перечисление коллекции объектов DirectoryInfo  
  
-   Используйте <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> метод для получения коллекции каталогов верхнего уровня.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>Перечисление коллекции объектов FileInfo во всех каталогах  
  
-   Используйте <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> метод, чтобы получить коллекцию файлов, которые соответствуют указанному шаблону поиска во всех каталогах. В этом примере сначала Перечисляет каталоги верхнего уровня для перехвата возможных исключений несанкционированного доступа и затем выполняется перечисление файлов.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
