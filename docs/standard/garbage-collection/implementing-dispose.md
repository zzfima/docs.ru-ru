---
title: "Реализация метода Dispose | Microsoft Docs"
ms.custom: ""
ms.date: "04/07/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Dispose - метод"
  - "сборщик мусора, метод Dispose"
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
caps.latest.revision: 44
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 44
---
# Реализация метода Dispose
Вы реализуете метод <xref:System.IDisposable.Dispose%2A> для выпуска неуправляемых ресурсов, которые используются вашим приложением. Сборщик мусора .NET Framework не выделяет и не выпускает неуправляемую память.  
  
 Шаблон удаления объекта, называют [шаблон удаления](../../../docs/standard/design-guidelines/dispose-pattern.md), упорядочивает жизненный цикл объекта. Шаблон удаления используется только для объектов, осуществляющих доступ к неуправляемым ресурсам, таких как дескрипторы файлов и канала, дескрипторы реестра, дескрипторы ожидания и указатели на блоки неуправляемой памяти. Это вызвано тем, что сборщик мусора очень эффективно удаляет неиспользуемые управляемые объекты, но не может удалить неуправляемые объекты.  
  
 Существует два варианта шаблона удаления:  
  
-   Заключение в оболочку каждого неуправляемого ресурса, используемого типом в безопасном дескрипторе (то есть в классе, производном от <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=fullName>). В этом случае необходимо реализовать интерфейс <xref:System.IDisposable> и дополнительный метод `Dispose(Boolean)`. Это рекомендуемый вариант, не требующий переопределения метода <xref:System.Object.Finalize%2A?displayProperty=fullName>.  
  
    > [!NOTE]
    >  Пространство имен The <xref:Microsoft.Win32.SafeHandles?displayProperty=fullName> содержит набор классов, производный от <xref:System.Runtime.InteropServices.SafeHandle>; эти классы перечислены в разделе [Использование безопасных дескрипторов](#SafeHandles). Если не удается найти класс, способный освободить неуправляемый ресурс, можно реализовать собственный подкласс <xref:System.Runtime.InteropServices.SafeHandle>.  
  
-   Необходимо реализовать <xref:System.IDisposable> интерфейс и дополнительный `Dispose(Boolean)` метода, а также переопределение <xref:System.Object.Finalize%2A?displayProperty=fullName> метод. Необходимо переопределить метод <xref:System.Object.Finalize%2A>, чтобы убедиться, что неуправляемые ресурсы удаляются, если реализация <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> не вызывается объектом-получателем типа. При использовании рекомендуемого метода, описанного в предыдущем пункте, класс <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=fullName> делает это от вашего имени.  
  
 Чтобы обеспечить соответствующую очистку ресурсов, метод <xref:System.IDisposable.Dispose%2A> должен быть доступен для многократного вызова без выдачи исключения.  
  
> [!IMPORTANT]
>  Если вы программируете на C++, не реализуют <xref:System.IDisposable.Dispose%2A> метод. Вместо этого следуйте инструкциям в разделе «Деструкторы и методы завершения» [Практическое руководство: определение и использование классов и структур (C + +/ CLI)](../Topic/How%20to:%20Define%20and%20Consume%20Classes%20and%20Structs%20\(C++-CLI\).md). Начиная с .NET Framework 2.0 компилятор C++ поддерживает детерминированную утилизацию ресурсов и не позволяет реализовать <xref:System.IDisposable.Dispose%2A> метод.  
  
 В приведенном для метода <xref:System.GC.KeepAlive%2A?displayProperty=fullName> примере показано, как чрезмерно активная сборка мусора может привести к выполнению финализатора до завершения выполнения утилизируемого объекта. Рекомендуется вызывать <xref:System.GC.KeepAlive%2A> метод в конце большого <xref:System.IDisposable.Dispose%2A> метод.  
  
<a name="Dispose2"></a>   
## <a name="dispose-and-disposeboolean"></a>Dispose() и Dispose(Boolean)  
 Интерфейс <xref:System.IDisposable> требует реализации одного метода <xref:System.IDisposable.Dispose%2A> без параметров. Однако шаблон удаления требует реализации двух методов `Dispose`:  
  
-   Реализация открытого невиртуального (в Visual Basic — `NonInheritable`) метода <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> без параметров.  
  
-   Защищенный виртуальный (в Visual Basic — `Overridable`) метод `Dispose` со следующей подписью:  
  
     [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
     [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]  
  
### <a name="the-dispose-overload"></a>Перегрузка Dispose()  
 Поскольку открытый невиртуальный (`NonInheritable` в Visual Basic) метод `Dispose` без параметров вызывается объектом-получателем типа, его назначение состоит в том, чтобы освободить неуправляемые ресурсы и указать, что метод завершения, если он задан, не должен выполняться. Он имеет стандартную реализацию:  
  
 [!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
 [!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]  
  
 Метод `Dispose` полностью выполняет очистку объектов, поэтому сборщику мусора не требуется вызывать переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=fullName> объекта. Следовательно, вызов <xref:System.GC.SuppressFinalize%2A> метод не позволяет сборщику мусора запустить метод завершения. Если тип не имеет метода завершения, вызов <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> не влияет. Обратите внимание, что фактическая работа по освобождению неуправляемых ресурсов выполняется вторым перегруженным методом `Dispose`.  
  
### <a name="the-disposeboolean-overload"></a>Перегрузка Dispose(Boolean)  
 Во второй перегрузке `disposing` параметр <xref:System.Boolean> , указывающее, является ли метод вызывается из <xref:System.IDisposable.Dispose%2A> метод (его значение равно `true`) или из метода завершения (значение `false`).  
  
 Тело метода состоит из двух блоков кода:  
  
-   Блок, который освобождает неуправляемые ресурсы. Этот блок выполняется вне зависимости от значения параметра `disposing`.  
  
-   Условный блок, который освобождает управляемые ресурсы. Этот блок выполняется, если параметр `disposing` имеет значение `true`. К управляемым ресурсам, которые он освобождает, могут относиться:  
  
     **Управляемые объекты, реализующие <xref:System.IDisposable>.**  
     Условный блок может использоваться для вызова реализации <xref:System.IDisposable.Dispose%2A>. При использовании безопасного дескриптора в качестве оболочки для неуправляемого ресурса необходимо вызвать <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=fullName> реализацию.  
  
     **Управляемые объекты, которые используют большие объемы памяти или дефицитные ресурсы**.  
     При использовании метода `Dispose` эти объекты освобождаются быстрее, чем при недетерминированной очистке сборщиком мусора.  
  
 Если метод вызывается из метода завершения (т. е. если свойство `disposing` имеет значение `false`), выполняется только тот код, который освобождает неуправляемые ресурсы. Поскольку порядок уничтожения управляемых объектов сборщиком мусора во время завершения не определен, вызов этой перегрузки `Dispose` со значением `false` предотвращает попытки метода завершения освободить управляемые ресурсы, которые уже могли быть освобождены.  
  
## <a name="implementing-the-dispose-pattern-for-a-base-class"></a>Реализация шаблона удаления для базового класса  
 При реализации шаблона удаления для базового класса необходимо следующее:  
  
> [!IMPORTANT]
>  Следует реализовать этот шаблон для всех базовых классов, реализующих <xref:System.IDisposable> и не `sealed` (`NotInheritable` в Visual Basic).  
  
-   Реализация <xref:System.IDisposable.Dispose%2A>, которая вызывает метод `Dispose(Boolean)`.  
  
-   Метод `Dispose(Boolean)`, который выполняет фактическую работу по освобождению ресурсов.  
  
-   Любой класс, производный от класса <xref:System.Runtime.InteropServices.SafeHandle>, который создает оболочку для неуправляемого ресурс (рекомендуется), или переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=fullName>. Класс <xref:System.Runtime.InteropServices.SafeHandle> содержит метод завершения, что освобождает разработчика от необходимости создавать его вручную.  
  
 Вот общий шаблон реализации шаблона удаления для базового класса, который использует безопасный дескриптор.  
  
 [!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
 [!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]  
  
> [!NOTE]
>  В предыдущем примере используется объект <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для иллюстрации шаблона. Вместо него может использоваться любой объект, производный от <xref:System.Runtime.InteropServices.SafeHandle>. Обратите внимание, что в этом примере неправильно создаются экземпляры объекта <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.  
  
 Вот общий шаблон реализации шаблона удаления для базового класса, который переопределяет метод <xref:System.Object.Finalize%2A?displayProperty=fullName>.  
  
 [!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
 [!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]  
  
> [!NOTE]
>  Переопределение в C# <xref:System.Object.Finalize%2A?displayProperty=fullName> , определив [деструктор](../Topic/Destructors%20\(C%23%20Programming%20Guide\).md).  
  
## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a>Реализация шаблона удаления для производного класса  
 Класс, производный от класса, реализующего интерфейс <xref:System.IDisposable>, не должен реализовывать интерфейс <xref:System.IDisposable>, поскольку реализация метода <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> базового класса наследуется производными классами. Вместо этого, чтобы реализовать шаблон удаления для базового класса, необходимо следующее:  
  
-   Метод `protected``Dispose(Boolean)`, который переопределяет метод базового класса и выполняет фактическую работу по освобождению ресурсов производного класса. Этот метод должен также вызывать метод `Dispose(Boolean)` базового класса и передавать в него значение `true` для аргумента `disposing`.  
  
-   Любой класс, производный от класса <xref:System.Runtime.InteropServices.SafeHandle>, который создает оболочку для неуправляемого ресурс (рекомендуется), или переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=fullName>. Класс <xref:System.Runtime.InteropServices.SafeHandle> содержит метод завершения, что освобождает разработчика от необходимости создавать его вручную. Если есть метод завершения, он должен вызывать перегруженный метод `Dispose(Boolean)`, указывая при этом аргумент `disposing` со значением `false`.  
  
 Вот общий шаблон реализации шаблона удаления для производного класса, который использует безопасный дескриптор:  
  
 [!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
 [!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]  
  
> [!NOTE]
>  В предыдущем примере используется объект <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для иллюстрации шаблона. Вместо него может использоваться любой объект, производный от <xref:System.Runtime.InteropServices.SafeHandle>. Обратите внимание, что в этом примере неправильно создаются экземпляры объекта <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.  
  
 Вот общий шаблон реализации шаблона удаления для производного класса, который переопределяет метод <xref:System.Object.Finalize%2A?displayProperty=fullName>:  
  
 [!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
 [!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]  
  
> [!NOTE]
>  Переопределение в C# <xref:System.Object.Finalize%2A?displayProperty=fullName> , определив [деструктор](../Topic/Destructors%20\(C%23%20Programming%20Guide\).md).  
  
<a name="SafeHandles"></a>   
## <a name="using-safe-handles"></a>Использование безопасных дескрипторов  
 Написание кода для метода завершения объекта является сложной задачей, которая может вызвать проблемы при неправильном выполнении. Поэтому вместо реализации метода завершения рекомендуется создавать объекты <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=fullName>.  
  
 Классы, производные от класса <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=fullName>, упрощают проблемы времени существования объекта путем назначения и освобождения дескрипторов без прерываний. Они содержат критический метод завершения, который обязательно выполняется во время выгрузки домена приложения. Дополнительные сведения о преимуществах использования безопасного дескриптора см. в разделе <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=fullName>. Безопасные дескрипторы предоставляются следующими производными классами в пространстве имен <xref:Microsoft.Win32.SafeHandles>:  
  
-   Классы <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> и <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> для файлов, сопоставленных в памяти файлов и каналов.  
  
-   Класс <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> для представлений памяти.  
  
-   Классы <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> и <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> для конструкций шифрования.  
  
-   Класс <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> для разделов реестра.  
  
-   Класс <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> для дескрипторов ожидания.  
  
<a name="base"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a>Использование безопасного дескриптора для реализации шаблона удаления для базового класса  
 В следующем примере показан шаблон удаления для базового класса `DisposableStreamResource`, который использует безопасный дескриптор для инкапсуляции неуправляемых ресурсов. Он определяет класс `DisposableResource`, который использует <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для создания экземпляра объекта <xref:System.IO.Stream>, который представляет открытый файл. Метод `DisposableResource` также включает свойство `Size`, которое возвращает общее количество байтов в файловом потоке.  
  
 [!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
 [!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]  
  
<a name="derived"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a>Использование безопасного дескриптора для реализации шаблона удаления для производного класса  
 В следующем примере показан шаблон удаления для производного класса `DisposableStreamResource2`, унаследованного от класса `DisposableStreamResource`, представленного в предыдущем примере. Класс добавляет дополнительный метод `WriteFileInfo` и использует объект <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для создания экземпляра дескриптора записываемого файла.  
  
 [!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
 [!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.GC.SuppressFinalize%2A>   
 <xref:System.IDisposable>   
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>   
 <xref:Microsoft.Win32.SafeHandles>   
 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=fullName>   
 <xref:System.Object.Finalize%2A?displayProperty=fullName>   
 [Практическое руководство: определение и использование классов и структур (C + +/ CLI)](../Topic/How%20to:%20Define%20and%20Consume%20Classes%20and%20Structs%20\(C++-CLI\).md)   
 [Шаблон удаления](../../../docs/standard/design-guidelines/dispose-pattern.md)