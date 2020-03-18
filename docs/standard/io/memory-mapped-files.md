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
ms.openlocfilehash: 004da94bc7345bdc294562f0e1bedf6f1735adec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159719"
---
# <a name="memory-mapped-files"></a>Сопоставленные в памяти файлы
Отображаемый в память файл содержит содержимое файла в виртуальной памяти. Отображение файла в области памяти позволяет приложению, содержащему несколько процессов, взаимодействовать с файлом путем чтения этой памяти и записи в нее. Начиная с версии .NET Framework 4, вы можете использовать управляемый код для доступа к отображенным в память файлам тем же способом, что и собственные функции Windows. Описание этого механизма можно найти на странице [Managing Memory-Mapped File](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)) (Управление отображенными в память файлами).  
  
 Есть два типа отображенных в память файлов:  
  
- Постоянные отображенные в память файлы.  
  
     В контексте отображения в память постоянными называются файлы, сопоставленные с исходным файлом на диске. Когда последний процесс завершит работу с таким файлом, все данные сохраняются в исходный файл на диске. Такие отображенные в память файлы удобны для работы с очень большими исходными файлами.  
  
- Непостоянные отображенные в память файлы.  
  
     Непостоянными называются отображенные в память файлы, которые не сопоставлены с файлом на диске. Когда последний процесс закончит работу с таким файлом, данные не сохраняются, а файл удаляется при сборке мусора. Такие файлы позволяют создать общую область памяти для межпроцессного взаимодействия (IPC).  
  
## <a name="processes-views-and-managing-memory"></a>Процессы, представления и управление памятью  
 Отображенные в память файлы можно сделать общими для нескольких процессов. Процессы могут обращаться к одному отображенному в память файлу по единому имени, которое назначается процессом, создающим этот файл.  
  
 Для работы с отображенным в память файлом следует создать представление всего файла или его части. Также вы можете создать несколько представлений для одной части отображенного в память файла, фактически применяя одновременно используемую память. Чтобы два представления оставались согласованными, их нужно создавать из одного отображенного в память файла.  
  
 Несколько представлений потребуются еще и в том случае, если размер файла превышает размер пространства логической памяти, доступной приложению для отображения в память (например, 2 ГБ на 32-разрядном компьютере).  
  
 Есть два типа представлений: представление потокового доступа и представление произвольного доступа. Представления потокового доступа удобны для последовательного доступа к файлу (чаще всего это непостоянные файлы и IPC). Представления произвольного доступа предпочтительны для работы с постоянными файлами.  
  
 Доступ к отображенным в память файлам осуществляется через диспетчер памяти операционной системы, который автоматически разделяет файл на несколько страниц и предоставляет их по мере необходимости. Вам не придется самостоятельно осуществлять управление памятью.  
  
 На следующем изображении показано, как несколько процессов могут одновременно использовать несколько перекрывающихся представлений для одного отображенного в память файла:

 На следующем рисунке показано несколько перекрывающихся представлений для отображенного в память файла:  
  
 ![Снимок экрана с представлениями для отображенного в память файла.](./media/memory-mapped-files/memory-map-persist-file.png)  
  
## <a name="programming-with-memory-mapped-files"></a>Программирование с использованием отображенных в память файлов  
 В следующей таблице содержатся инструкции по использованию объектов и элементов для отображенных в память файлов.  
  
|Задача|Применимые методы или свойства|  
|----------|----------------------------------|  
|Получение объекта <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>, который представляет постоянный файл, отображенный в память из файла на диске.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.|  
|Получение объекта <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>, который представляет непостоянный файл, отображенный в память из файла на диске.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.<br /><br /> — или —<br /><br /> Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.|  
|Получение объекта <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> для уже существующего отображенного в память файла (постоянного или непостоянного).|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.|  
|Получение объекта <xref:System.IO.UnmanagedMemoryStream> для представления последовательного доступа для отображенного в память файла.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.|  
|Получение объекта <xref:System.IO.UnmanagedMemoryAccessor> для представления произвольного доступа для отображенного в память файла.|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.|  
|Получение объекта <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> для использования с неуправляемым кодом.|Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.<br /><br /> — или —<br /><br /> Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.<br /><br /> — или —<br /><br /> Свойство <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.|  
|Задержка распределения памяти до момента, когда будет создано представление (только для непостоянных файлов).<br /><br /> (Чтобы определить текущий размер системной страницы, используйте свойство <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>.)|Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> со значением <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>.<br /><br /> — или —<br /><br /> Методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>, которые принимают в качестве параметра перечисление <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions>.|  
  
### <a name="security"></a>безопасность  
 При создании отображенного в память файла вы можете применить к нему права доступа. Для этого используйте следующие методы, которые принимают в качестве параметра перечисление <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess>:  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 Вы можете указать права доступа для открытия существующего отображенного в память файла, используя методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A>, которые принимают <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> в качестве параметра.  
  
 Кроме того, можно включить объект <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> с предварительно определенными правилами доступа.  
  
 Чтобы применить к отображенному в память файлу новые или измененные правила доступа, используйте метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>. Чтобы получить доступ или проверить правила для существующего файла, используйте метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>.  
  
## <a name="examples"></a>Примеры  
  
### <a name="persisted-memory-mapped-files"></a>Постоянные отображенные в память файлы  
 Метод <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> позволяет создать отображенный в память файл из существующего файла на диске.  
  
 В следующем примере создается отображенное в память представление для части очень большого файла, с которым выполняются определенные действия:  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

 В следующем примере тот же отображенный в память файл открывается для другого процесса:  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a>Непостоянные отображенные в память файлы  
 Методы <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> и <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> позволяют создать отображенный в память файл, который не сопоставлен ни с каким файлом на диске.  
  
 Приведенный ниже пример состоит из трех отдельных процессов (консольных приложений), при которых логические значения записываются в отображенный в память файл. Последовательность действий следующая:  
  
1. `Process A` — создается отображенный в память файл и в него записывается значение.  
  
2. `Process B` — открывается отображенный в память файл и в него записывается значение.  
  
3. `Process C` — открывается отображенный в память файл и в него записывается значение.  
  
4. `Process A` — из отображенного в память файла считываются значения, затем значения отображаются.  
  
5. Когда в `Process A` завершается работа с отображенным в память файлом, он немедленно уничтожается при сборке мусора.  
  
 Чтобы выполнить этот пример, сделайте следующее:  
  
1. Скомпилируйте приложение и откройте три окна командной строки.  
  
2. В первом окне командной строки выполните команду `Process A`.  
  
3. Во втором окне командной строки выполните команду `Process B`.  
  
4. Вернитесь к `Process A` и нажмите клавишу ВВОД.  
  
5. В третьем окне командной строки выполните команду `Process C`.  
  
6. Вернитесь к `Process A` и нажмите клавишу ВВОД.  
  
 Выходные данные `Process A` выглядят следующим образом:  
  
```console  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 **Process A**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 **Process B**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 **Process C**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
