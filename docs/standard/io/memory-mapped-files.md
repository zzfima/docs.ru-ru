---
title: "Сопоставленные в памяти файлы"
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
- memory-mapped files
- inter-process communiation
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
caps.latest.revision: "24"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2602d431aada7b3e0ee226eed319903492022ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="memory-mapped-files"></a>Сопоставленные в памяти файлы
Отображаемый в память файл содержит содержимое файла в виртуальной памяти. Это сопоставление файла и области памяти позволяет приложению, включая множество процессов, измените файл, чтение и запись напрямую в память. Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать управляемый код для доступа к памяти файлов таким же образом, что собственные функции Windows, доступ к файлам, размещенный в памяти, как описано в [помощью файлы в Win32](http://go.microsoft.com/fwlink/?linkid=180801).  
  
 Существует два типа файлов, размещенный в памяти.  
  
-   Постоянные сопоставленные в памяти файлы  
  
     Сохраненные файлы, сопоставленные в памяти файлы, которые связаны с исходным файлом на диске. Когда последний процесс закончил работу с файлом, данные сохраняются в исходный файл на диске. Эти сопоставленные в памяти файлы подходят для работы с очень большими исходными файлами.  
  
-   Непостоянные сопоставленные в памяти файлы  
  
     Непостоянные файлы, сопоставленные в памяти файлы, которые не связаны с файлом на диске. Когда последний процесс закончил работу с файлом, данные будут потеряны, и файл будет удален при сборке мусора. Эти файлы подходят для создания общей памяти для межпроцессного взаимодействия (IPC).  
  
## <a name="processes-views-and-managing-memory"></a>Процессы, представления и управление памятью  
 Сопоставленные в памяти файлы могут совместно использоваться несколькими процессами. Процессы могут сопоставляться в тот же файл, размещенный в памяти с помощью общего имени, которое назначается процессом, который создал файл.  
  
 Для работы с файлом, размещенный в памяти, необходимо создать представление весь файл, размещенный в памяти или его части. Также можно создать несколько представлений на одну часть файла размещенный в памяти, тем самым создавая параллельной памяти. Для два представления оставались параллельными они должны быть созданы из одного файла размещенный в памяти.  
  
 Несколько представлений, также может потребоваться в том случае, если файл больше, чем размер пространства логической памяти приложения, доступный для сопоставления (2 ГБ на 32-разрядном компьютере) памяти.  
  
 Существует два типа представления: представление потокового доступа и представление произвольного доступа. Использовать представления потокового доступа для последовательного доступа к файлу. Это рекомендуется для непостоянных файлов и IPC. Представления произвольного доступа являются предпочтительными для работы с постоянными файлами.  
  
 Сопоставленные в памяти файлы осуществляется через диспетчер памяти операционной системы, чтобы файл автоматически разделена на несколько страниц и доступным при необходимости. Необходимо самостоятельно обрабатывать управление памятью.  
  
 На следующем рисунке показано как несколько процессов могут иметь несколько представлений и перекрывающие представления в тот же файл, размещенный в памяти в то же время.  
  
 ![Показывает представления в памяти & #45, сопоставленный файл. ] (../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")  
Несколько представлений и перекрывающие представления в файл, размещенный в памяти  
  
## <a name="programming-with-memory-mapped-files"></a>Программирование с использованием сопоставленные в памяти файлы  
 Следующая таблица содержится руководство по использованию файла размещенный в памяти объекты и их члены.  
  
|Задача|Методы или свойства для использования|  
|----------|----------------------------------|  
|Чтобы получить <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> , представляющий сохраненный файл, размещенный в памяти, из файла на диске.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.|  
|Для получения <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> объект, который представляет переменное размещенный в памяти файл (не связан с файлом на диске).|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.<br /><br /> -или-<br /><br /> Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.|  
|Для получения <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> объекта существующего файла размещенный в памяти (материализованные или переменное).|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.|  
|Для получения <xref:System.IO.UnmanagedMemoryStream> для последовательно доступного представления в файл, размещенный в памяти.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.|  
|Для получения <xref:System.IO.UnmanagedMemoryAccessor> объекта для представления произвольный доступ к сопоставленному в памяти файлу.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.|  
|Для получения <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> объект для использования с неуправляемым кодом.|Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.<br /><br /> -или-<br /><br /> Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.<br /><br /> -или-<br /><br /> Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.|  
|Чтобы отложить распределение памяти до представление создается (только непостоянных файлов).<br /><br /> (Чтобы определить размер текущей системной страницы, используйте <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> свойство.)|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>метод с <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> значение.<br /><br /> -или-<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>методы, которые имеют <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> перечисление как параметр.|  
  
### <a name="security"></a>Безопасность  
 Права доступа можно применять при создании файла размещенный в памяти, с помощью следующих методов, которые принимают <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> перечисление как параметр:  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 Можно задать права доступа для открытия существующего файла размещенный в памяти с помощью <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> методов, которые принимают <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> как параметр.  
  
 Кроме того, можно включить <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> , содержащий предварительно определенные правила доступа.  
  
 Чтобы применить новые или измененные правила доступа в файл, размещенный в памяти, используйте <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> метод. Чтобы получить доступ или правила аудита из существующего файла, используйте <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> метод.  
  
## <a name="examples"></a>Примеры  
  
### <a name="persisted-memory-mapped-files"></a>Постоянные сопоставленные в памяти файлы  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> Методы создают размещенный в памяти файл из существующего файла на диске.  
  
 В следующем примере создается представление, размещенный в памяти части очень большого файла и управляет его части.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 В следующем примере открывается же размещенный в памяти файл для другого процесса.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a>Несохраняемые сопоставленные в памяти файлы  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> И <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> методы создания файла, не сопоставленным к существующему файлу на диске размещенный в памяти.  
  
 Приведенный далее пример состоит из трех отдельных процессов (консольных приложений), которые записывают логические значения в файл, размещенный в памяти. Происходят следующие действия:  
  
1.  `Process A`Создает размещенный в памяти файл и записывает в него значение.  
  
2.  `Process B`открывает размещенный в памяти файл и записывает в него значение.  
  
3.  `Process C`открывает размещенный в памяти файл и записывает в него значение.  
  
4.  `Process A`Считывает и отображает значения из файла размещенный в памяти.  
  
5.  После `Process A` завершения работы с файлом размещенный в памяти файл немедленно будет уничтожен сборщиком мусора.  
  
 Чтобы выполнить этот пример, выполните следующие действия:  
  
1.  Скомпилируйте приложения и откройте три окна командной строки.  
  
2.  В первом окне командной строки запустите `Process A`.  
  
3.  Во втором окне командной строки запустите `Process B`.  
  
4.  Вернитесь к `Process A` и нажмите клавишу ВВОД.  
  
5.  В третьем окне командной строки запустите `Process C`.  
  
6.  Вернитесь к `Process A` и нажмите клавишу ВВОД.  
  
 Выходные данные `Process A` выглядит следующим образом:  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 **Процесс A**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 **Процесс Б**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 **Процесс C**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
