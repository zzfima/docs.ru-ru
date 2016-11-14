---
title: "Реализация метода dispose"
description: "Реализация метода dispose"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: eca6cdc3-6a14-4296-86fb-1eb2f21455b0
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: dfe2cebfbcf1f4c2697683ebda8c1e11567fd015

---

# <a name="implementing-a-dispose-method"></a>Реализация метода dispose

Вы реализуете метод [Dispose](xref:System.IDisposable.Dispose) для выпуска неуправляемых ресурсов, которые используются вашим приложением. Сборщик мусора .NET не выделяет и не выпускает неуправляемую память. 

Шаблон удаления объекта упорядочивает жизненный цикл этого объекта. Шаблон удаления используется только для объектов, осуществляющих доступ к неуправляемым ресурсам, таких как дескрипторы файлов и канала, дескрипторы реестра, дескрипторы ожидания и указатели на блоки неуправляемой памяти. Это вызвано тем, что сборщик мусора очень эффективно удаляет неиспользуемые управляемые объекты, но не может удалить неуправляемые объекты.

Существует два варианта шаблона удаления:

* Заключение в оболочку каждого неуправляемого ресурса, используемого типом в безопасном дескрипторе (то есть в классе, производном от [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)). В этом случае необходимо реализовать интерфейс [IDisposable](xref:System.IDisposable) и дополнительный метод `Dispose(Boolean)`. Это рекомендуемый вариант, не требующий переопределения метода [Object.Finalize](xref:System.Object.Finalize). 

> [!NOTE]
> Пространство имен The [Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles) содержит набор классов, производный от [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle); эти классы перечислены в разделе [Использование безопасных дескрипторов](#using-safe-handles). Если не удается найти класс, способный освободить неуправляемый ресурс, можно реализовать собственный подкласс [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle). 
 
* Реализация интерфейса [IDisposable](xref:System.IDisposable) и дополнительного метода `Dispose(Boolean`, а также переопределение метода [Object.Finalize](xref:System.Object.Finalize). Необходимо переопределить метод [Finalize](xref:System.Object.Finalize), чтобы убедиться, что неуправляемые ресурсы удаляются, если реализация [IDisposable.Dispose](xref:System.IDisposable.Dispose) не вызывается объектом-получателем типа. При использовании рекомендуемого метода, описанного в предыдущем пункте, класс [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) делает это от вашего имени. 

Чтобы обеспечить соответствующую очистку ресурсов, метод [Dispose](xref:System.IDisposable.Dispose) должен быть доступен для многократного вызова без выдачи исключения. 

В приведенном для метода [GC.KeepAlive](xref:System.GC.KeepAlive(System.Object)) примере показано, как чрезмерно активная сборка мусора может привести к выполнению финализатора до завершения выполнения утилизируемого объекта. Рекомендуется вызывать метод [KeepAlive](xref:System.GC.KeepAlive(System.Object)) в конце большого метода `Dispose`.

## <a name="dispose-and-disposeboolean"></a>Dispose() и Dispose(Boolean)

Интерфейс [IDisposable](xref:System.IDisposable) требует реализации одного метода [Dispose](xref:System.IDisposable.Dispose) без параметров. Однако шаблон удаления требует реализации двух методов `Dispose`: 

* Реализация открытого невиртуального (в Visual Basic — `NonInheritable`) метода [IDisposable.Dispose](xref:System.IDisposable.Dispose) без параметров.

* Защищенный виртуальный (в Visual Basic — `Overridable`) метод `Dispose` со следующей подписью:

  ```cs
  protected virtual void Dispose(bool disposing)
  ```

  ```vb
  Protected Overridable Sub Dispose(disposing As Boolean)
  ```

### <a name="the-dispose-overload"></a>Перегрузка Dispose()

Поскольку открытый невиртуальный (`NonInheritable` в Visual Basic) метод `Dispose` без параметров вызывается объектом-получателем типа, его назначение состоит в том, чтобы освободить неуправляемые ресурсы и указать, что метод завершения, если он задан, не должен выполняться. Он имеет стандартную реализацию:

```cs
public void Dispose()
{
   // Dispose of unmanaged resources.
   Dispose(true);
   // Suppress finalization.
   GC.SuppressFinalize(this);
}
```

```vb
Public Sub Dispose() _
           Implements IDisposable.Dispose
   ' Dispose of unmanaged resources.
   Dispose(True)
   ' Suppress finalization.
   GC.SuppressFinalize(Me)
End Sub
```

Метод `Dispose` полностью выполняет очистку объектов, поэтому сборщику мусора не требуется вызывать переопределенный метод [Object.Finalize](xref:System.Object.Finalize) объекта. Таким образом, вызов метода [GC.SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object)) не позволит сборщику мусора запустить метод завершения. Если тип не имеет метода завершения, вызов метода [SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object)) не имеет силы. Обратите внимание, что фактическая работа по освобождению неуправляемых ресурсов выполняется вторым перегруженным методом `Dispose`.

