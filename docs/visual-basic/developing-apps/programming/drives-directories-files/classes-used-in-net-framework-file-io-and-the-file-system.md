---
title: Классы, используемые при файловом вводе-выводе в .NET Framework, и файловая система
ms.date: 07/20/2015
helpviewer_keywords:
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
ms.openlocfilehash: fe70f8fb655579049bb36fc324d04530259d25f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348930"
---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a>Классы, используемые при файловом вводе-выводе в .NET Framework, и файловая система (Visual Basic)

В приведенных ниже таблицах перечислены классы, обычно используемые для файлового ввода-вывода в .NET Framework. Они разделены на классы файлового ввода-вывода, классы для создания потоков и классы для чтения и записи в поток.  
  
Более полный список см. в разделе [Общие сведения о библиотеке классов](../../../../standard/class-library-overview.md).  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a>Основные классы ввода-вывода для файлов, каталогов и дисков  

 В приведенной ниже таблице перечислены и описаны основные классы, используемые для файлового ввода-вывода.  
  
|Класс|Описание:|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=nameWithType>|Предоставляет статические методы для создания, перемещения и перечисления в каталогах и подкаталогах.|  
|<xref:System.IO.DirectoryInfo?displayProperty=nameWithType>|Предоставляет методы экземпляра для создания, перемещения и перечисления в каталогах и подкаталогах.|  
|<xref:System.IO.DriveInfo?displayProperty=nameWithType>|Предоставляет методы экземпляра для создания, перемещения и перечисления по дискам.|  
|<xref:System.IO.File?displayProperty=nameWithType>|Предоставляет статические методы для создания, копирования, удаления, перемещения и открытия файлов, а также помогает при создании объектов `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=nameWithType>|Определяет константы для доступа к файлу для чтения, записи или чтения и записи.|  
|<xref:System.IO.FileAttributes?displayProperty=nameWithType>|Предоставляет атрибуты для файлов и каталогов, например `Archive`, `Hidden` и `ReadOnly`.|  
|<xref:System.IO.FileInfo?displayProperty=nameWithType>|Предоставляет статические методы для создания, копирования, удаления, перемещения и открытия файлов, а также помогает при создании объектов `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=nameWithType>|Управляет процессом открытия файла. Этот параметр задается во многих конструкторах объектов `FileStream` и `IsolatedStorageFileStream`, а также в методах `Open` объектов <xref:System.IO.File> и <xref:System.IO.FileInfo>.|  
|<xref:System.IO.FileShare?displayProperty=nameWithType>|Определяет константы для управления типом доступа других файловых потоков к этому же файлу.|  
|<xref:System.IO.Path?displayProperty=nameWithType>|Предоставляет методы и свойства для обработки строк каталога.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>|Управляет доступом к файлам и папкам, определяя разрешения <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> и <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.|  
  
## <a name="classes-used-to-create-streams"></a>Классы, используемые для создания потоков  

 В приведенной ниже таблице перечислены и описаны основные классы, используемые для создания потоков.  
  
|Класс|Описание:|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=nameWithType>|Добавляет уровень буферизации в операциях чтения и записи в другие потоки.|  
|<xref:System.IO.FileStream?displayProperty=nameWithType>|Поддерживает произвольный доступ к файлам с помощью метода <xref:System.IO.FileStream.Seek%2A>. <xref:System.IO.FileStream> по умолчанию открывает файлы синхронно, но поддерживает и асинхронные операции.|  
|<xref:System.IO.MemoryStream?displayProperty=nameWithType>|Создает поток, резервное хранилище которого находится в памяти, а не в файле.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=nameWithType>|Обеспечивает базовый поток данных для доступа к сети.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=nameWithType>|Определяет поток, который связывает потоки данных с криптографическими преобразованиями.|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a>Классы, используемые для чтения из потоков и записи в них  

 В приведенной ниже таблице описаны некоторые классы, используемые для чтения из файлов и записи в них с помощью потоков.  
  
|**Класс**|**Описание**|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=nameWithType>|Считывает кодированные строки и примитивные типы данных из <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=nameWithType>|Записывает кодированные строки и примитивные типы данных в <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=nameWithType>|Считывает символы из <xref:System.IO.FileStream>, преобразуя символы в байты и наоборот с помощью <xref:System.IO.StreamReader.CurrentEncoding%2A>. <xref:System.IO.StreamReader> имеет конструктор, который пытается выяснить правильный <xref:System.IO.StreamReader.CurrentEncoding%2A> для заданного потока, оценивая наличие преамбулы для конкретного <xref:System.IO.StreamReader.CurrentEncoding%2A>, например метки порядка байтов.|  
|<xref:System.IO.StreamWriter?displayProperty=nameWithType>|Записывает символы в `FileStream`, преобразуя символы в байты с помощью <xref:System.IO.StreamWriter.Encoding%2A>.|  
|<xref:System.IO.StringReader?displayProperty=nameWithType>|Считывает символы из `String`. Вывод может быть либо потоком в любой кодировке, либо `String`.|  
|<xref:System.IO.StringWriter?displayProperty=nameWithType>|Записывает символы в `String`. Вывод может быть либо потоком в любой кодировке, либо `String`.|  
  
## <a name="see-also"></a>См. также раздел

- [Составление потоков](../../../../standard/io/composing-streams.md)
- [Файловый и потоковый ввод-вывод](../../../../standard/io/index.md)
- [Asynchronous File I/O](../../../../standard/io/asynchronous-file-i-o.md)
- [Основы файлового ввода-вывода и файловой системы в .NET Framework (Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)
