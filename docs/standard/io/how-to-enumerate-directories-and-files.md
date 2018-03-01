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
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5d0f22853210144881e49c4192ea38a5c3e57cda
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>Практическое руководство. Перечисление каталогов и файлов
Чтобы перечислить все каталоги и файлы, вы можете применить методы, которые возвращают перечислимую коллекцию строк с именами объектов. Также можно использовать методы, которые возвращают перечислимую коллекцию объектов <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> или <xref:System.IO.FileSystemInfo>. Перечислимые коллекции дают более высокую производительность, чем массивы, если вы работаете с большими коллекциями файлов и каталогов.  
  
 Кроме того, можно использовать перечислимые коллекции, полученные из этих методов, чтобы передавать параметр <xref:System.Collections.Generic.IEnumerable%601> в конструкторы классов коллекций, таких как класс <xref:System.Collections.Generic.List%601>.  
  
 Если вы хотите только получить имена каталогов или файлов, используйте методы перечисления из класса <xref:System.IO.Directory>. Если вы хотите получить другие свойства каталогов или файлов, используйте классы <xref:System.IO.DirectoryInfo> и <xref:System.IO.FileSystemInfo>.  
  
 Следующая таблица содержит рекомендации по работе с методами, которые возвращают перечислимые коллекции.  
  
|Объект для перечисления|Возвращаемая перечислимая коллекция|Используемый метод|  
|------------------|-------------------------------------|-------------------|  
|Каталоги|Имена каталогов|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||Сведения о каталогах (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Файлы|Имена файлов|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||Сведения о файлах (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Сведения о файловой системе|Элементы файловой системы|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||Сведения о файловой системе (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 Несмотря на то, что у вас есть возможность немедленно перечислить все файлы во вложенных каталогах родительского каталога, применив функцию поиска <xref:System.IO.SearchOption.AllDirectories> из перечисления <xref:System.IO.SearchOption>, это перечисление может оказаться неполным из-за исключений несанкционированного доступа (<xref:System.UnauthorizedAccessException>). Если есть риск таких исключений, следует организовать их перехват, и для продолжения работы сначала перечислить каталоги, а затем файлы в них.  
  
### <a name="to-enumerate-directory-names"></a>Перечисление имен каталогов  
  
-   Используйте метод <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>, чтобы получить список имен каталогов верхнего уровня из указанного пути.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>Перечисление имен файлов в каталоге и подкаталогах  
  
-   Используйте метод <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType>, чтобы выполнить поиск в каталоге и (необязательно) его подкаталогах и получить список имен файлов, соответствующих указанному шаблону поиска.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>Перечисление коллекции объектов DirectoryInfo  
  
-   Используйте метод <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>, чтобы получить коллекцию каталогов верхнего уровня.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>Перечисление коллекции объектов FileInfo из всех каталогов  
  
-   Используйте метод <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>, чтобы получить коллекцию файлов, имена которых соответствуют указанному шаблону поиска, расположенных из всех каталогов. В этом примере поиска сначала перечисляются каталоги верхнего уровня, чтобы перехватить все возможные исключения несанкционированного доступа, а затем перечисляются файлы.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