### <a name="the-disposeboolean-overload"></a>Перегрузка Dispose(Boolean)

Во второй перегрузке параметр *disposing* типа [Boolean](xref:System.Boolean) указывает, откуда осуществляется вызов метода: из метода [Dispose](xref:System.IDisposable.Dispose) (значение `true`) или из метода завершения (значение `false`). 

Тело метода состоит из двух блоков кода: 

* Блок, который освобождает неуправляемые ресурсы. Этот блок выполняется вне зависимости от значения параметра *disposing*. 

* Условный блок, который освобождает управляемые ресурсы. Этот блок выполняется, если параметр *disposing* имеет значение `true`. К управляемым ресурсам, которые он освобождает, могут относиться: 

    **Управляемые объекты, реализующие интерфейс IDisposable**. Условный блок может использоваться для вызова реализации [Dispose](xref:System.IDisposable.Dispose). При использовании безопасного дескриптора в качестве оболочки для неуправляемого ресурса необходимо вызвать реализацию [SafeHandle.Dispose(Boolean)](xref:System.Runtime.InteropServices.SafeHandle.Dispose(System.Boolean)). 

    **Управляемые объекты, которые используют большие объемы памяти или дефицитные ресурсы**. При использовании метода `Dispose` эти объекты освобождаются быстрее, чем при недетерминированной очистке сборщиком мусора. 


Если метод вызывается из метода завершения (т. е. если свойство *disposing* имеет значение `false`), выполняется только тот код, который освобождает неуправляемые ресурсы. Поскольку порядок уничтожения управляемых объектов сборщиком мусора во время завершения не определен, вызов этой перегрузки `Dispose` со значением `false` предотвращает попытки метода завершения освободить управляемые ресурсы, которые уже могли быть освобождены. 

## <a name="implementing-the-dispose-pattern-for-a-base-class"></a>Реализация шаблона удаления для базового класса

При реализации шаблона удаления для базового класса необходимо следующее: 

> [!IMPORTANT]
> Вам следует реализовать этот шаблон для всех базовых классов, которые реализуют [IDisposable](xref:System.IDisposable) и не являются `sealed`. 
 
* Реализация [Dispose](xref:System.IDisposable.Dispose), которая вызывает метод `Dispose(Boolean)`. 

* Метод `Dispose(Boolean)`, который выполняет фактическую работу по освобождению ресурсов. 

* Любой класс, производный от класса [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle), который создает оболочку для неуправляемого ресурс (рекомендуется), или переопределенный метод [Object.Finalize](xref:System.Object.Finalize). Класс [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) содержит метод завершения, что освобождает разработчика от необходимости создавать его вручную. 

Вот общий шаблон реализации шаблона удаления для базового класса, который использует безопасный дескриптор. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.Runtime.InteropServices;

class BaseClass : IDisposable
{
   // Flag: Has Dispose already been called?
   bool disposed = false;
   // Instantiate a SafeHandle instance.
   SafeHandle handle = new SafeFileHandle(IntPtr.Zero, true);

   // Public implementation of Dispose pattern callable by consumers.
   public void Dispose()
   { 
      Dispose(true);
      GC.SuppressFinalize(this);           
   }

   // Protected implementation of Dispose pattern.
   protected virtual void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         handle.Dispose();
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.Runtime.InteropServices

Class BaseClass : Implements IDisposable
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False
   ' Instantiate a SafeHandle instance.
   Dim handle As SafeHandle = New SafeFileHandle(IntPtr.Zero, True)

