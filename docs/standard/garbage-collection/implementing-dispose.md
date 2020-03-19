---
title: Реализация метода Dispose
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: f3d3269ccf56954f963762503d2bc1c53b9e6b83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78238992"
---
# <a name="implementing-a-dispose-method"></a>Реализация метода Dispose

Реализация метода <xref:System.IDisposable.Dispose%2A> необходима для освобождения неуправляемых ресурсов, которые использует ваше приложение. Сборщик мусора .NET не выделяет и не освобождает неуправляемую память.  
  
Шаблон ликвидации объекта, именуемый также [шаблоном удаления](implementing-dispose.md), налагает определенные правила на время жизни объекта. Шаблон удаления используется только для объектов, осуществляющих доступ к неуправляемым ресурсам, таких как дескрипторы файлов и каналов, дескрипторы реестра, дескрипторы ожидания и указатели на блоки неуправляемой памяти. Это вызвано тем, что сборщик мусора очень эффективно удаляет неиспользуемые управляемые объекты, но не может удалить неуправляемые объекты.  
  
Существует два варианта шаблона удаления:  
  
- Заключение в оболочку каждого неуправляемого ресурса, используемого типом в безопасном дескрипторе (то есть в классе, производном от <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>). В этом случае необходимо реализовать интерфейс <xref:System.IDisposable> и дополнительный метод `Dispose(Boolean)`. Это рекомендуемый вариант, не требующий переопределения метода <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.  
  
  > [!NOTE]
  > Пространство имен <xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> содержит набор классов, производных от <xref:System.Runtime.InteropServices.SafeHandle>. Эти классы перечислены в разделе [Использование безопасных дескрипторов](#SafeHandles). Если не удается найти класс, способный освободить неуправляемый ресурс, можно реализовать собственный подкласс <xref:System.Runtime.InteropServices.SafeHandle>.  
  
- Реализация интерфейса <xref:System.IDisposable> и дополнительного метода `Dispose(Boolean)`, а также переопределение метода <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Необходимо переопределить метод <xref:System.Object.Finalize%2A>, чтобы убедиться, что неуправляемые ресурсы удаляются, если реализация <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> не вызывается объектом-получателем типа. При использовании рекомендуемого метода, описанного в предыдущем пункте, класс <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> делает это от вашего имени.  
  
Чтобы обеспечить соответствующую очистку ресурсов, метод <xref:System.IDisposable.Dispose%2A> должен быть доступен для многократного вызова без выдачи исключения.  
  
В приведенном для метода <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> примере показано, как сборка мусора может привести к выполнению метода завершения, в то время как по-прежнему будет использоваться неуправляемая ссылка на объект или его члены. Возможно, имеет смысл использовать <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType>, чтобы запретить сборку мусора для объекта с момента начала текущей процедуры до вызова этого метода.
  
<a name="Dispose2"></a>
## <a name="dispose-and-disposeboolean"></a>Dispose() и Dispose(Boolean)  

Интерфейс <xref:System.IDisposable> требует реализации одного метода <xref:System.IDisposable.Dispose%2A> без параметров. Однако шаблон удаления требует реализации двух методов `Dispose`:  
  
- Реализация открытого невиртуального (в Visual Basic — `NonInheritable`) метода <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> без параметров.  
  
- Защищенный виртуальный (в Visual Basic — `Overridable`) метод `Dispose` со следующей подписью:  
  
  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]  
  
### <a name="the-dispose-overload"></a>Перегрузка Dispose()

Поскольку открытый невиртуальный (`NonInheritable` в Visual Basic) метод `Dispose` без параметров вызывается объектом-получателем типа, его назначение состоит в том, чтобы освободить неуправляемые ресурсы и указать, что метод завершения, если он задан, не должен выполняться. Он имеет стандартную реализацию:  
  
[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]  
  
Метод `Dispose` полностью выполняет очистку объектов, поэтому сборщику мусора не требуется вызывать переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Таким образом, вызов метода <xref:System.GC.SuppressFinalize%2A> не позволит сборщику мусора запустить метод завершения. Если тип не имеет метода завершения, вызов метода <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> не производит эффекта. Обратите внимание, что фактическая работа по освобождению неуправляемых ресурсов выполняется вторым перегруженным методом `Dispose`.  
  
### <a name="the-disposeboolean-overload"></a>Перегрузка Dispose(Boolean)

Во второй перегрузке *disposing* используется параметр типа <xref:System.Boolean>, который указывает, откуда осуществляется вызов метода: из метода <xref:System.IDisposable.Dispose%2A> (значение `true`) или из метода завершения (значение `false`).  
  
Тело метода состоит из двух блоков кода:  
  
- Блок, который освобождает неуправляемые ресурсы. Этот блок выполняется вне зависимости от значения параметра `disposing`.  
  
- Условный блок, который освобождает управляемые ресурсы. Этот блок выполняется, если параметр `disposing` имеет значение `true`. К управляемым ресурсам, которые он освобождает, могут относиться:  
  
  **Управляемые объекты, реализующие <xref:System.IDisposable>.** Условный блок может использоваться для вызова реализации <xref:System.IDisposable.Dispose%2A>. При использовании безопасного дескриптора в качестве оболочки для неуправляемого ресурса необходимо вызвать реализацию <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType>.  
  
  **Управляемые объекты, которые используют большие объемы памяти или дефицитные ресурсы**. При использовании метода `Dispose` эти объекты освобождаются быстрее, чем при недетерминированной очистке сборщиком мусора.  
  
