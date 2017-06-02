---
title: "Практическое руководство. Перечисление каталогов и файлов | Microsoft Docs"
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
  - "ввод-вывод [платформа .NET Framework], перечисление каталогов и файлов"
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Перечисление каталогов и файлов
Можно выполнять перечисление каталогов и файлов с помощью методов, которые возвращают перечисляемую коллекцию строк, представляющих их имена.  Также можно использовать методы, которые возвращают перечисляемую коллекцию объектов класса<xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> или объектов класса <xref:System.IO.FileSystemInfo>.  Перечисляемые коллекции обеспечивают лучшую производительность, чем массивы, при работе с большими коллекциями каталогов и файлов.  
  
 Перечисляемые коллекции, полученные из этих методов, также можно использовать для предоставления параметра <xref:System.Collections.Generic.IEnumerable%601> для конструкторов классов коллекций, например, классу <xref:System.Collections.Generic.List%601>.  
  
 Если необходимо получить только имена каталогов или файлов, используйте методы перечисления класса <xref:System.IO.Directory>.  Если необходимо получить другие свойства каталогов или файлов, используйте класс <xref:System.IO.DirectoryInfo> и класс <xref:System.IO.FileSystemInfo>.  
  
 В следующей таблице представлено руководство для методов, которые возвращают перечисляемые коллекции.  
  
|Объект для перечисления|Возвращаемая перечисляемая коллекция|Используемый метод|  
|-----------------------------|------------------------------------------|------------------------|  
|Каталоги|Имена каталогов|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=fullName>|  
||Сведения о каталоге \(<xref:System.IO.DirectoryInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=fullName>|  
|Файлы|Имена файла|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=fullName>|  
||Сведения о файле \(<xref:System.IO.FileInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=fullName>|  
|Сведения о файловой системе|Элементы файловой системы|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=fullName>|  
||Сведения о файловой системе \(<xref:System.IO.FileSystemInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=fullName>|  
  
 Хотя можно немедленно выполнить перечисление всех файлов во вложенных каталогах родительского каталога, с помощью параметра поиска <xref:System.IO.SearchOption>, представленного перечислением <xref:System.IO.SearchOption>, исключения несанкционированного доступа \(<xref:System.UnauthorizedAccessException>\) могут привести к тому, что коллекция будет неполной.  Если такие исключения вероятны, их можно перехватить и продолжить выполнение перечисления сначала для каталогов, а затем для файлов.  
  
### Перечисление имен каталогов  
  
-   Используйте метод <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=fullName> для получения списка имен каталогов верхнего уровня в заданном пути.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### Перечисление имен файлов в каталоге и подкаталогах  
  
-   Используйте метод <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=fullName> для поиска каталог и \(при необходимости\) его подкаталогов, и получения списка имен файлов, соответствующих заданному шаблону поиска.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### Перечисление коллекции объектов DirectoryInfo  
  
-   Используйте метод <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=fullName> для получения коллекции каталогов верхнего уровня.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### Перечисление коллекции объектов FileInfo во всех каталогах  
  
-   Используйте метод <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=fullName> для получения коллекции файлов, которые сопоставлены заданному шаблону поиска во всех каталогах.  В данном примере сначала выполняется перечисление каталогов верхнего уровня с целью перехвата возможных исключений несанкционированного доступа, затем выполняется перечисление файлов.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## См. также  
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)