   ' Public implementation of Dispose pattern callable by consumers.
   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)           
   End Sub

   ' Protected implementation of Dispose pattern.
   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         handle.Dispose()
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True
   End Sub
End Class
```

> [!NOTE] 
> В предыдущем примере используется объект [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) для иллюстрации шаблона. Вместо него может использоваться любой объект, производный от [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle). Обратите внимание, что в этом примере неправильно создаются экземпляры объекта [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle). 
 
Вот общий шаблон реализации шаблона удаления для базового класса, который переопределяет метод [Object.Finalize](xref:System.Object.Finalize). 

```cs
using System;

class BaseClass : IDisposable
{
   // Flag: Has Dispose already been called?
   bool disposed = false;

   // Public implementation of Dispose pattern callable by consumers.
   public void Dispose()
   { 
      Dispose(true);
      GC.SuppressFinalize(this);           
   }

   // Protected implementation of Dispose pattern.
   protected virtual void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;
   }

   ~BaseClass()
   {
      Dispose(false);
   }
}
```

```vb
Class BaseClass : Implements IDisposable
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False

   ' Public implementation of Dispose pattern callable by consumers.
   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)           
   End Sub

   ' Protected implementation of Dispose pattern.
   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True
   End Sub

   Protected Overrides Sub Finalize()
      Dispose(False)      
   End Sub
End Class
```

> [!NOTE]
> В C# переопределение метода [Object.Finalize](xref:System.Object.Finalize) осуществляется путем определения `destructor`. 


## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a>Реализация шаблона удаления для производного класса

Класс, производный от класса, реализующего интерфейс [IDisposable](xref:System.IDisposable), не должен реализовывать интерфейс [IDisposable](xref:System.IDisposable), поскольку реализация метода [IDisposable.Dispose](xref:System.IDisposable.Dispose) базового класса наследуется производными классами. Вместо этого, чтобы реализовать шаблон удаления для базового класса, необходимо следующее: 

* Метод `protected Dispose(Boolean)`, который переопределяет метод базового класса и выполняет фактическую работу по освобождению ресурсов производного класса. Этот метод должен также вызывать метод `Dispose(Boolean)` базового класса и передавать в него значение `true` для аргумента *disposing*. 

* Любой класс, производный от класса [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle), который создает оболочку для неуправляемого ресурс (рекомендуется), или переопределенный метод [Object.Finalize](xref:System.Object.Finalize). Класс [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) содержит метод завершения, что освобождает разработчика от необходимости создавать его вручную. Если есть метод завершения, он должен вызывать перегруженный метод `Dispose(Boolean)`, указывая при этом аргумент *disposing* со значением `false`. 

Вот общий шаблон реализации шаблона удаления для производного класса, который использует безопасный дескриптор: 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.Runtime.InteropServices;

class DerivedClass : BaseClass
{
   // Flag: Has Dispose already been called?
   bool disposed = false;
   // Instantiate a SafeHandle instance.
   SafeHandle handle = new SafeFileHandle(IntPtr.Zero, true);

   // Protected implementation of Dispose pattern.
   protected override void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         handle.Dispose();
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //

      disposed = true;
      // Call base class implementation.
      base.Dispose(disposing);
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.Runtime.InteropServices

Class DerivedClass : Inherits BaseClass 
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False
   ' Instantiate a SafeHandle instance.
   Dim handle As SafeHandle = New SafeFileHandle(IntPtr.Zero, True)

   ' Protected implementation of Dispose pattern.
   Protected Overrides Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         handle.Dispose()
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True

      ' Call base class implementation.
      MyBase.Dispose(disposing)
   End Sub
End Class
```

> [!NOTE] 
> В предыдущем примере используется объект [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) для иллюстрации шаблона. Вместо него может использоваться любой объект, производный от [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle). Обратите внимание, что в этом примере неправильно создаются экземпляры объекта [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle). 

Вот общий шаблон реализации шаблона удаления для производного класса, который переопределяет метод [Object.Finalize](xref:System.Object.Finalize):

```cs
using System;

class DerivedClass : BaseClass
{
   // Flag: Has Dispose already been called?
   bool disposed = false;

   // Protected implementation of Dispose pattern.
   protected override void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;

      // Call the base class implementation.
      base.Dispose(disposing);
   }

   ~DerivedClass()
   {
      Dispose(false);
   }
}
```

