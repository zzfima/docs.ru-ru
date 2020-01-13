---
title: Практическое руководство. Перечисление каталогов и файлов
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: 6a26d0ef529b81976c4d2caafed34bb5f08d8d46
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75707749"
---
# <a name="how-to-enumerate-directories-and-files"></a>Практическое руководство. Перечисление каталогов и файлов
Перечислимые коллекции дают более высокую производительность, чем массивы, если вы работаете с большими коллекциями файлов и каталогов. Чтобы перечислить каталоги и файлы, вы можете применить методы, которые возвращают перечисляемую коллекцию имен каталогов или файлов, либо их объекты <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> или <xref:System.IO.FileSystemInfo>.  
  
Если вы хотите найти и вернуть только имена каталогов или файлов, используйте методы перечисления из класса <xref:System.IO.Directory>. Если вы хотите найти и вернуть другие свойства каталогов или файлов, используйте классы <xref:System.IO.DirectoryInfo> и <xref:System.IO.FileSystemInfo>.  
  
Кроме того, можно использовать перечисляемые коллекции из этих методов в качестве параметра <xref:System.Collections.Generic.IEnumerable%601> для конструкторов классов коллекций, таких как <xref:System.Collections.Generic.List%601>.  
  
В следующей таблице обобщаются методы, которые возвращают перечисляемые коллекции файлов и каталогов:  
  
|Что нужно найти и вернуть|Используемый метод|  
|------------------|-------------------------------------|-------------------|  
|Имена каталогов|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Сведения о каталогах (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Имена файлов|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Сведения о файлах (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Имена записей файловой системы|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|Сведения о записи файловой системы (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|Имена каталогов и файлов |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> Несмотря на то, что у вас есть возможность немедленно перечислить все файлы во вложенных каталогах родительского каталога, применив параметр <xref:System.IO.SearchOption.AllDirectories> необязательного перечисления <xref:System.IO.SearchOption>, из-за ошибок <xref:System.UnauthorizedAccessException> перечисление может оказаться неполным. Вы можете реализовать перехват таких исключений, сначала перечислив каталоги, а затем файлы.  
  
## <a name="examples-use-the-directory-class"></a>Примеры Использование класса Directory  
  
В следующем примере используется метод <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType>, чтобы получить список имен каталогов верхнего уровня из указанного пути.  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

В следующем примере используется метод <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> для рекурсивного перечисления имен всех файлов в каталоге и подкаталогах, соответствующих определенному шаблону. После этого проверяется каждая строка каждого файла и отображаются строки, которые содержат указанную строку, с соответствующими именами файлов и путями к ним.

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a>Примеры Использование класса DirectoryInfo  
  
В следующем примере используется метод <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> для получения списка каталогов верхнего уровня, для которых значение <xref:System.IO.FileSystemInfo.CreationTimeUtc> раньше заданного значения <xref:System.DateTime>.  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
В следующем примере используется метод <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> для получения списка всех файлов, для которых значение <xref:System.IO.FileInfo.Length> превышает 10 МБ. В этом примере поиска сначала перечисляются каталоги верхнего уровня, чтобы перехватить все возможные исключения несанкционированного доступа, а затем перечисляются файлы.  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
