---
title: dotnet-counters (.NET Core)
description: Сведения о том, как установить и использовать программу командной строки dotnet-counter.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: b2fab239713d9d19c580580496e73a91ceafcc52
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321540"
---
# <a name="dotnet-counters"></a><span data-ttu-id="e2507-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="e2507-103">dotnet-counters</span></span>

<span data-ttu-id="e2507-104">**Эта статья относится к ✓** SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="e2507-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="e2507-105">Установка dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="e2507-105">Install dotnet-counters</span></span>

<span data-ttu-id="e2507-106">Чтобы установить последнюю версию `dotnet-counters` [пакета NuGet](https://www.nuget.org/packages/dotnet-counters), используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="e2507-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="e2507-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e2507-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="e2507-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="e2507-108">Description</span></span>

<span data-ttu-id="e2507-109">`dotnet-counters` — это средство мониторинга производительности и первого уровня анализа производительности.</span><span class="sxs-lookup"><span data-stu-id="e2507-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="e2507-110">Оно умеет отслеживать значения счетчиков производительности, опубликованные через API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="e2507-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="e2507-111">Например, вы можете быстро отслеживать такие параметры, как загрузка ЦП или частота возникновения исключений в приложении .NET Core, чтобы обнаружить подозрительное поведение перед началом более серьезных расследований с помощью `PerfView` или `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="e2507-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="e2507-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2507-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="e2507-113">Отображение версии служебной программы dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="e2507-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e2507-114">Отображение справки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e2507-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="e2507-115">Команды</span><span class="sxs-lookup"><span data-stu-id="e2507-115">Commands</span></span>

| <span data-ttu-id="e2507-116">Команда</span><span class="sxs-lookup"><span data-stu-id="e2507-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="e2507-117">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="e2507-117">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="e2507-118">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="e2507-118">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a><span data-ttu-id="e2507-119">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="e2507-119">dotnet-counters list</span></span>

<span data-ttu-id="e2507-120">Отображение списка имен и описаний счетчиков, сгруппированных по поставщикам.</span><span class="sxs-lookup"><span data-stu-id="e2507-120">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="e2507-121">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e2507-121">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="e2507-122">Пример</span><span class="sxs-lookup"><span data-stu-id="e2507-122">Example</span></span>

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="e2507-123">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="e2507-123">dotnet-counters monitor</span></span>

<span data-ttu-id="e2507-124">Отображение периодически обновляемых значений для выбранных счетчиков.</span><span class="sxs-lookup"><span data-stu-id="e2507-124">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="e2507-125">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e2507-125">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="e2507-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2507-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="e2507-127">Идентификатор отслеживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="e2507-127">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="e2507-128">Время (в секундах) между обновлением значений отображаемых счетчиков</span><span class="sxs-lookup"><span data-stu-id="e2507-128">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="e2507-129">Список счетчиков, разделенный пробелами.</span><span class="sxs-lookup"><span data-stu-id="e2507-129">A space separated list of counters.</span></span> <span data-ttu-id="e2507-130">Вы можете объявить счетчики как `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="e2507-130">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="e2507-131">Если используется `provider_name` без указания `counter_name`, отображаются все счетчики.</span><span class="sxs-lookup"><span data-stu-id="e2507-131">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="e2507-132">Для обнаружения имен поставщиков и счетчиков используйте команду [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="e2507-132">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="e2507-133">Примеры</span><span class="sxs-lookup"><span data-stu-id="e2507-133">Examples</span></span>

- <span data-ttu-id="e2507-134">Мониторинг всех счетчиков из `System.Runtime` с интервалом обновления 3 секунды:</span><span class="sxs-lookup"><span data-stu-id="e2507-134">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="e2507-135">Мониторинг только счетчиков использования ЦП и размера кучи GC из `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="e2507-135">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="e2507-136">Мониторинг значений `EventCounter` из определяемых пользователем `EventSource`:</span><span class="sxs-lookup"><span data-stu-id="e2507-136">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="e2507-137">Дополнительные сведения см. в статье [Руководство. How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md) (Как измерять производительность для очень часто выполняемых событий с помощью EventCounters).</span><span class="sxs-lookup"><span data-stu-id="e2507-137">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
