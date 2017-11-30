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
# <a name="memory-mapped-files"></a><span data-ttu-id="1c1b7-102">Сопоставленные в памяти файлы</span><span class="sxs-lookup"><span data-stu-id="1c1b7-102">Memory-Mapped Files</span></span>
<span data-ttu-id="1c1b7-103">Отображаемый в память файл содержит содержимое файла в виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-103">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="1c1b7-104">Это сопоставление файла и области памяти позволяет приложению, включая множество процессов, измените файл, чтение и запись напрямую в память.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-104">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="1c1b7-105">Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать управляемый код для доступа к памяти файлов таким же образом, что собственные функции Windows, доступ к файлам, размещенный в памяти, как описано в [помощью файлы в Win32](http://go.microsoft.com/fwlink/?linkid=180801).</span><span class="sxs-lookup"><span data-stu-id="1c1b7-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files in Win32](http://go.microsoft.com/fwlink/?linkid=180801).</span></span>  
  
 <span data-ttu-id="1c1b7-106">Существует два типа файлов, размещенный в памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-106">There are two types of memory-mapped files:</span></span>  
  
-   <span data-ttu-id="1c1b7-107">Постоянные сопоставленные в памяти файлы</span><span class="sxs-lookup"><span data-stu-id="1c1b7-107">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="1c1b7-108">Сохраненные файлы, сопоставленные в памяти файлы, которые связаны с исходным файлом на диске.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-108">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="1c1b7-109">Когда последний процесс закончил работу с файлом, данные сохраняются в исходный файл на диске.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-109">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="1c1b7-110">Эти сопоставленные в памяти файлы подходят для работы с очень большими исходными файлами.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-110">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
-   <span data-ttu-id="1c1b7-111">Непостоянные сопоставленные в памяти файлы</span><span class="sxs-lookup"><span data-stu-id="1c1b7-111">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="1c1b7-112">Непостоянные файлы, сопоставленные в памяти файлы, которые не связаны с файлом на диске.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-112">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="1c1b7-113">Когда последний процесс закончил работу с файлом, данные будут потеряны, и файл будет удален при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-113">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="1c1b7-114">Эти файлы подходят для создания общей памяти для межпроцессного взаимодействия (IPC).</span><span class="sxs-lookup"><span data-stu-id="1c1b7-114">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="1c1b7-115">Процессы, представления и управление памятью</span><span class="sxs-lookup"><span data-stu-id="1c1b7-115">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="1c1b7-116">Сопоставленные в памяти файлы могут совместно использоваться несколькими процессами.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-116">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="1c1b7-117">Процессы могут сопоставляться в тот же файл, размещенный в памяти с помощью общего имени, которое назначается процессом, который создал файл.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-117">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="1c1b7-118">Для работы с файлом, размещенный в памяти, необходимо создать представление весь файл, размещенный в памяти или его части.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-118">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="1c1b7-119">Также можно создать несколько представлений на одну часть файла размещенный в памяти, тем самым создавая параллельной памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-119">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="1c1b7-120">Для два представления оставались параллельными они должны быть созданы из одного файла размещенный в памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-120">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="1c1b7-121">Несколько представлений, также может потребоваться в том случае, если файл больше, чем размер пространства логической памяти приложения, доступный для сопоставления (2 ГБ на 32-разрядном компьютере) памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-121">Multiple views may also be necessary if the file is greater than the size of the application’s logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="1c1b7-122">Существует два типа представления: представление потокового доступа и представление произвольного доступа.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-122">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="1c1b7-123">Использовать представления потокового доступа для последовательного доступа к файлу. Это рекомендуется для непостоянных файлов и IPC.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-123">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="1c1b7-124">Представления произвольного доступа являются предпочтительными для работы с постоянными файлами.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-124">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="1c1b7-125">Сопоставленные в памяти файлы осуществляется через диспетчер памяти операционной системы, чтобы файл автоматически разделена на несколько страниц и доступным при необходимости.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-125">Memory-mapped files are accessed through the operating system’s memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="1c1b7-126">Необходимо самостоятельно обрабатывать управление памятью.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-126">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="1c1b7-127">На следующем рисунке показано как несколько процессов могут иметь несколько представлений и перекрывающие представления в тот же файл, размещенный в памяти в то же время.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-127">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>  
  
 <span data-ttu-id="1c1b7-128">![Показывает представления в памяти & #45, сопоставленный файл. ] (../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span><span class="sxs-lookup"><span data-stu-id="1c1b7-128">![Shows views to a memory&#45;mapped file.](../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span></span>  
<span data-ttu-id="1c1b7-129">Несколько представлений и перекрывающие представления в файл, размещенный в памяти</span><span class="sxs-lookup"><span data-stu-id="1c1b7-129">Multiple and overlapped views to a memory-mapped file</span></span>  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="1c1b7-130">Программирование с использованием сопоставленные в памяти файлы</span><span class="sxs-lookup"><span data-stu-id="1c1b7-130">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="1c1b7-131">Следующая таблица содержится руководство по использованию файла размещенный в памяти объекты и их члены.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-131">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="1c1b7-132">Задача</span><span class="sxs-lookup"><span data-stu-id="1c1b7-132">Task</span></span>|<span data-ttu-id="1c1b7-133">Методы или свойства для использования</span><span class="sxs-lookup"><span data-stu-id="1c1b7-133">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="1c1b7-134">Чтобы получить <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> , представляющий сохраненный файл, размещенный в памяти, из файла на диске.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-134">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="1c1b7-135">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="1c1b7-136">Для получения <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> объект, который представляет переменное размещенный в памяти файл (не связан с файлом на диске).</span><span class="sxs-lookup"><span data-stu-id="1c1b7-136">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="1c1b7-137">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="1c1b7-138">-или-</span><span class="sxs-lookup"><span data-stu-id="1c1b7-138">- or -</span></span><br /><br /> <span data-ttu-id="1c1b7-139">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="1c1b7-140">Для получения <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> объекта существующего файла размещенный в памяти (материализованные или переменное).</span><span class="sxs-lookup"><span data-stu-id="1c1b7-140">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="1c1b7-141">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="1c1b7-142">Для получения <xref:System.IO.UnmanagedMemoryStream> для последовательно доступного представления в файл, размещенный в памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-142">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="1c1b7-143">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="1c1b7-144">Для получения <xref:System.IO.UnmanagedMemoryAccessor> объекта для представления произвольный доступ к сопоставленному в памяти файлу.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-144">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="1c1b7-145">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="1c1b7-146">Для получения <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> объект для использования с неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-146">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="1c1b7-147">Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="1c1b7-148">-или-</span><span class="sxs-lookup"><span data-stu-id="1c1b7-148">- or -</span></span><br /><br /> <span data-ttu-id="1c1b7-149">Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="1c1b7-150">-или-</span><span class="sxs-lookup"><span data-stu-id="1c1b7-150">- or -</span></span><br /><br /> <span data-ttu-id="1c1b7-151">Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="1c1b7-152">Чтобы отложить распределение памяти до представление создается (только непостоянных файлов).</span><span class="sxs-lookup"><span data-stu-id="1c1b7-152">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="1c1b7-153">(Чтобы определить размер текущей системной страницы, используйте <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> свойство.)</span><span class="sxs-lookup"><span data-stu-id="1c1b7-153">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="1c1b7-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>метод с <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> значение.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="1c1b7-155">-или-</span><span class="sxs-lookup"><span data-stu-id="1c1b7-155">- or -</span></span><br /><br /> <span data-ttu-id="1c1b7-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>методы, которые имеют <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> перечисление как параметр.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="1c1b7-157">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1c1b7-157">Security</span></span>  
 <span data-ttu-id="1c1b7-158">Права доступа можно применять при создании файла размещенный в памяти, с помощью следующих методов, которые принимают <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> перечисление как параметр:</span><span class="sxs-lookup"><span data-stu-id="1c1b7-158">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="1c1b7-159">Можно задать права доступа для открытия существующего файла размещенный в памяти с помощью <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> методов, которые принимают <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> как параметр.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-159">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="1c1b7-160">Кроме того, можно включить <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> , содержащий предварительно определенные правила доступа.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-160">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="1c1b7-161">Чтобы применить новые или измененные правила доступа в файл, размещенный в памяти, используйте <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-161">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="1c1b7-162">Чтобы получить доступ или правила аудита из существующего файла, используйте <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-162">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1c1b7-163">Примеры</span><span class="sxs-lookup"><span data-stu-id="1c1b7-163">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="1c1b7-164">Постоянные сопоставленные в памяти файлы</span><span class="sxs-lookup"><span data-stu-id="1c1b7-164">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="1c1b7-165"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> Методы создают размещенный в памяти файл из существующего файла на диске.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-165">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="1c1b7-166">В следующем примере создается представление, размещенный в памяти части очень большого файла и управляет его части.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-166">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 <span data-ttu-id="1c1b7-167">В следующем примере открывается же размещенный в памяти файл для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-167">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="1c1b7-168">Несохраняемые сопоставленные в памяти файлы</span><span class="sxs-lookup"><span data-stu-id="1c1b7-168">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="1c1b7-169"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> И <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> методы создания файла, не сопоставленным к существующему файлу на диске размещенный в памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-169">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="1c1b7-170">Приведенный далее пример состоит из трех отдельных процессов (консольных приложений), которые записывают логические значения в файл, размещенный в памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-170">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="1c1b7-171">Происходят следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1c1b7-171">The following sequence of actions occur:</span></span>  
  
1.  <span data-ttu-id="1c1b7-172">`Process A`Создает размещенный в памяти файл и записывает в него значение.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-172">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2.  <span data-ttu-id="1c1b7-173">`Process B`открывает размещенный в памяти файл и записывает в него значение.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-173">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3.  <span data-ttu-id="1c1b7-174">`Process C`открывает размещенный в памяти файл и записывает в него значение.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-174">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4.  <span data-ttu-id="1c1b7-175">`Process A`Считывает и отображает значения из файла размещенный в памяти.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-175">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5.  <span data-ttu-id="1c1b7-176">После `Process A` завершения работы с файлом размещенный в памяти файл немедленно будет уничтожен сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-176">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="1c1b7-177">Чтобы выполнить этот пример, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1c1b7-177">To run this example, do the following:</span></span>  
  
1.  <span data-ttu-id="1c1b7-178">Скомпилируйте приложения и откройте три окна командной строки.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-178">Compile the applications and open three Command Prompt windows.</span></span>  
  
2.  <span data-ttu-id="1c1b7-179">В первом окне командной строки запустите `Process A`.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-179">In the first Command Prompt window, run `Process A`.</span></span>  
  
3.  <span data-ttu-id="1c1b7-180">Во втором окне командной строки запустите `Process B`.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-180">In the second Command Prompt window, run `Process B`.</span></span>  
  
4.  <span data-ttu-id="1c1b7-181">Вернитесь к `Process A` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-181">Return to `Process A` and press ENTER.</span></span>  
  
5.  <span data-ttu-id="1c1b7-182">В третьем окне командной строки запустите `Process C`.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-182">In the third Command Prompt window, run `Process C`.</span></span>  
  
6.  <span data-ttu-id="1c1b7-183">Вернитесь к `Process A` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1c1b7-183">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="1c1b7-184">Выходные данные `Process A` выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1c1b7-184">The output of `Process A` is as follows:</span></span>  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="1c1b7-185">**Процесс A**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-185">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="1c1b7-186">**Процесс Б**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-186">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="1c1b7-187">**Процесс C**</span><span class="sxs-lookup"><span data-stu-id="1c1b7-187">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1c1b7-188">См. также</span><span class="sxs-lookup"><span data-stu-id="1c1b7-188">See Also</span></span>  
 [<span data-ttu-id="1c1b7-189">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="1c1b7-189">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
