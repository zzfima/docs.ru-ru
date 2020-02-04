---
title: dotnet-dump (.NET Core)
description: Установка и использование программы командной строки dotnet-dump.
ms.date: 10/14/2019
ms.openlocfilehash: 3c0e28d4efc96ae53ec7dfae243725ab400e6b8f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737669"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a>Программа для сбора и анализа дампов (`dotnet-dump`)

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 3.0 и более поздних версий

> [!NOTE]
> `dotnet-dump` не поддерживается для macOS.

## <a name="installing-dotnet-dump"></a>Установка `dotnet-dump`

Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-dump) `dotnet-dump`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a>Краткий обзор

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a>Описание

`dotnet-dump` — это средство сбора и анализа дампов в Windows и Linux, которое не задействует собственный отладчик системы (как, например, `lldb` в Linux). Это средство имеет важное значение на таких платформах, как Alpine Linux, где отсутствует полноценно работающее средство `lldb`. Средство `dotnet-dump` позволяет выполнять команды SOS для анализа сбоев и сборщика мусора (GC), но не поддерживает некоторые функции, как, например, отображение собственных кадров стека, потому что не является встроенным отладчиком.

## <a name="options"></a>Параметры

- **`--version`**

  Отображение версии служебной программы dotnet-counters.

- **`-h|--help`**

  Отображение справки в командной строке.

## <a name="commands"></a>Команды