```vb
Class DerivedClass : Inherits BaseClass
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False

   ' Protected implementation of Dispose pattern.
   Protected Overrides Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True

      ' Call the base class implementation.
      MyBase.Dispose(disposing)
   End Sub

   Protected Overrides Sub Finalize()
      Dispose(False)
   End Sub 
End Class
```

> [!NOTE]
> В C# переопределение метода [Object.Finalize](xref:System.Object.Finalize) осуществляется путем определения `destructor`.

## <a name="using-safe-handles"></a>Использование безопасных дескрипторов

Написание кода для метода завершения объекта является сложной задачей, которая может вызвать проблемы при неправильном выполнении. Поэтому вместо реализации метода завершения рекомендуется создавать объекты [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle).

Классы, производные от класса [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle), упрощают проблемы времени существования объекта путем назначения и освобождения дескрипторов без прерываний. Они содержат критический метод завершения, который обязательно выполняется во время выгрузки домена приложения. Безопасные дескрипторы предоставляются следующими производными классами в пространстве имен [Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles): 

* Классы [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle), [SafeMemoryMappedFileHandle](xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle) и [SafePipeHandle](xref:Microsoft.Win32.SafeHandles.SafePipeHandle) для файлов, сопоставленных в памяти файлов и каналов. 

* Класс [SafeMemoryMappedViewHandle](xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle) для представлений памяти. 

