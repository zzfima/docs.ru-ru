---
title: Программа dotnet-trace — .NET Core
description: Установка и использование программы командной строки dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: 64c931db5a18659707e832aaca910cfbbd6823c0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714435"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>Программа анализа производительности dotnet-trace

**Эта статья относится к** ✓ SDK для .NET Core 3.0 и более поздних версий

## <a name="install-dotnet-trace"></a>Установка dotnet-trace

Установите [пакет NuGet](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` с помощью команды [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>Описание

Программа `dotnet-trace` —

* это кроссплатформенное средство .NET Core.
* Выполняет сбор трассировок .NET Core для запущенного процесса без встроенного профилировщика.
* Создано на основе кроссплатформенной технологии `EventPipe` для среды выполнения .NET Core.
* Предоставляет одинаковые возможности в Windows, Linux и macOS.

## <a name="options"></a>Параметры

- **`--version`**  

  Отображение версии служебной программы dotnet-counters.

- **`-h|--help`**

  Отображение справки в командной строке.

## <a name="commands"></a>Команды

| Команда                                                     |
| ----------------------------------------------------------- |
| [dotnet-trace collect](#dotnet-trace-collect)               |
| [dotnet-trace convert](#dotnet-trace-convert)               |
| [dotnet-trace ps](#dotnet-trace-ps) |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

Собирает диагностическую трассировку для выполняющегося процесса.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>Параметры

- **`-p|--process-id <PID>`**

  Процесс, для которого нужна трассировка.

- **`--buffersize <size>`**

  Задает размер кольцевого буфера в памяти (в мегабайтах). По умолчанию используется значение 256 МБ.

- **`-o|--output <trace-file-path>`**

  Выходной путь для собранных данных трассировки. Если это значение не указано, по умолчанию используется `trace.nettrace`.

- **`--providers <list-of-comma-separated-providers>`**

  Список применяемых поставщиков `EventPipe`, разделенный запятыми. Поставщики из этого списка применяются в дополнение к тем, которые подразумеваются в `--profile <profile-name>`. При наличии несогласованности по конкретному поставщику указанная здесь конфигурация имеет приоритет над неявной конфигурацией из профиля.

  Список поставщиков предоставляется в следующем формате:

  - `Provider[,Provider]`
  - `Provider` имеет формат `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`;
  - `KeyValueArgs` имеет формат `[key1=value1][;key2=value2]`.

- **`--profile <profile-name>`**

  Заранее определенный именованный набор конфигураций поставщиков, который позволяет кратко указывать типичные сценарии трассировки.

- **`--format {NetTrace|Speedscope}`**

  Задает формат выходных данных для преобразования файла трассировки. Значение по умолчанию — `NetTrace`.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

Преобразует трассировки `nettrace` в альтернативные форматы для использования с другими средствами анализа трассировок.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>Аргументы

- **`<input-filename>`**

  Исходный файл трассировки для преобразования. По умолчанию используется значение *trace.nettrace*.

### <a name="options"></a>Параметры

- **`--format <NetTrace|Speedscope>`**

  Задает формат выходных данных для преобразования файла трассировки.

- **`-o|--output <output-filename>`**

  Имя файла выходных данных. К нему добавляется расширение целевого формата.

## <a name="dotnet-trace-ps"></a>dotnet-trace ps

Список процессов dotnet, к которым можно присоединиться.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

Список предварительно созданных профилей трассировки с перечислением поставщиков и фильтров в каждом профиле.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Сбор трассировки с помощью dotnet-trace

Для сбора трассировок с помощью `dotnet-trace` выполните указанные ниже действия.

- Получите идентификатор процесса (PID) для трассируемого приложения .NET Core.

  - В Windows его можно получить, например, через диспетчер задач или с помощью команды `tasklist`.
  - В Linux можно использовать, например, команду `ps`.
  - [dotnet-trace ps](#dotnet-trace-ps)

- Выполните следующую команду:

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  Приведенная выше команда создает выходные данные наподобие следующих:

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- Чтобы остановить сбор, нажмите клавишу `<Enter>`. `dotnet-trace` завершит запись событий в файл *trace.nettrace*.

## <a name="view-the-trace-captured-from-dotnet-trace"></a>Просмотр трассировки, собранной с помощью dotnet-trace

В Windows файлы *NETTRACE* можно просматривать и анализировать в [PerfView](https://github.com/microsoft/perfview). Если трассировка была собрана на другой платформе, ее файл можно переместить на компьютер с Windows для просмотра в PerfView.

В Linux трассировку можно просмотреть, изменив формат выходных данных с `dotnet-trace` на `speedscope`. Чтобы изменить формат выходного файла, укажите параметр `-f|--format`. При значении `-f speedscope` программа `dotnet-trace` создаст файл `speedscope`. Вы можете выбрать варианты `nettrace` (по умолчанию) или `speedscope`. Файлы `Speedscope` можно открывать с помощью <https://www.speedscope.app>.

> [!NOTE]
> Среда выполнения .NET Core создает трассировки в формате `nettrace`. В формат speedscope (если требуется) они преобразуются уже после завершения трассировки. Так как некоторые преобразования приводят к потере данных, исходный файл `nettrace` сохраняется рядом с преобразованным файлом.

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a>Использование dotnet-trace для получения значений счетчиков за период времени

Программа `dotnet-trace` позволяет выполнять следующие задачи:

* использовать `EventCounter` для простого мониторинга работоспособности в средах с высокой чувствительностью к производительности, например рабочих;
* собирать трассировки, чтобы их не нужно было просматривать в режиме реального времени.

Например, если вам нужны значения счетчика производительности из среды выполнения, используйте следующую команду:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Эта команда означает, что счетчики среды выполнения будут отслеживаться каждую секунду, то есть реализует не требовательную к ресурсам схему мониторинга работоспособности. Заменив `EventCounterIntervalSec=1` большим значением (например, 60), вы получите трассировку данных счетчиков меньшего объема и с меньшим уровнем детализации.

Следующая команда сокращает накладные расходы и размер трассировки сильнее, чем предыдущая:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

Эта команда отключает события среды выполнения и профилировщик управляемого стека.

## <a name="net-providers"></a>Поставщики .NET

Среда выполнения .NET Core поддерживает следующие поставщики .NET. .NET Core использует одинаковые ключевые слова для включения трассировок `Event Tracing for Windows (ETW)` и `EventPipe`.

| Имя поставщика                            | Сведения |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [Поставщик среды выполнения](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[Ключевые слова среды выполнения CLR](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [Поставщик очистки](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[Ключевые слова очистки CLR](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Включает пример профилировщика. |
