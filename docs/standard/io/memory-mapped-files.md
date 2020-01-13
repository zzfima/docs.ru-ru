---
title: Сопоставленные в памяти файлы
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- memory-mapped files
- inter-process communication
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
ms.openlocfilehash: add109e285dfc435a3d4fd7753fb647e28a6a2fd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706573"
---
# <a name="memory-mapped-files"></a><span data-ttu-id="b8d13-102">Сопоставленные в памяти файлы</span><span class="sxs-lookup"><span data-stu-id="b8d13-102">Memory-Mapped Files</span></span>
<span data-ttu-id="b8d13-103">Отображаемый в память файл содержит содержимое файла в виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="b8d13-103">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="b8d13-104">Отображение файла в области памяти позволяет приложению, содержащему несколько процессов, взаимодействовать с файлом путем чтения этой памяти и записи в нее.</span><span class="sxs-lookup"><span data-stu-id="b8d13-104">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="b8d13-105">Начиная с версии .NET Framework 4, вы можете использовать управляемый код для доступа к отображенным в память файлам тем же способом, что и собственные функции Windows. Описание этого механизма можно найти на странице [Managing Memory-Mapped File](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)) (Управление отображенными в память файлами).</span><span class="sxs-lookup"><span data-stu-id="b8d13-105">Starting with the .NET Framework 4, you can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="b8d13-106">Есть два типа отображенных в память файлов:</span><span class="sxs-lookup"><span data-stu-id="b8d13-106">There are two types of memory-mapped files:</span></span>  
  