Если метод вызывается из метода завершения (т. е. если свойство *disposing* имеет значение `false`), выполняется только тот код, который освобождает неуправляемые ресурсы. Поскольку порядок уничтожения управляемых объектов сборщиком мусора во время завершения не определен, вызов этой перегрузки `Dispose` со значением `false` предотвращает попытки метода завершения освободить управляемые ресурсы, которые уже могли быть освобождены.  
  
## <a name="implementing-the-dispose-pattern-for-a-base-class"></a>Реализация шаблона удаления для базового класса

При реализации шаблона удаления для базового класса необходимо следующее:  
  
> [!IMPORTANT]
> Вам следует реализовать этот шаблон для всех базовых классов, которые реализуют <xref:System.IDisposable.Dispose> и не являются `sealed` (`NotInheritable` в Visual Basic).  
  
- Реализация <xref:System.IDisposable.Dispose%2A>, которая вызывает метод `Dispose(Boolean)`.  
  
- Метод `Dispose(Boolean)`, который выполняет фактическую работу по освобождению ресурсов.  
  
- Любой класс, производный от класса <xref:System.Runtime.InteropServices.SafeHandle>, который создает оболочку для неуправляемого ресурс (рекомендуется), или переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Класс <xref:System.Runtime.InteropServices.SafeHandle> содержит метод завершения, что освобождает разработчика от необходимости создавать его вручную.  
  
Вот общий шаблон реализации шаблона удаления для базового класса, который использует безопасный дескриптор.  
  
[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]  
  
> [!NOTE]
> В предыдущем примере используется объект <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для иллюстрации шаблона. Вместо него может использоваться любой объект, производный от <xref:System.Runtime.InteropServices.SafeHandle>. Обратите внимание, что в этом примере неправильно создаются экземпляры объекта <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.  
  
Вот общий шаблон реализации шаблона удаления для базового класса, который переопределяет метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.  
  
[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]  
  
> [!NOTE]
> В C# переопределение <xref:System.Object.Finalize%2A?displayProperty=nameWithType> выполняется путем определения [деструктора](../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a>Реализация шаблона удаления для производного класса

Класс, производный от класса, реализующего интерфейс <xref:System.IDisposable>, не должен реализовывать интерфейс <xref:System.IDisposable>, поскольку реализация метода <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> базового класса наследуется производными классами. Вместо этого для высвобождения ресурсов производного класса необходимо предоставить следующее.  
  
- Метод `protected Dispose(Boolean)`, который переопределяет метод базового класса и выполняет фактическую работу по освобождению ресурсов производного класса. Этот метод должен также вызвать метод `Dispose(Boolean)` базового класса и передать состояние удаления ресурса в качестве аргумента.  
  
- Любой класс, производный от класса <xref:System.Runtime.InteropServices.SafeHandle>, который создает оболочку для неуправляемого ресурс (рекомендуется), или переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Класс <xref:System.Runtime.InteropServices.SafeHandle> содержит метод завершения, что освобождает разработчика от необходимости создавать его вручную. Если есть метод завершения, он должен вызывать перегруженный метод `Dispose(Boolean)`, указывая при этом аргумент *disposing* со значением `false`.  
  
Вот общий шаблон реализации шаблона удаления для производного класса, который использует безопасный дескриптор:  
  
[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]  
  
> [!NOTE]
> В предыдущем примере используется объект <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для иллюстрации шаблона. Вместо него может использоваться любой объект, производный от <xref:System.Runtime.InteropServices.SafeHandle>. Обратите внимание, что в этом примере неправильно создаются экземпляры объекта <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.  
  
Вот общий шаблон реализации шаблона удаления для производного класса, который переопределяет метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:  
  
[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]  
  
> [!NOTE]
> В C# переопределение <xref:System.Object.Finalize%2A?displayProperty=nameWithType> выполняется путем определения [деструктора](../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
<a name="SafeHandles"></a>
## <a name="using-safe-handles"></a>Использование безопасных дескрипторов

Написание кода для метода завершения объекта является сложной задачей, которая может вызвать проблемы при неправильном выполнении. Поэтому вместо реализации метода завершения рекомендуется создавать объекты <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>.  
  
Классы, производные от класса <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>, упрощают проблемы времени существования объекта путем назначения и освобождения дескрипторов без прерываний. Они содержат критический метод завершения, который обязательно выполняется во время выгрузки домена приложения. Дополнительные сведения о преимуществах использования безопасного дескриптора см. в разделе <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>. Безопасные дескрипторы предоставляются следующими производными классами в пространстве имен <xref:Microsoft.Win32.SafeHandles>:  
  
- Классы <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> и <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> — для файлов, файлов сопоставления памяти и каналов.  
  
- Класс <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> — для представлений памяти.  
  
- Классы <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> и <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> — для конструкций шифрования.  
  
- Класс <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> — для разделов реестра.  
  
- Класс <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> — для дескрипторов ожидания.  
  
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

- <xref:System.GC.SuppressFinalize%2A>
- <xref:System.IDisposable>
- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>
- <xref:Microsoft.Win32.SafeHandles>
- <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>
- [Практическое руководство. Определение и использование классов и структур (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
- [Шаблон ликвидации](implementing-dispose.md)