| Команда                                     |
| ------------------------------------------- |
| [dotnet-dump collect](#dotnet-dump-collect) |
| [dotnet-dump analyze](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a>dotnet-dump collect

Записывает дамп из процесса.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a>Параметры

- **`-h|--help`**

  Отображение справки в командной строке.

- **`-p|--process-id <PID>`**

  Указывает идентификатор процесса, из которого нужно собрать дамп памяти.

- **`--type <Heap|Mini>`**

  Указывает тип дампа, который определяет типы собираемых из процесса данных. Различаются два типа дампа.

  - `Heap` — большой и сравнительно подробный дамп, который содержит списки модулей, списки потоков, все стеки, сведения об исключениях, сведения об обработке и всю память, за исключением сопоставленных образов.
  - `Mini` — небольшой дамп, который содержит списки модулей, списки потоков, сведения об исключениях и все стеки.

  Если тип не указан, по умолчанию используется вариант `Heap`.

- **`-o|--output <output_dump_path>`**

  Полный путь и имя файла, в который будет записан собранный дамп.

  Если значение не указано, используются следующие:

  - *.\dump_YYYYMMDD_HHMMSS.dmp* в ОС Windows;
  - *./core_YYYYMMDD_HHMMSS* в ОС Linux.

  YYYYMMDD обозначает формат "год/месяц/день", а HHMMSS — формат "час/минута/секунда".

- **`--diag`**

  Включает ведение журнала диагностики для сбора дампов.

## <a name="dotnet-dump-analyze"></a>dotnet-dump analyze

Запускает интерактивную оболочку для просмотра дампа. Эта оболочка принимает различные [команды SOS](#analyze-sos-commands).

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a>Аргументы

- **`<dump_path>`**

  Указывает путь к анализируемому файлу дампа.

### <a name="options"></a>Параметры

- **`-c|--command <debug_command>`**

  Указывает [команду](#analyze-sos-commands), которую нужно выполнить при запуске оболочки.

### <a name="analyze-sos-commands"></a>Анализ команд SOS

| Команда                             | Функция                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | Отображение всех доступных команд.                                                               |
| `soshelp|help <command>`            | Отображение сведений об указанной команде.                                                               |
| `exit|quit`                         | Выход из интерактивного режима.                                                                       |
| `clrstack <arguments>`              | Обеспечивает трассировку стека только для управляемого кода.                                                  |
| `clrthreads <arguments>`            | Перечисление всех выполняемых управляемых потоков.                                                            |
| `dumpasync <arguments>`             | Отображение информации о машинах асинхронной обработки для кучи со сборкой мусора.                |
| `dumpassembly <arguments>`          | Отображение сведений о сборке.                                                           |
| `dumpclass <arguments>`             | Отображение сведений о структуре класса EE, размещенной по указанному адресу.                     |
| `dumpdelegate <arguments>`          | Отображение сведений о делегате.                                                        |
| `dumpdomain <arguments>`            | Отображение сведений обо всех доменах приложений и всех сборках в этих доменах.                |
| `dumpheap <arguments>`              | Отображение сведений о куче со сборкой мусора и статистики сборки мусора по объектам.       |
| `dumpil <arguments>`                | Отображает язык CIL, связанный с управляемым методом. |
| `dumplog <arguments>`               | Записывает в указанный файл содержимое журнала нагрузок, хранящегося в памяти.                         |
| `dumpmd <arguments>`                | Отображение сведений о структуре MethodDesc, которая расположена по указанному адресу.                   |
| `dumpmodule <arguments>`            | Отображение сведений о структуре модуля EE, который расположен по указанному адресу.                    |
| `dumpmt <arguments>`                | Отображает сведения о таблице методов, расположенной по указанному адресу.                           |
| `dumpobj <arguments>`               | Отображение сведений об объекте, который расположен по указанному адресу.                                       |
| `dso|dumpstackobjects <arguments>`  | Отображает все управляемые объекты, обнаруженные в пределах границ текущего стека.                    |
| `eeheap <arguments>`                | Отображение сведений о памяти процессов, занятой внутренними структурами данных среды выполнения.              |
| `finalizequeue <arguments>`         | Отображает все объекты, зарегистрированные для заключительной обработки.                                             |
| `gcroot <arguments>`                | Отображение информации о ссылках (или корневых элементах) объекта, который расположен по указанному адресу.              |
| `gcwhere <arguments>`               | Отображение расположения переданного аргумента в куче со сборкой мусора.                               |
| `ip2md <arguments>`                 | Отображение структуры MethodDesc, которая расположена по указанному адресу в JIT-коде.                       |
| `histclear <arguments>`             | Освобождает все ресурсы, используемые семейством команд `hist*`.                                |
| `histinit <arguments>`              | Инициализирует структуры SOS из журнала нагрузки, сохраненного в отлаживаемом объекте.                     |
| `histobj <arguments>`               | Отображение перераспределений журнала нагрузок для сборки мусора, связанных с `<arguments>`.              |
| `histobjfind <arguments>`           | Отображает все записи журнала, ссылающиеся на объект по указанному адресу.               |
| `histroot <arguments>`              | Отображает сведения о повышениях и перемещениях указанного корневого элемента.        |
| `lm|modules`                        | Отображение выполняемых собственных модулей.                                                   |
| `name2ee <arguments>`               | Отображение структуры MethodTable и структуры EEClass для `<argument>`.                |
| `pe|printexception <arguments>`     | Отображение всех объектов, наследуемых от класса Exception, который расположен по адресу `<argument>`.             |
| `setsymbolserver <arguments>`       | Включение поддержки сервера символов                                                             |
| `syncblk <arguments>`               | Отображение сведений о заполнителе SyncBlock.                                                           |
| `threads|setthread <threadid>`      | Отображение или изменение идентификатора текущего потока для команд SOS.                                  |

## <a name="using-dotnet-dump"></a>Использование `dotnet-dump`

Первым шагом является сборка дампа. Этот шаг можно пропустить, если уже создан основной дамп. Основные дампы могут создавать как операционная система, так и встроенная в среду выполнения .NET Core [функция создания дампа](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md).

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

Теперь запустите анализ основного дампа с помощью команды `analyze`:

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

Это действие открывает интерактивный сеанс, который принимает команды следующего вида:

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

Чтобы получить сведения о необработанном исключении, которое привело к сбою приложения, выполните:

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a>Особые инструкции для Docker

Если вы используете Docker, для сбора дампа требуются возможности `SYS_PTRACE` (`--cap-add=SYS_PTRACE` или `--privileged`).

В образах Docker с Linux и пакетом SDK для Microsoft .NET Core некоторые команды `dotnet-dump` могут вызвать следующее исключение:

> Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception. (Необработанное исключение: System.DllNotFoundException: Не удалось загрузить общую библиотеку libdl.so или одну из ее зависимостей.)

Чтобы обойти эту проблему, установите пакет libc6-dev.
