---
title: "Сопоставленные в памяти файлы | Microsoft Docs"
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
  - "межпроцессное взаимодействие"
  - "сопоставленные в памяти файлы"
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
caps.latest.revision: 24
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 24
---
# Сопоставленные в памяти файлы
Отображаемый в память файл содержит содержимое файла в виртуальной памяти.  Это сопоставление файла и области памяти позволяет приложению, включая множество процессов, изменять файл путем чтения и записи прямо в память.  Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать управляемый код для доступа к сопоставленным в памяти файлам тем же способом, с помощью которого собственные функции Windows получают доступ к сопоставленным в памяти файлам. Описание см. в разделе [Managing Memory\-Mapped Files in Win32](http://go.microsoft.com/fwlink/?linkid=180801) в библиотеке MSDN.  
  
 Существует два типа сопоставленных в памяти файлов.  
  
-   Постоянные сопоставленные в памяти файлы  
  
     Постоянные файлы являются сопоставленными в памяти файлами, которые связаны с исходным файлом на диске.  Данные сохраняются в исходный файл на диск, когда последний процесс закончил работу с файлом.  Это сопоставленные в памяти файлы подходят для работы с очень большими исходными файлами.  
  
-   Непостоянные сопоставленные в памяти файлы  
  
     Непостоянные файлы являются сопоставленными в памяти файлами, которые не связаны с исходным файлом на диске.  Когда последний процесс закончил работу с файлом, данные утрачиваются и файл удаляется функцией сборки мусора.  Такие файлы подходят для создания общей памяти для межпроцессного взаимодействия \(IPC\).  
  
## Процессы, представления и управление памятью  
 Сопоставленные в памяти файлы могут совместно использоваться несколькими процессами.  Процессы могут сопоставляться с одним сопоставленным в памяти файлом с помощью общего имени, которое назначается процессом, создающим файл.  
  
 Для работы с сопоставленным в памяти файлом необходимо создать представление всего сопоставленного в памяти файла или его части.  Можно также создать несколько представлений одной и той же части сопоставленного в памяти файла, создавая таким образом параллельную память.  Чтобы два представления оставались параллельными, они должны быть созданы из одного сопоставленного в памяти файла.  
  
 Также может потребоваться использование нескольких представлений, если файл превышает размер пространства логической памяти приложения, доступный для сопоставления памяти \(2 ГБ на компьютере с 32\-разрядной архитектурой\).  
  
 Существует два типа представлений: представление потокового доступа и представление произвольного доступа.  Необходимо использовать представления потокового доступа для последовательного доступа к файлу; это является предпочтительным для непостоянных файлов и IPC.  Представления произвольного доступа являются предпочтительными для работы с постоянными файлами.  
  
 Сопоставляемые в памяти файлы являются доступными при помощи диспетчера памяти операционной системы, таким образом файл является автоматически разделенным на множество страниц и доступным при необходимости.  Управлять памятью вручную не нужно.  
  
 На следующем рисунке показаны несколько представлений и перекрывающие представления одного и того же одновременно сопоставленного в памяти файла.  
  
 ![Отображение представлений в размещенном в памяти файле.](../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")  
Несколько представлений и перекрывающие представления сопоставленного в памяти файла  
  
## Программирование с использованием сопоставленных в памяти файлов  
 В следующей таблице представлено краткое руководство по использованию объектов сопоставленных в памяти файлов и их членов.  
  
|Задача|Использование методов или свойств|  
|------------|---------------------------------------|  
|Чтобы получить объект <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>, который представляет постоянный сопоставленный в памяти файл из файла на диске.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=fullName>.|  
|Чтобы получить объект <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>, который представляет непостоянный сопоставленный в памяти файл \(не связанный с файлом на диске\).|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=fullName>.<br /><br /> \- либо \-<br /><br /> Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=fullName>.|  
|Чтобы получить объект <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> создаваемого сопоставленного в памяти файла \(постоянного или непостоянного\).|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=fullName>.|  
|Чтобы получить объект <xref:System.IO.UnmanagedMemoryStream> для последовательно доступного представления к сопоставленному в памяти файлу.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=fullName>.|  
|Чтобы получить объект <xref:System.IO.UnmanagedMemoryAccessor> для произвольного доступа представления к сопоставленному в памяти файлу.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=fullName>.|  
|Чтобы получить объект <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> для использования с неуправляемым кодом.|Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=fullName>.<br /><br /> \- либо \-<br /><br /> Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=fullName>.<br /><br /> \- либо \-<br /><br /> Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=fullName>.|  
|Чтобы отложить распределение памяти до момента создания представления \(только для непостоянных файлов\).<br /><br /> \(Чтобы определить размер текущей системной страницы, необходимо использовать свойство <xref:System.Environment.SystemPageSize%2A?displayProperty=fullName>\).|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> со значением <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions?displayProperty=fullName>.<br /><br /> \- либо \-<br /><br /> метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>, имеющий перечисление как параметр <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions>.|  
  
### Безопасность  
 Можно применять права доступа, когда создается сопоставленный в памяти файл, используя методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess>, которые принимают перечисление как параметр:  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=fullName>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=fullName>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=fullName>  
  
 Можно задать права доступа для открытия сопоставленного в памяти файла, используя методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A>, которые принимают <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> как параметр.  
  
 Дополнительно, можно включить объект <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity>, который содержит предварительно определенные правила доступа.  
  
 Чтобы применить новые или измененные правила доступа к сопоставленному в памяти файлу, используется метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>.  Для извлечения правил доступа или аудита из существующего файла служит метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>.  
  
## Примеры  
  
### Постоянные сопоставленные в памяти файлы  
 Методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> создают сопоставленный в памяти файл из существующего файла на диске.  
  
 В следующем примере создается сопоставленное в памяти представление части очень большого файла и выполняется работа с его частью.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 В следующем примере открывается тот же сопоставленный в памяти файл для другого процесса.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### Непостоянные сопоставленные в памяти файлы  
 Методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> и <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> создают сопоставленный в памяти файл, не сопоставленный с существующим файлом на диске.  
  
 Следующий пример состоит из трех отдельных процессов \(консольных приложений\), которые записывают логические значения в сопоставленный в памяти файл.  Выполняется приведенная ниже последовательность действий.  
  
1.  Процесс `Process A` создает сопоставленный в памяти файл и записывает в него значение.  
  
2.  Процесс `Process B` открывает сопоставленный в памяти файл и записывает в него значение.  
  
3.  Процесс `Process C` открывает сопоставленный в памяти файл и записывает в него значение.  
  
4.  Процесс `Process A` считывает и отображает значения из сопоставленного в памяти файла.  
  
5.  После того как процесс `Process A` закончит работу с сопоставленным в памяти файлом, этот файл немедленно будет уничтожен сборкой мусора.  
  
 Для выполнения этого примера выполните следующие действия:  
  
1.  Скомпилируйте приложения и откройте три окна командной строки.  
  
2.  В первом окне командной строки запустите процесс `Process A`.  
  
3.  Во втором окне командной строки запустите процесс `Process B`.  
  
4.  Вернитесь к процессу `Process A` и нажмите клавишу ВВОД.  
  
5.  В третьем окне командной строки запустите процесс `Process C`.  
  
6.  Вернитесь к процессу `Process A` и нажмите клавишу ВВОД.  
  
 Выходные данные процесса `Process A` выглядят следующим образом.  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 **Процесс А**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 **Процесс Б**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 **Процесс В**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## См. также  
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)