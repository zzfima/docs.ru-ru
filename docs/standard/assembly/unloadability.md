---
title: Использование и отладка сборок с возможностью выгрузки в .NET Core
description: Сведения об использовании собираемого AssemblyLoadContext для загрузки и выгрузки управляемых сборок, а также об отладке проблем, препятствующих успешной выгрузке.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: 267c2209556b66ab3541c9c79c99d7eceb2024da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159745"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Использование и отладка сборок с возможностью выгрузки в .NET Core

Начиная с .NET Core 3.0 поддерживается возможность загрузки и последующей выгрузки набора сборок. В .NET Framework для этой цели использовались пользовательские домены приложений, но .NET Core поддерживает только один домен приложения по умолчанию.

.NET Core 3.0 и более поздние версии поддерживают выгрузку с помощью <xref:System.Runtime.Loader.AssemblyLoadContext>. Вы можете загрузить набор сборок в собираемые `AssemblyLoadContext`, выполнять в них методы или просто проверять их с помощью отражения и, наконец, выгрузить `AssemblyLoadContext`. Эта операция выгружает сборки, загруженные в `AssemblyLoadContext`.

Между выгрузкой с помощью `AssemblyLoadContext` и доменов приложений есть одно важное различие. При использовании доменов приложений выгрузка выполняется принудительно. В момент выгрузки все потоки, работающие в целевом домене приложения, прерываются, управляемые COM-объекты, созданные в целевом домене приложения, уничтожаются и т. д. При использовании `AssemblyLoadContext` выгрузка выполняется в режиме "сотрудничества". Вызов метода <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> просто инициирует выгрузку. Выгрузка завершается после того, как:

- Ни один из потоков не имеет методов из сборок, загруженных в `AssemblyLoadContext` в стеках вызовов.
- Ни на один из типов из сборок, загруженных в `AssemblyLoadContext`, экземпляры этих типов и сами сборки не ссылаются:
  - Ссылки за пределами `AssemblyLoadContext`, за исключением слабых ссылок (<xref:System.WeakReference> или <xref:System.WeakReference%601>).
  - Строгие дескрипторы сборщика мусора ([GCHandleType.Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) или [GCHandleType.Pinned](xref:System.Runtime.InteropServices.GCHandleType.Pinned)) как внутри, так и за пределами `AssemblyLoadContext`.

## <a name="use-collectible-assemblyloadcontext"></a>Использование забираемого AssemblyLoadContext

В этом разделе содержится подробное пошаговое руководство, в котором показан простой способ загрузки приложения .NET Core в собираемый `AssemblyLoadContext`, выполнения его точки входа и последующей выгрузки. Полный пример см. по адресу [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).

### <a name="create-a-collectible-assemblyloadcontext"></a>Создание собираемого AssemblyLoadContext

Необходимо получить класс от <xref:System.Runtime.Loader.AssemblyLoadContext> и перегрузить его метод <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>. Этот метод разрешает ссылки на все сборки, которые являются зависимостями загруженных в `AssemblyLoadContext` сборок.

Следующий код является примером простейшего пользовательского `AssemblyLoadContext`:

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

Как видите, метод `Load` возвращает `null`. Это означает, что все сборки зависимостей загружаются в контекст по умолчанию, а новый контекст содержит только те сборки, которые были явно загружены в него.

Если требуется загрузить некоторые или все зависимости в `AssemblyLoadContext` тоже, можно использовать `AssemblyDependencyResolver` в методе `Load`. `AssemblyDependencyResolver` разрешает имена сборок в абсолютные пути к файлам сборки. Сопоставитель использует файл *.deps.json* и файлы сборки в каталоге основной сборки, загруженной в контекст.

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a>Использование пользовательского собираемого AssemblyLoadContext

В этом разделе предполагается, что используется более простая версия `TestAssemblyLoadContext`.

Вы можете создать экземпляр пользовательского `AssemblyLoadContext` и загрузить в него сборку следующим образом:

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

Для каждой сборки, на которую ссылается загруженная сборка, вызывается метод `TestAssemblyLoadContext.Load`, чтобы `TestAssemblyLoadContext` мог решить, откуда получить сборку. В нашем случае он возвращает `null`, чтобы указать, что он должен быть загружен в контекст по умолчанию из расположений, используемых средой выполнения для загрузки сборок по умолчанию.