* Классы [SafeNCryptKeyHandle](https://msdn.microsoft.com/en-us/library/microsoft.win32.safehandles.safencryptkeyhandle(v=vs.110).aspx), [SafeNCryptProviderHandle](https://msdn.microsoft.com/en-us/library/microsoft.win32.safehandles.safencryptproviderhandle(v=vs.110).aspx) и [SafeNCryptSecretHandle](https://msdn.microsoft.com/en-us/library/microsoft.win32.safehandles.safencryptsecrethandle(v=vs.110).aspx) для конструкций шифрования.

* Класс [SafeRegistryHandle](xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle) для разделов реестра. 

* Класс [SafeWaitHandle](xref:Microsoft.Win32.SafeHandles.SafeWaitHandle) для дескрипторов ожидания. 

## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a>Использование безопасного дескриптора для реализации шаблона удаления для базового класса

В следующем примере показан шаблон удаления для базового класса `DisposableStreamResource`, который использует безопасный дескриптор для инкапсуляции неуправляемых ресурсов. Он определяет класс `DisposableResource`, который использует [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) для создания экземпляра объекта [Stream](xref:System.IO.Stream), который представляет открытый файл. Метод `DisposableResource` также включает свойство `Size`, которое возвращает общее количество байтов в файловом потоке. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.IO;
using System.Runtime.InteropServices;

public class DisposableStreamResource : IDisposable
{
   // Define constants.
   protected const uint GENERIC_READ = 0x80000000;
   protected const uint FILE_SHARE_READ = 0x00000001;
   protected const uint OPEN_EXISTING = 3;
   protected const uint FILE_ATTRIBUTE_NORMAL = 0x80;
   protected IntPtr INVALID_HANDLE_VALUE = new IntPtr(-1);
   private const int INVALID_FILE_SIZE = unchecked((int) 0xFFFFFFFF);

   // Define Windows APIs.
   [DllImport("kernel32.dll", EntryPoint = "CreateFileW", CharSet = CharSet.Unicode)]
   protected static extern IntPtr CreateFile (
                                  string lpFileName, uint dwDesiredAccess, 
                                  uint dwShareMode, IntPtr lpSecurityAttributes, 
                                  uint dwCreationDisposition, uint dwFlagsAndAttributes, 
                                  IntPtr hTemplateFile);

   [DllImport("kernel32.dll")]
   private static extern int GetFileSize(SafeFileHandle hFile, out int lpFileSizeHigh);

   // Define locals.
   private bool disposed = false;
   private SafeFileHandle safeHandle; 
   private long bufferSize;
   private int upperWord;

   public DisposableStreamResource(string filename)
   {
      if (filename == null)
         throw new ArgumentNullException("The filename cannot be null.");
      else if (filename == "")
         throw new ArgumentException("The filename cannot be an empty string.");

      IntPtr handle = CreateFile(filename, GENERIC_READ, FILE_SHARE_READ,
                                 IntPtr.Zero, OPEN_EXISTING, FILE_ATTRIBUTE_NORMAL,
                                 IntPtr.Zero);
      if (handle != INVALID_HANDLE_VALUE)
         safeHandle = new SafeFileHandle(handle, true);
      else
         throw new FileNotFoundException(String.Format("Cannot open '{0}'", filename));

      // Get file size.
      bufferSize = GetFileSize(safeHandle, out upperWord); 
      if (bufferSize == INVALID_FILE_SIZE)
         bufferSize = -1;
      else if (upperWord > 0) 
         bufferSize = (((long)upperWord) << 32) + bufferSize;
   }

   public long Size 
   { get { return bufferSize; } }

   public void Dispose()
   {
      Dispose(true);
      GC.SuppressFinalize(this);
   }           

   protected virtual void Dispose(bool disposing)
   {
      if (disposed) return;

      // Dispose of managed resources here.
      if (disposing)
         safeHandle.Dispose();

      // Dispose of any unmanaged resources not wrapped in safe handles.

      disposed = true;
   }  
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.IO

Public Class DisposableStreamResource : Implements IDisposable
   ' Define constants.
   Protected Const GENERIC_READ As UInteger = &H80000000ui
   Protected Const FILE_SHARE_READ As UInteger = &H0000000i
   Protected Const OPEN_EXISTING As UInteger = 3
   Protected Const FILE_ATTRIBUTE_NORMAL As UInteger = &H80
   Protected INVALID_HANDLE_VALUE As New IntPtr(-1)
   Private Const INVALID_FILE_SIZE As Integer = &HFFFFFFFF

   ' Define Windows APIs.
   Protected Declare Function CreateFile Lib "kernel32" Alias "CreateFileA" (
                                         lpFileName As String, dwDesiredAccess As UInt32, 
                                         dwShareMode As UInt32, lpSecurityAttributes As IntPtr, 
                                         dwCreationDisposition As UInt32, dwFlagsAndAttributes As UInt32, 
                                         hTemplateFile As IntPtr) As IntPtr
   Private Declare Function GetFileSize Lib "kernel32" (hFile As SafeFileHandle, 
                                                        ByRef lpFileSizeHigh As Integer) As Integer

   ' Define locals.
   Private disposed As Boolean = False
   Private safeHandle As SafeFileHandle 
   Private bufferSize As Long 
   Private upperWord As Integer

   Public Sub New(filename As String)
      If filename Is Nothing Then
         Throw New ArgumentNullException("The filename cannot be null.")
      Else If filename = ""
         Throw New ArgumentException("The filename cannot be an empty string.")
      End If

      Dim handle As IntPtr = CreateFile(filename, GENERIC_READ, FILE_SHARE_READ,
                                        IntPtr.Zero, OPEN_EXISTING, FILE_ATTRIBUTE_NORMAL,
                                        IntPtr.Zero)
      If handle <> INVALID_HANDLE_VALUE Then
         safeHandle = New SafeFileHandle(handle, True)
      Else
         Throw New FileNotFoundException(String.Format("Cannot open '{0}'", filename))
      End If

      ' Get file size.
      bufferSize = GetFileSize(safeHandle, upperWord) 
      If bufferSize = INVALID_FILE_SIZE Then
         bufferSize = -1
      Else If upperWord > 0 Then 
         bufferSize = (CLng(upperWord) << 32) + bufferSize
      End If     
   End Sub

   Public ReadOnly Property Size As Long
      Get
         Return bufferSize
      End Get
   End Property

   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)
   End Sub           

   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Exit Sub

      ' Dispose of managed resources here.
      If disposing Then
         safeHandle.Dispose()
      End If

      ' Dispose of any unmanaged resources not wrapped in safe handles.

      disposed = True
   End Sub  
End Class
```

## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a>Использование безопасного дескриптора для реализации шаблона удаления для производного класса

В следующем примере показан шаблон удаления для производного класса `DisposableStreamResource2`, унаследованного от класса `DisposableStreamResource`, представленного в предыдущем примере. Класс добавляет дополнительный метод `WriteFileInfo` и использует объект [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) для создания экземпляра дескриптора записываемого файла. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.IO;
using System.Runtime.InteropServices;
using System.Threading;

public class DisposableStreamResource2 : DisposableStreamResource
{
   // Define additional constants.
   protected const uint GENERIC_WRITE = 0x40000000; 
   protected const uint OPEN_ALWAYS = 4;

   // Define additional APIs.
   [DllImport("kernel32.dll")]   
   protected static extern bool WriteFile(
                                SafeFileHandle safeHandle, string lpBuffer, 
                                int nNumberOfBytesToWrite, out int lpNumberOfBytesWritten,
                                IntPtr lpOverlapped);

   // Define locals.
   private bool disposed = false;
   private string filename;
   private bool created = false;
   private SafeFileHandle safeHandle;

   public DisposableStreamResource2(string filename) : base(filename)
   {
      this.filename = filename;
   }

   public void WriteFileInfo()
   { 
      if (! created) {
         IntPtr hFile = CreateFile(xref:".\FileInfo.txt", GENERIC_WRITE, 0, 
                                   IntPtr.Zero, OPEN_ALWAYS, 
                                   FILE_ATTRIBUTE_NORMAL, IntPtr.Zero);
         if (hFile != INVALID_HANDLE_VALUE)
            safeHandle = new SafeFileHandle(hFile, true);
         else
            throw new IOException("Unable to create output file.");

         created = true;
      }

      string output = String.Format("{0}: {1:N0} bytes\n", filename, Size);
      int bytesWritten;
      bool result = WriteFile(safeHandle, output, output.Length, out bytesWritten, IntPtr.Zero);                                     
   }

   protected new virtual void Dispose(bool disposing)
   {
      if (disposed) return;

      // Release any managed resources here.
      if (disposing)
         safeHandle.Dispose();

      disposed = true;

      // Release any unmanaged resources not wrapped by safe handles here.

      // Call the base class implementation.
      base.Dispose(true);
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.IO

Public Class DisposableStreamResource2 : Inherits DisposableStreamResource
   ' Define additional constants.
   Protected Const GENERIC_WRITE As Integer = &H40000000 
   Protected Const OPEN_ALWAYS As Integer = 4

   ' Define additional APIs.
   Protected Declare Function WriteFile Lib "kernel32.dll" (
                              safeHandle As SafeFileHandle, lpBuffer As String, 
                              nNumberOfBytesToWrite As Integer, ByRef lpNumberOfBytesWritten As Integer,
                              lpOverlapped As Object) As Boolean

   ' Define locals.
   Private disposed As Boolean = False
   Private filename As String
   Private created As Boolean = False
   Private safeHandle As SafeFileHandle

   Public Sub New(filename As String)
      MyBase.New(filename)
      Me.filename = filename
   End Sub

   Public Sub WriteFileInfo() 
      If Not created Then
         Dim hFile As IntPtr = CreateFile(".\FileInfo.txt", GENERIC_WRITE, 0, 
                                          IntPtr.Zero, OPEN_ALWAYS, 
                                          FILE_ATTRIBUTE_NORMAL, IntPtr.Zero)
         If hFile <> INVALID_HANDLE_VALUE Then
            safeHandle = New SafeFileHandle(hFile, True)
         Else
            Throw New IOException("Unable to create output file.")
         End If
         created = True
      End If
      Dim output As String = String.Format("{0}: {1:N0} bytes {2}", filename, Size, 
                                           vbCrLf)
      WriteFile(safeHandle, output, output.Length, 0&, Nothing)                                     
   End Sub

   Protected Overloads Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Exit Sub

      ' Release any managed resources here.
      If disposing Then
         safeHandle.Dispose()
      End If

      disposed = True
      ' Release any unmanaged resources not wrapped by safe handles here.

      ' Call the base class implementation.
      MyBase.Dispose(True)
   End Sub
End Class
```

## <a name="see-also"></a>См. также

[SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object))

[IDisposable](xref:System.IDisposable)

[IDisposable.Dispose](xref:System.IDisposable.Dispose)

[Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles)

[System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)

[IDisposable.Dispose](xref:System.IDisposable.Dispose)



<!--HONumber=Nov16_HO1-->