- <span data-ttu-id="b8d13-107">Постоянные отображенные в память файлы.</span><span class="sxs-lookup"><span data-stu-id="b8d13-107">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="b8d13-108">В контексте отображения в память постоянными называются файлы, сопоставленные с исходным файлом на диске.</span><span class="sxs-lookup"><span data-stu-id="b8d13-108">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="b8d13-109">Когда последний процесс завершит работу с таким файлом, все данные сохраняются в исходный файл на диске.</span><span class="sxs-lookup"><span data-stu-id="b8d13-109">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="b8d13-110">Такие отображенные в память файлы удобны для работы с очень большими исходными файлами.</span><span class="sxs-lookup"><span data-stu-id="b8d13-110">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
- <span data-ttu-id="b8d13-111">Непостоянные отображенные в память файлы.</span><span class="sxs-lookup"><span data-stu-id="b8d13-111">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="b8d13-112">Непостоянными называются отображенные в память файлы, которые не сопоставлены с файлом на диске.</span><span class="sxs-lookup"><span data-stu-id="b8d13-112">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="b8d13-113">Когда последний процесс закончит работу с таким файлом, данные не сохраняются, а файл удаляется при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="b8d13-113">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="b8d13-114">Такие файлы позволяют создать общую область памяти для межпроцессного взаимодействия (IPC).</span><span class="sxs-lookup"><span data-stu-id="b8d13-114">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="b8d13-115">Процессы, представления и управление памятью</span><span class="sxs-lookup"><span data-stu-id="b8d13-115">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="b8d13-116">Отображенные в память файлы можно сделать общими для нескольких процессов.</span><span class="sxs-lookup"><span data-stu-id="b8d13-116">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="b8d13-117">Процессы могут обращаться к одному отображенному в память файлу по единому имени, которое назначается процессом, создающим этот файл.</span><span class="sxs-lookup"><span data-stu-id="b8d13-117">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="b8d13-118">Для работы с отображенным в память файлом следует создать представление всего файла или его части.</span><span class="sxs-lookup"><span data-stu-id="b8d13-118">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="b8d13-119">Также вы можете создать несколько представлений для одной части отображенного в память файла, фактически применяя одновременно используемую память.</span><span class="sxs-lookup"><span data-stu-id="b8d13-119">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="b8d13-120">Чтобы два представления оставались согласованными, их нужно создавать из одного отображенного в память файла.</span><span class="sxs-lookup"><span data-stu-id="b8d13-120">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="b8d13-121">Несколько представлений потребуются еще и в том случае, если размер файла превышает размер пространства логической памяти, доступной приложению для отображения в память (например, 2 ГБ на 32-разрядном компьютере).</span><span class="sxs-lookup"><span data-stu-id="b8d13-121">Multiple views may also be necessary if the file is greater than the size of the application’s logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="b8d13-122">Есть два типа представлений: представление потокового доступа и представление произвольного доступа.</span><span class="sxs-lookup"><span data-stu-id="b8d13-122">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="b8d13-123">Представления потокового доступа удобны для последовательного доступа к файлу (чаще всего это непостоянные файлы и IPC).</span><span class="sxs-lookup"><span data-stu-id="b8d13-123">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="b8d13-124">Представления произвольного доступа предпочтительны для работы с постоянными файлами.</span><span class="sxs-lookup"><span data-stu-id="b8d13-124">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="b8d13-125">Доступ к отображенным в память файлам осуществляется через диспетчер памяти операционной системы, который автоматически разделяет файл на несколько страниц и предоставляет их по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b8d13-125">Memory-mapped files are accessed through the operating system’s memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="b8d13-126">Вам не придется самостоятельно осуществлять управление памятью.</span><span class="sxs-lookup"><span data-stu-id="b8d13-126">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="b8d13-127">На следующем изображении показано, как несколько процессов могут одновременно использовать несколько перекрывающихся представлений для одного отображенного в память файла:</span><span class="sxs-lookup"><span data-stu-id="b8d13-127">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>

 <span data-ttu-id="b8d13-128">На следующем рисунке показано несколько перекрывающихся представлений для отображенного в память файла:</span><span class="sxs-lookup"><span data-stu-id="b8d13-128">The following image shows multiple and overlapped views to a memory-mapped file:</span></span>  
  
 ![Снимок экрана с представлениями для отображенного в память файла.](./media/memory-mapped-files/memory-map-persist-file.png)  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="b8d13-130">Программирование с использованием отображенных в память файлов</span><span class="sxs-lookup"><span data-stu-id="b8d13-130">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="b8d13-131">В следующей таблице содержатся инструкции по использованию объектов и элементов для отображенных в память файлов.</span><span class="sxs-lookup"><span data-stu-id="b8d13-131">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="b8d13-132">Задача</span><span class="sxs-lookup"><span data-stu-id="b8d13-132">Task</span></span>|<span data-ttu-id="b8d13-133">Применимые методы или свойства</span><span class="sxs-lookup"><span data-stu-id="b8d13-133">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="b8d13-134">Получение объекта <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>, который представляет постоянный файл, отображенный в память из файла на диске.</span><span class="sxs-lookup"><span data-stu-id="b8d13-134">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="b8d13-135">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="b8d13-136">Получение объекта <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>, который представляет непостоянный файл, отображенный в память из файла на диске.</span><span class="sxs-lookup"><span data-stu-id="b8d13-136">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="b8d13-137">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="b8d13-138">-или-</span><span class="sxs-lookup"><span data-stu-id="b8d13-138">- or -</span></span><br /><br /> <span data-ttu-id="b8d13-139">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="b8d13-140">Получение объекта <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> для уже существующего отображенного в память файла (постоянного или непостоянного).</span><span class="sxs-lookup"><span data-stu-id="b8d13-140">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="b8d13-141">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="b8d13-142">Получение объекта <xref:System.IO.UnmanagedMemoryStream> для представления последовательного доступа для отображенного в память файла.</span><span class="sxs-lookup"><span data-stu-id="b8d13-142">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="b8d13-143">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="b8d13-144">Получение объекта <xref:System.IO.UnmanagedMemoryAccessor> для представления произвольного доступа для отображенного в память файла.</span><span class="sxs-lookup"><span data-stu-id="b8d13-144">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="b8d13-145">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="b8d13-146">Получение объекта <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> для использования с неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="b8d13-146">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="b8d13-147">Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="b8d13-148">-или-</span><span class="sxs-lookup"><span data-stu-id="b8d13-148">- or -</span></span><br /><br /> <span data-ttu-id="b8d13-149">Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="b8d13-150">-или-</span><span class="sxs-lookup"><span data-stu-id="b8d13-150">- or -</span></span><br /><br /> <span data-ttu-id="b8d13-151">Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="b8d13-152">Задержка распределения памяти до момента, когда будет создано представление (только для непостоянных файлов).</span><span class="sxs-lookup"><span data-stu-id="b8d13-152">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="b8d13-153">(Чтобы определить текущий размер системной страницы, используйте свойство <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="b8d13-153">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="b8d13-154">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> со значением <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="b8d13-155">-или-</span><span class="sxs-lookup"><span data-stu-id="b8d13-155">- or -</span></span><br /><br /> <span data-ttu-id="b8d13-156">Методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>, которые принимают в качестве параметра перечисление <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="b8d13-157">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b8d13-157">Security</span></span>  
 <span data-ttu-id="b8d13-158">При создании отображенного в память файла вы можете применить к нему права доступа. Для этого используйте следующие методы, которые принимают в качестве параметра перечисление <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess>:</span><span class="sxs-lookup"><span data-stu-id="b8d13-158">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="b8d13-159">Вы можете указать права доступа для открытия существующего отображенного в память файла, используя методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A>, которые принимают <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="b8d13-159">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="b8d13-160">Кроме того, можно включить объект <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> с предварительно определенными правилами доступа.</span><span class="sxs-lookup"><span data-stu-id="b8d13-160">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="b8d13-161">Чтобы применить к отображенному в память файлу новые или измененные правила доступа, используйте метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-161">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="b8d13-162">Чтобы получить доступ или проверить правила для существующего файла, используйте метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8d13-162">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b8d13-163">Примеры</span><span class="sxs-lookup"><span data-stu-id="b8d13-163">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="b8d13-164">Постоянные отображенные в память файлы</span><span class="sxs-lookup"><span data-stu-id="b8d13-164">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="b8d13-165">Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> позволяет создать отображенный в память файл из существующего файла на диске.</span><span class="sxs-lookup"><span data-stu-id="b8d13-165">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="b8d13-166">В следующем примере создается отображенное в память представление для части очень большого файла, с которым выполняются определенные действия:</span><span class="sxs-lookup"><span data-stu-id="b8d13-166">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 <span data-ttu-id="b8d13-167">В следующем примере тот же отображенный в память файл открывается для другого процесса:</span><span class="sxs-lookup"><span data-stu-id="b8d13-167">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="b8d13-168">Непостоянные отображенные в память файлы</span><span class="sxs-lookup"><span data-stu-id="b8d13-168">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="b8d13-169">Методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> и <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> позволяют создать отображенный в память файл, который не сопоставлен ни с каким файлом на диске.</span><span class="sxs-lookup"><span data-stu-id="b8d13-169">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="b8d13-170">Приведенный ниже пример состоит из трех отдельных процессов (консольных приложений), при которых логические значения записываются в отображенный в память файл.</span><span class="sxs-lookup"><span data-stu-id="b8d13-170">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="b8d13-171">Последовательность действий следующая:</span><span class="sxs-lookup"><span data-stu-id="b8d13-171">The following sequence of actions occur:</span></span>  
  
1. <span data-ttu-id="b8d13-172">`Process A` — создается отображенный в память файл и в него записывается значение.</span><span class="sxs-lookup"><span data-stu-id="b8d13-172">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2. <span data-ttu-id="b8d13-173">`Process B` — открывается отображенный в память файл и в него записывается значение.</span><span class="sxs-lookup"><span data-stu-id="b8d13-173">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3. <span data-ttu-id="b8d13-174">`Process C` — открывается отображенный в память файл и в него записывается значение.</span><span class="sxs-lookup"><span data-stu-id="b8d13-174">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4. <span data-ttu-id="b8d13-175">`Process A` — из отображенного в память файла считываются значения, затем значения отображаются.</span><span class="sxs-lookup"><span data-stu-id="b8d13-175">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5. <span data-ttu-id="b8d13-176">Когда в `Process A` завершается работа с отображенным в память файлом, он немедленно уничтожается при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="b8d13-176">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="b8d13-177">Чтобы выполнить этот пример, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="b8d13-177">To run this example, do the following:</span></span>  
  
1. <span data-ttu-id="b8d13-178">Скомпилируйте приложение и откройте три окна командной строки.</span><span class="sxs-lookup"><span data-stu-id="b8d13-178">Compile the applications and open three Command Prompt windows.</span></span>  
  
2. <span data-ttu-id="b8d13-179">В первом окне командной строки выполните команду `Process A`.</span><span class="sxs-lookup"><span data-stu-id="b8d13-179">In the first Command Prompt window, run `Process A`.</span></span>  
  
3. <span data-ttu-id="b8d13-180">Во втором окне командной строки выполните команду `Process B`.</span><span class="sxs-lookup"><span data-stu-id="b8d13-180">In the second Command Prompt window, run `Process B`.</span></span>  
  
4. <span data-ttu-id="b8d13-181">Вернитесь к `Process A` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b8d13-181">Return to `Process A` and press ENTER.</span></span>  
  
5. <span data-ttu-id="b8d13-182">В третьем окне командной строки выполните команду `Process C`.</span><span class="sxs-lookup"><span data-stu-id="b8d13-182">In the third Command Prompt window, run `Process C`.</span></span>  
  
6. <span data-ttu-id="b8d13-183">Вернитесь к `Process A` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b8d13-183">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="b8d13-184">Выходные данные `Process A` выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b8d13-184">The output of `Process A` is as follows:</span></span>  
  
```console  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="b8d13-185">**Process A**</span><span class="sxs-lookup"><span data-stu-id="b8d13-185">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="b8d13-186">**Process B**</span><span class="sxs-lookup"><span data-stu-id="b8d13-186">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="b8d13-187">**Process C**</span><span class="sxs-lookup"><span data-stu-id="b8d13-187">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b8d13-188">См. также</span><span class="sxs-lookup"><span data-stu-id="b8d13-188">See also</span></span>

- [<span data-ttu-id="b8d13-189">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="b8d13-189">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