Теперь, когда сборка загружена, можно выполнить из нее метод. Выполните метод `Main`:

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

После возврата метода `Main` можно инициировать выгрузку путем вызова метода `Unload` для пользовательского `AssemblyLoadContext` или удаления имеющейся ссылки на `AssemblyLoadContext`:

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

Этого достаточно для выгрузки тестовой сборки. Давайте разместим все это в отдельном невстраиваемом методе, чтобы гарантировать, что, `TestAssemblyLoadContext`, `Assembly` и `MethodInfo` (`Assembly.EntryPoint`) не могут поддерживаться в активном состоянии ссылками слота стека (в реальных или введенных JIT локальных переменных). Это поможет поддерживать `TestAssemblyLoadContext` и предотвратить выгрузку.

Кроме того, верните слабую ссылку на `AssemblyLoadContext`, чтобы можно было использовать его позже для обнаружения завершения выгрузки.

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

Теперь эту функцию можно использовать для загрузки, выполнения и выгрузки сборки.

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

Однако выгрузка не завершается немедленно. Как упоминалось ранее, она полагается на сборщика мусора для сбора всех объектов из тестовой сборки. Во многих случаях нет необходимости ждать завершения выгрузки. Однако в некоторых случаях полезно знать, что выгрузка завершена. Например, вы хотите удалить файл сборки, который был загружен в пользовательский `AssemblyLoadContext` с диска. В этом случае можно использовать следующий фрагмент кода. Он запускает сборку мусора и ожидает методы завершения ожидания в цикле, пока слабая ссылка на пользовательский `AssemblyLoadContext` не будет установлена на `null`, указывая, что целевой объект был собран. В большинстве случаев требуется только один проход по циклу. Однако в более сложных случаях, когда объекты, создаваемые кодом, выполняющимися в `AssemblyLoadContext`, имеют методы завершения, может потребоваться больше проходов.

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a>Событие выгрузки

В некоторых случаях может потребоваться, чтобы код был загружен в пользовательский `AssemblyLoadContext` для выполнения очистки при инициации выгрузки. Например, может потребоваться отключить потоки или очистить некоторые строгие дескрипторы сборки мусора. В таких случаях можно использовать событие `Unloading`. Обработчик, выполняющий необходимую очистку, может быть подключен к этому событию.

### <a name="troubleshoot-unloadability-issues"></a>Устранение проблем с выгрузкой

Из-за сотрудничающей природы выгрузки можно легко забыть о ссылках, которые поддерживают активность элементов в собираемом `AssemblyLoadContext` и предотвращают выгрузку. Ниже описываются сущности (некоторые из них не очевидны), которые могут содержать ссылки:

- Обычные ссылки за пределами собираемого `AssemblyLoadContext`, хранящегося в слоте стека или в регистре процессора (локальные переменные метода, явно созданные пользовательским кодом или неявно JIT-компилятором), статическая переменная или строгий/закрепляющий обработчик сборки мусора, транзитивно указывающие на следующие элементы:
  - Сборка, загруженная в собираемый `AssemblyLoadContext`.
  - Тип из такой сборки.
  - Экземпляр типа из такой сборки.
- Потоки, выполняющие код из сборки, загруженной в собираемый `AssemblyLoadContext`.
- Экземпляры пользовательских несобираемых типов `AssemblyLoadContext`, созданных в собираемом `AssemblyLoadContext`.
- Ожидающие обработки экземпляры <xref:System.Threading.RegisteredWaitHandle> с обратными вызовами, настроенными на методы в пользовательском `AssemblyLoadContext`.

> [!TIP]
> Ссылки на объекты, которые хранятся в слотах стека или регистрах процессора и которые могут предотвратить выгрузку `AssemblyLoadContext`, могут возникать в следующих ситуациях:
>
> - Когда результаты вызова функции передаются непосредственно в другую функцию, несмотря на отсутствие созданной пользователем локальной переменной.
> - Когда JIT-компилятор сохраняет ссылку на объект, который был доступен в определенный момент в методе.

## <a name="debug-unloading-issues"></a>Отладка проблем с выгрузкой

Отладка проблем с выгрузкой может быть утомительной. Иногда вы не знаете, что поддерживает активность `AssemblyLoadContext`, но выгрузка завершается ошибкой. Лучшим решением станет WinDbg (LLDB в UNIX) с подключаемым модулем SOS. Необходимо найти сведения о том, что поддерживает активность `LoaderAllocator`, принадлежащего конкретному `AssemblyLoadContext`. Подключаемый модуль SOS позволяет просматривать объекты кучи GC, их иерархии и корни.

