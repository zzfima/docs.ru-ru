---
title: "Классы, используемые при файловом вводе-выводе в .NET Framework, и файловая система (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "файл классов ввода-вывода"
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Классы, используемые при файловом вводе-выводе в .NET Framework, и файловая система (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В следующей таблице перечислены классы, обычно используемые для файлового ввода\-вывода в .NET Framework. Они разделены на классы файлового ввода\-вывода, классы для создания потоков и классы для чтения и записи в поток.  
  
 Документацию по [!INCLUDE[dnprdnlong](../../../../csharp/programming-guide/events/includes/dnprdnlong-md.md)] и более полный список см. в разделе [Общие сведения о библиотеке классов](../Topic/.NET%20Framework%20Class%20Library%20Overview.md).  
  
## Основные классы ввода\-вывода для файлов, каталогов и дисков  
 В следующей таблице перечислены и описаны основные классы, используемые для файлового ввода\-вывода.  
  
|Класс|Описание|  
|-----------|--------------|  
|<xref:System.IO.Directory?displayProperty=fullName>|Предоставляет статические методы для создания, перемещения и перечисления в каталогах и вложенных каталогах.|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|Предоставляет методы экземпляра класса для создания, перемещения и перечисления в каталогах и вложенных каталогах.|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|Предоставляет методы экземпляра класса для создания, перемещения и перечисления по дискам.|  
|<xref:System.IO.File?displayProperty=fullName>|Предоставляет статические методы для создания, копирования, удаления, перемещения и открытия файлов, а также помогает при создании объектов `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|Определяет константы чтения, записи или чтения и записи файла.|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|Предоставляет атрибуты для файлов и каталогов, например `Archive` `Hidden` и `ReadOnly`.|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|Предоставляет статические методы для создания, копирования, удаления, перемещения и открытия файлов, а также помогает при создании объектов `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=fullName>|Управляет процессом открытия файла.  Этот параметр задается во многих конструкторах объектов `FileStream` и `IsolatedStorageFileStream` и методах `Open` объектов <xref:System.IO.File> и <xref:System.IO.FileInfo>.|  
|<xref:System.IO.FileShare?displayProperty=fullName>|Определяет константы для управления типом доступа других файловых потоков к этому же файлу.|  
|<xref:System.IO.Path?displayProperty=fullName>|Предоставляет методы и свойства для обработки строк каталога.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|Управляет доступом к файлам и каталогам путем определения разрешений <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A> <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> и <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.|  
  
## Классы, используемые для создания потоков  
 В следующей таблице перечислены и описаны основные классы, используемые для создания потоков.  
  
|Класс|Описание|  
|-----------|--------------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|Осуществляет буферизацию в операциях чтения и записи в другие потоки.|  
|<xref:System.IO.FileStream?displayProperty=fullName>|Поддерживает произвольный доступ к файлам с помощью метода <xref:System.IO.FileStream.Seek%2A>.  <xref:System.IO.FileStream> по умолчанию открывает файлы синхронно, но поддерживает и асинхронные операции.|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|Создает поток, резервное хранилище которого находится в памяти, а не в файле.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|Обеспечивает базовый поток данных для доступа к сети.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|Определяет поток, который связывает потоки данных с криптографическими преобразованиями.|  
  
## Классы, используемые для чтения и записи в потоки  
 В следующей таблице описаны некоторые классы, используемые для чтения и записи в файлы с помощью потоков.  
  
|**Класс**|**Описание**|  
|---------------|------------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|Считывает кодированные строки и простые типы данных из <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|Записывает кодированные строки и простые типы данных в <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|Считывает символы из <xref:System.IO.FileStream>, используя <xref:System.IO.StreamReader.CurrentEncoding%2A> для преобразования символов в байты и наоборот.  <xref:System.IO.StreamReader> имеет конструктор, который пытается выяснить подходящую кодировку <xref:System.IO.StreamReader.CurrentEncoding%2A> для заданного потока на основе наличия специфичной для <xref:System.IO.StreamReader.CurrentEncoding%2A> преамбулы, такой как метка порядка байтов.|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|Записывает символы в поток `FileStream`, используя класс <xref:System.IO.StreamWriter.Encoding%2A> для преобразования символов в байты.|  
|<xref:System.IO.StringReader?displayProperty=fullName>|Считывает символы из `String`.  Вывод может быть либо потоком в любой кодировке, либо `String`.|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|Записывает символы в `String`.  Вывод может быть либо потоком в любой кодировке, либо `String`.|  
  
## См. также  
 [Составление потоков](../Topic/Composing%20Streams.md)   
 [Файловый и потоковый ввод\-вывод](../Topic/File%20and%20Stream%20I-O.md)   
 [Асинхронный файловый ввод\-вывод](../Topic/Asynchronous%20File%20I-O.md)   
 [Основы файлового ввода\-вывода и файловой системы в .NET Framework \(Visual Basic\)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)