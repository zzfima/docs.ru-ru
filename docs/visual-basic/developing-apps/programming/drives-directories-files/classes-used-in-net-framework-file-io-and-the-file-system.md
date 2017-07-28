---
title: "Классы, используемые при файловом вводе-выводе в .NET Framework, и файловая система (Visual Basic) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ca1ecff264734c16369c9a7d28fbb388bb2f1ccc
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a>Классы, используемые при файловом вводе-выводе в .NET Framework, и файловая система (Visual Basic)
В приведенных ниже таблицах перечислены классы, обычно используемые для файлового ввода-вывода в .NET Framework. Они разделены на классы файлового ввода-вывода, классы для создания потоков и классы для чтения и записи в поток.  
  
 Документацию по [!INCLUDE[dnprdnlong](../../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] и более полный список см. в разделе [Общие сведения о библиотеке классов](https://msdn.microsoft.com/library/hfa3fa08).  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a>Основные классы ввода-вывода для файлов, каталогов и дисков  
 В приведенной ниже таблице перечислены и описаны основные классы, используемые для файлового ввода-вывода.  
  
|Класс|Описание|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=fullName>|Предоставляет статические методы для создания, перемещения и перечисления в каталогах и подкаталогах.|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|Предоставляет методы экземпляра для создания, перемещения и перечисления в каталогах и подкаталогах.|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|Предоставляет методы экземпляра для создания, перемещения и перечисления по дискам.|  
|<xref:System.IO.File?displayProperty=fullName>|Предоставляет статические методы для создания, копирования, удаления, перемещения и открытия файлов, а также помогает при создании объектов `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|Определяет константы для доступа к файлу для чтения, записи или чтения и записи.|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|Предоставляет атрибуты для файлов и каталогов, например `Archive`, `Hidden` и `ReadOnly`.|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|Предоставляет статические методы для создания, копирования, удаления, перемещения и открытия файлов, а также помогает при создании объектов `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=fullName>|Управляет процессом открытия файла. Этот параметр задается во многих конструкторах объектов `FileStream` и `IsolatedStorageFileStream`, а также в методах `Open` объектов <xref:System.IO.File> и <xref:System.IO.FileInfo>.|  
|<xref:System.IO.FileShare?displayProperty=fullName>|Определяет константы для управления типом доступа других файловых потоков к этому же файлу.|  
|<xref:System.IO.Path?displayProperty=fullName>|Предоставляет методы и свойства для обработки строк каталога.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|Управляет доступом к файлам и папкам, определяя разрешения <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> и <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.|  
  
## <a name="classes-used-to-create-streams"></a>Классы, используемые для создания потоков  
 В приведенной ниже таблице перечислены и описаны основные классы, используемые для создания потоков.  
  
|Класс|Описание|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|Добавляет уровень буферизации в операциях чтения и записи в другие потоки.|  
|<xref:System.IO.FileStream?displayProperty=fullName>|Поддерживает произвольный доступ к файлам с помощью метода <xref:System.IO.FileStream.Seek%2A>. <xref:System.IO.FileStream> по умолчанию открывает файлы синхронно, но поддерживает и асинхронные операции.|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|Создает поток, резервное хранилище которого находится в памяти, а не в файле.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|Обеспечивает базовый поток данных для доступа к сети.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|Определяет поток, который связывает потоки данных с криптографическими преобразованиями.|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a>Классы, используемые для чтения из потоков и записи в них  
 В приведенной ниже таблице описаны некоторые классы, используемые для чтения из файлов и записи в них с помощью потоков.  
  
|**Класс**|**Описание**|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|Считывает кодированные строки и примитивные типы данных из <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|Записывает кодированные строки и примитивные типы данных в <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|Считывает символы из <xref:System.IO.FileStream>, преобразуя символы в байты и наоборот с помощью <xref:System.IO.StreamReader.CurrentEncoding%2A>. <xref:System.IO.StreamReader> имеет конструктор, который пытается выяснить правильный <xref:System.IO.StreamReader.CurrentEncoding%2A> для заданного потока, оценивая наличие преамбулы для конкретного <xref:System.IO.StreamReader.CurrentEncoding%2A>, например метки порядка байтов.|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|Записывает символы в `FileStream`, преобразуя символы в байты с помощью <xref:System.IO.StreamWriter.Encoding%2A>.|  
|<xref:System.IO.StringReader?displayProperty=fullName>|Считывает символы из `String`. Вывод может быть либо потоком в любой кодировке, либо `String`.|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|Записывает символы в `String`. Вывод может быть либо потоком в любой кодировке, либо `String`.|  
  
## <a name="see-also"></a>См. также  
 [Составление потоков](https://msdn.microsoft.com/library/e4y2dch9)   
 [Файловый и потоковый ввод-вывод](https://msdn.microsoft.com/library/k3352a4t)   
 [Асинхронный файловый ввод-вывод](https://msdn.microsoft.com/library/kztecsys)   
 [Основы файлового ввода-вывода и файловой системы в .NET Framework (Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)