Чтобы загрузить подключаемый модуль в отладчик, введите следующую команду в командной строке отладчика:

В WinDbg (кажется, что WinDbg делает это автоматически при прерывании приложения .NET Core):

```console
.loadby sos coreclr
```

В LLDB:

```console
plugin load /path/to/libsosplugin.so
```

Давайте выполним отладку примера программы, в которой возникли проблемы с выгрузкой. Исходный код приводится ниже. При запуске с помощью WinDbg программа переключается в отладчике сразу после попытки проверить успешность выгрузки. После этого вы можете начать поиск причины проблемы.

> [!TIP]
> При отладке с помощью LLDB в Unix команды SOS в следующих примерах не содержат перед собой `!`.

```console
!dumpheap -type LoaderAllocator
```

Эта команда выполняет дамп всех объектов с именем типа, содержащим `LoaderAllocator` в куче сборщика мусора. Например:

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48
000002b78000ceb0 00007ffadc93a218       24

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

В разделе "Statistics:" ниже проверьте `MT` (`MethodTable`), который принадлежит `System.Reflection.LoaderAllocator`, и именно этот объект нас интересует. Затем в списке в начале найдите запись с `MT`, соответствующим этому объекту, и получите адрес самого объекта. В нашем случае это 000002b78000ce40.

Теперь, когда мы знаем адрес объекта `LoaderAllocator`, можно использовать другую команду для поиска его корней в сборке мусора:

```console
!gcroot -all 0x000002b78000ce40
```

Эта команда выполняет дампы цепочки ссылок на объекты, ведущих к экземпляру `LoaderAllocator`. Список начинается с корня, который поддерживает активность `LoaderAllocator`, и, таким образом, является причиной проблемы. Корнем может быть слот стека, регистр процессора, обработчик сборки мусора или статическая переменная.

Вот пример результата выходных данных команды `gcroot`:

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

Следующий шаг — выяснить, где находится корень, чтобы его можно было исправить. Самый простой случай: корень — это слот стека или регистр процессора. В этом случае в `gcroot` отображается имя функции, фрейм которой содержит корень, и поток, в котором выполняется эта функция. Сложный случай: корень является статической переменной или обработчиком сборки мусора.

В предыдущем примере первый корень является локальной переменной типа `System.Reflection.RuntimeMethodInfo`, хранимого во фрейме функции `example.Program.Main(System.String[])` по адресу `rbp-20` (`rbp` — это регистр процессора `rbp`, а –20 — шестнадцатеричное смещение от этого регистра).

Второй корень является нормальным (строгим) `GCHandle`, который содержит ссылку на экземпляр класса `test.Test`.

Третий корень является закрепленным `GCHandle`. На самом деле это статическая переменная, но к сожалению, нет способа определить это. Статические переменные для ссылочных типов хранятся в управляемом массиве объектов во внутренних структурах среды выполнения.

Другой вариант, который может помешать выгрузке `AssemblyLoadContext`, — когда поток содержит фрейм метода из сборки, загруженной в стек `AssemblyLoadContext`. Это можно проверить, выполнив дамп управляемых стеков вызовов всех потоков:

```console
~*e !clrstack
```

Команда означает "Применить ко всем потокам команду `!clrstack`". Ниже приведен результат выполнения команды для примера. К сожалению, в LLDB в Unix нет способа применить команду ко всем потокам, поэтому необходимо будет вручную переключать потоки и повторять команду `clrstack`. Игнорируйте все потоки, в которых отладчик сообщает: "Не удалось пройти по управляемому стеку".

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998]
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28]
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0]
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568]
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0]

```

Как видите, последний поток имеет `test.Program.ThreadProc()`. Это функция из сборки, загруженной в `AssemblyLoadContext`, и поэтому она сохраняет активность `AssemblyLoadContext`.

## <a name="example-source-with-unloadability-issues"></a>Пример источника с проблемами выгрузки

В предыдущем примере отладки используется следующий код.

### <a name="main-testing-program"></a>Основная программа тестирования

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a>Программа, загруженная в TestAssemblyLoadContext

Следующий код представляет *test.dll*, переданный в метод `ExecuteAndUnload` в основной программе тестирования.

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
