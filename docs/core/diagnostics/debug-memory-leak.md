---
title: Учебник по выполнению отладки утечки памяти
description: Узнайте, как выполнить отладку утечки памяти в .NET Core.
ms.topic: tutorial
ms.date: 12/17/2019
ms.openlocfilehash: cb137503cbc81f5ab9438dadcf1dc1c6750a1ca8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715606"
---
# <a name="tutorial-debug-a-memory-leak-in-net-core"></a><span data-ttu-id="ed467-103">Учебник. Отладка утечки памяти в .NET Core</span><span class="sxs-lookup"><span data-stu-id="ed467-103">Tutorial: Debug a memory leak in .NET Core</span></span>

<span data-ttu-id="ed467-104">**Эта статья относится к ✓** SDK для .NET Core 3.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="ed467-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="ed467-105">В этом учебнике демонстрируются инструменты, позволяющие проанализировать утечку памяти в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ed467-105">This tutorial demonstrates the tools to analyze a .NET Core memory leak.</span></span>

<span data-ttu-id="ed467-106">Здесь используется пример приложения, в котором намеренно происходит утечка памяти.</span><span class="sxs-lookup"><span data-stu-id="ed467-106">This tutorial uses a sample app, which is designed to intentionally leak memory.</span></span> <span data-ttu-id="ed467-107">Пример предоставляется для выполнения упражнения.</span><span class="sxs-lookup"><span data-stu-id="ed467-107">The sample is provided as an exercise.</span></span> <span data-ttu-id="ed467-108">Вы можете проанализировать приложение, в котором также непреднамеренно происходит утечка памяти.</span><span class="sxs-lookup"><span data-stu-id="ed467-108">You can analyze an app that is unintentionally leaking memory too.</span></span>

<span data-ttu-id="ed467-109">В этом руководстве рассмотрены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="ed467-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="ed467-110">Изучение использования управляемой памяти с помощью [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="ed467-110">Examine managed memory usage with [dotnet-counters](dotnet-counters.md).</span></span>
> - <span data-ttu-id="ed467-111">Создание файла дампа.</span><span class="sxs-lookup"><span data-stu-id="ed467-111">Generate a dump file.</span></span>
> - <span data-ttu-id="ed467-112">Анализ использования памяти с помощью файла дампа.</span><span class="sxs-lookup"><span data-stu-id="ed467-112">Analyze the memory usage using the dump file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed467-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ed467-113">Prerequisites</span></span>

<span data-ttu-id="ed467-114">В этом учебнике используется:</span><span class="sxs-lookup"><span data-stu-id="ed467-114">The tutorial uses:</span></span>

- <span data-ttu-id="ed467-115">[Пакет SDK для .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ed467-115">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="ed467-116">[dotnet-trace](dotnet-trace.md) для отображения списка процессов.</span><span class="sxs-lookup"><span data-stu-id="ed467-116">[dotnet-trace](dotnet-trace.md) to list processes.</span></span>
- <span data-ttu-id="ed467-117">[dotnet-counters](dotnet-counters.md) для проверки использования управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="ed467-117">[dotnet-counters](dotnet-counters.md) to check managed memory usage.</span></span>
- <span data-ttu-id="ed467-118">[dotnet-dump](dotnet-dump.md) для сбора и анализа файла дампа.</span><span class="sxs-lookup"><span data-stu-id="ed467-118">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file.</span></span>
- <span data-ttu-id="ed467-119">[Пример целевого приложения отладки](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) для диагностики.</span><span class="sxs-lookup"><span data-stu-id="ed467-119">A [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) app to diagnose.</span></span>

<span data-ttu-id="ed467-120">В учебнике предполагается, что пример приложения и инструменты установлены и готовы к использованию.</span><span class="sxs-lookup"><span data-stu-id="ed467-120">The tutorial assumes the sample and tools are installed and ready to use.</span></span>

## <a name="examine-managed-memory-usage"></a><span data-ttu-id="ed467-121">Изучение использования управляемой памяти</span><span class="sxs-lookup"><span data-stu-id="ed467-121">Examine managed memory usage</span></span>

<span data-ttu-id="ed467-122">Перед началом сбора данных диагностики с целью поиска основной причины, которая привела к данному сценарию, необходимо убедиться в наличии утечки памяти (или ее увеличения).</span><span class="sxs-lookup"><span data-stu-id="ed467-122">Before you start collecting diagnostics data to help us root cause this scenario, you need to make sure you're actually seeing a memory leak (memory growth).</span></span> <span data-ttu-id="ed467-123">Для этого используйте [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="ed467-123">You can use the [dotnet-counters](dotnet-counters.md) tool to confirm that.</span></span>

<span data-ttu-id="ed467-124">Откройте окно консоли и перейдите к каталогу, в который вы скачали и распаковали [пример целевого объекта отладки](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/).</span><span class="sxs-lookup"><span data-stu-id="ed467-124">Open a console window and navigate to the directory where you downloaded and unzipped the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/).</span></span> <span data-ttu-id="ed467-125">Запустите целевой объект:</span><span class="sxs-lookup"><span data-stu-id="ed467-125">Run the target:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="ed467-126">В отдельном окне консоли найдите идентификатор процесса с помощью инструмента [dotnet-trace](dotnet-trace.md).</span><span class="sxs-lookup"><span data-stu-id="ed467-126">From a separate console, find the process ID using the [dotnet-trace](dotnet-trace.md) tool:</span></span>

```console
dotnet-trace ps
```

<span data-ttu-id="ed467-127">Результат должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ed467-127">The output should be similar to:</span></span>

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

<span data-ttu-id="ed467-128">Теперь проверьте использование управляемой памяти с помощью инструмента [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="ed467-128">Now, check managed memory usage with the [dotnet-counters](dotnet-counters.md) tool.</span></span> <span data-ttu-id="ed467-129">`--refresh-interval` задает время между обновлениями (в секундах):</span><span class="sxs-lookup"><span data-stu-id="ed467-129">The `--refresh-interval` specifies the number of seconds between refreshes:</span></span>

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

<span data-ttu-id="ed467-130">Динамические выходные данные должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ed467-130">The live output should be similar to:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    # of Assemblies Loaded                           118
    % Time in GC (since last GC)                       0
    Allocation Rate (Bytes / sec)                 37,896
    CPU Usage (%)                                      0
    Exceptions / sec                                   0
    GC Heap Size (MB)                                  4
    Gen 0 GC / sec                                     0
    Gen 0 Size (B)                                     0
    Gen 1 GC / sec                                     0
    Gen 1 Size (B)                                     0
    Gen 2 GC / sec                                     0
    Gen 2 Size (B)                                     0
    LOH Size (B)                                       0
    Monitor Lock Contention Count / sec                0
    Number of Active Timers                            1
    ThreadPool Completed Work Items / sec             10
    ThreadPool Queue Length                            0
    ThreadPool Threads Count                           1
    Working Set (MB)                                  83
```

<span data-ttu-id="ed467-131">Рассмотрите подробнее эту строку:</span><span class="sxs-lookup"><span data-stu-id="ed467-131">Focusing on this line:</span></span>

```console
    GC Heap Size (MB)                                  4
```

<span data-ttu-id="ed467-132">Как видите, сразу после запуска объем управляемой динамической памяти составляет 4 МБ.</span><span class="sxs-lookup"><span data-stu-id="ed467-132">You can see that the managed heap memory is 4 MB right after startup.</span></span>

<span data-ttu-id="ed467-133">Теперь перейдите по URL-адресу `http://localhost:5000/api/diagscenario/memleak/20000`.</span><span class="sxs-lookup"><span data-stu-id="ed467-133">Now, hit the URL `http://localhost:5000/api/diagscenario/memleak/20000`.</span></span>

<span data-ttu-id="ed467-134">Обратите внимание, что объем использования памяти увеличился до 30 МБ.</span><span class="sxs-lookup"><span data-stu-id="ed467-134">Observe that the memory usage has grown to 30 MB.</span></span>

```console
    GC Heap Size (MB)                                 30
```

<span data-ttu-id="ed467-135">Просмотрев данные об использовании памяти, вы можете точно определить, что происходит: утечка или увеличение памяти.</span><span class="sxs-lookup"><span data-stu-id="ed467-135">By watching the memory usage, you can safely say that memory is growing or leaking.</span></span> <span data-ttu-id="ed467-136">Следующим шагом является сбор правильных данных для анализа памяти.</span><span class="sxs-lookup"><span data-stu-id="ed467-136">The next step is to collect the right data for memory analysis.</span></span>

### <a name="generate-memory-dump"></a><span data-ttu-id="ed467-137">Создание дампа памяти</span><span class="sxs-lookup"><span data-stu-id="ed467-137">Generate memory dump</span></span>

<span data-ttu-id="ed467-138">При анализе возможных утечек памяти необходимо получить доступ к динамической памяти приложения.</span><span class="sxs-lookup"><span data-stu-id="ed467-138">When analyzing possible memory leaks, you need access to the app's memory heap.</span></span> <span data-ttu-id="ed467-139">Затем можно анализировать содержимое памяти.</span><span class="sxs-lookup"><span data-stu-id="ed467-139">Then you can analyze the memory contents.</span></span> <span data-ttu-id="ed467-140">Изучив связи между объектами, можно делать предположения о том, почему область памяти не освобождается.</span><span class="sxs-lookup"><span data-stu-id="ed467-140">Looking at relationships between objects, you create theories on why memory isn't being freed.</span></span> <span data-ttu-id="ed467-141">Общий источник диагностических данных — это дамп памяти в Windows или эквивалентный основной дамп в Linux.</span><span class="sxs-lookup"><span data-stu-id="ed467-141">A common diagnostics data source is a memory dump on Windows or the equivalent core dump on Linux.</span></span> <span data-ttu-id="ed467-142">Чтобы создать дамп приложения .NET Core, воспользуйтесь инструментом [dotnet-dump](dotnet-dump.md).</span><span class="sxs-lookup"><span data-stu-id="ed467-142">To generate a dump of a .NET Core application, you can use the [dotnet-dump)](dotnet-dump.md) tool.</span></span>

<span data-ttu-id="ed467-143">Выполните приведенную ниже команду, чтобы создать основной дамп в Linux для предварительно запущенного [примера целевого объекта отладки](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/):</span><span class="sxs-lookup"><span data-stu-id="ed467-143">Using the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) previously started, run the following command to generate a Linux core dump:</span></span>

```dotnetcli
dotnet-dump collect -p 4807
```

<span data-ttu-id="ed467-144">В результате в той же папке будет создан основной дамп.</span><span class="sxs-lookup"><span data-stu-id="ed467-144">The result is a core dump located in the same folder.</span></span>

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a><span data-ttu-id="ed467-145">Перезапуск неисправного процесса</span><span class="sxs-lookup"><span data-stu-id="ed467-145">Restart the failed process</span></span>

<span data-ttu-id="ed467-146">После сбора дампа у вас должно быть достаточно данных для диагностики неисправного процесса.</span><span class="sxs-lookup"><span data-stu-id="ed467-146">Once the dump is collected, you should have sufficient information to diagnose the failed process.</span></span> <span data-ttu-id="ed467-147">Если неисправный процесс запущен на рабочем сервере, это удачный момент для выполнения краткосрочного исправления проблем путем перезапуска процесса.</span><span class="sxs-lookup"><span data-stu-id="ed467-147">If the failed process is running on a production server, now it's the ideal time for short-term remediation by restarting the process.</span></span>

<span data-ttu-id="ed467-148">Вы уже завершили работу с [примером целевого объекта отладки](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) в рамках этого учебника и можете закрыть этот объект.</span><span class="sxs-lookup"><span data-stu-id="ed467-148">In this tutorial, you're now done with the [Sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) and you can close it.</span></span> <span data-ttu-id="ed467-149">Перейдите к терминалу, с которого запущен сервер, и нажмите клавиши `Control-C`.</span><span class="sxs-lookup"><span data-stu-id="ed467-149">Navigate to the terminal that started the server and press `Control-C`.</span></span>

### <a name="analyze-the-core-dump"></a><span data-ttu-id="ed467-150">Анализ основного дампа</span><span class="sxs-lookup"><span data-stu-id="ed467-150">Analyze the core dump</span></span>

<span data-ttu-id="ed467-151">Теперь, когда у вас есть основной дамп, используйте инструмент [dotnet-dump](dotnet-dump.md), чтобы проанализировать его:</span><span class="sxs-lookup"><span data-stu-id="ed467-151">Now that you have a core dump generated, use the [dotnet-dump)](dotnet-dump.md) tool to analyze the dump:</span></span>

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

<span data-ttu-id="ed467-152">Где `core_20190430_185145` — это имя основного дампа, который нужно проанализировать.</span><span class="sxs-lookup"><span data-stu-id="ed467-152">Where `core_20190430_185145` is the name of the core dump you want to analyze.</span></span>

> [!NOTE]
> <span data-ttu-id="ed467-153">Если отображается сообщение о том, что *libdl.so* не удалось найти, возможно, потребуется установить пакет *libc6-dev*.</span><span class="sxs-lookup"><span data-stu-id="ed467-153">If you see an error complaining that *libdl.so* cannot be found, you may have to install the *libc6-dev* package.</span></span> <span data-ttu-id="ed467-154">Дополнительные сведения см. в статье [Необходимые компоненты для .NET Core в Linux](../linux-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="ed467-154">For more information, see [Prerequisites for .NET Core on Linux](../linux-prerequisites.md).</span></span>

<span data-ttu-id="ed467-155">Отобразится командная строка для ввода команд SOS.</span><span class="sxs-lookup"><span data-stu-id="ed467-155">You'll be presented with a prompt where you can enter SOS commands.</span></span> <span data-ttu-id="ed467-156">Как правило, в первую очередь нужно просмотреть общее состояние управляемой динамической памяти:</span><span class="sxs-lookup"><span data-stu-id="ed467-156">Commonly, the first thing you want to look at is the overall state of the managed heap:</span></span>

```console
> dumpheap -stat

Statistics:
              MT    Count    TotalSize Class Name
...
00007f6c1eeefba8      576        59904 System.Reflection.RuntimeMethodInfo
00007f6c1dc021c8     1749        95696 System.SByte[]
00000000008c9db0     3847       116080      Free
00007f6c1e784a18      175       128640 System.Char[]
00007f6c1dbf5510      217       133504 System.Object[]
00007f6c1dc014c0      467       416464 System.Byte[]
00007f6c21625038        6      4063376 testwebapi.Controllers.Customer[]
00007f6c20a67498   200000      4800000 testwebapi.Controllers.Customer
00007f6c1dc00f90   206770     19494060 System.String
Total 428516 objects
```

<span data-ttu-id="ed467-157">В нашем примере видно, что большинство объектов принадлежат к типу `String` либо `Customer`.</span><span class="sxs-lookup"><span data-stu-id="ed467-157">Here you can see that most objects are either `String` or `Customer` objects.</span></span>

<span data-ttu-id="ed467-158">Вы можете повторно выполнить команду `dumpheap` с помощью таблицы методов, чтобы получить список всех экземпляров `String`:</span><span class="sxs-lookup"><span data-stu-id="ed467-158">You can use the `dumpheap` command again with the method table (MT) to get a list of all the `String` instances:</span></span>

```console
> dumpheap -mt 00007faddaa50f90

         Address               MT     Size
...
00007f6ad09421f8 00007faddaa50f90       94
...
00007f6ad0965b20 00007f6c1dc00f90       80
00007f6ad0965c10 00007f6c1dc00f90       80
00007f6ad0965d00 00007f6c1dc00f90       80
00007f6ad0965df0 00007f6c1dc00f90       80
00007f6ad0965ee0 00007f6c1dc00f90       80

Statistics:
              MT    Count    TotalSize Class Name
00007f6c1dc00f90   206770     19494060 System.String
Total 206770 objects
```

<span data-ttu-id="ed467-159">Теперь можно использовать команду `gcroot` в экземпляре `System.String`, чтобы узнать, как и зачем объект становится корневым.</span><span class="sxs-lookup"><span data-stu-id="ed467-159">You can now use the `gcroot` command on a `System.String` instance to see how and why the object is rooted.</span></span> <span data-ttu-id="ed467-160">Подождите, так как выполнение этой команды для объема памяти в 30 МБ занимает несколько минут:</span><span class="sxs-lookup"><span data-stu-id="ed467-160">Be patient because this command takes several minutes with a 30-MB heap:</span></span>

```console
> gcroot -all 00007f6ad09421f8

Thread 3f68:
    00007F6795BB58A0 00007F6C1D7D0745 System.Diagnostics.Tracing.CounterGroup.PollForValues() [/_/src/System.Private.CoreLib/shared/System/Diagnostics/Tracing/CounterGroup.cs @ 260]
        rbx:  (interior)
            ->  00007F6BDFFFF038 System.Object[]
            ->  00007F69D0033570 testwebapi.Controllers.Processor
            ->  00007F69D0033588 testwebapi.Controllers.CustomerCache
            ->  00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
            ->  00007F6C000148A0 testwebapi.Controllers.Customer[]
            ->  00007F6AD0942258 testwebapi.Controllers.Customer
            ->  00007F6AD09421F8 System.String

HandleTable:
    00007F6C98BB15F8 (pinned handle)
    -> 00007F6BDFFFF038 System.Object[]
    -> 00007F69D0033570 testwebapi.Controllers.Processor
    -> 00007F69D0033588 testwebapi.Controllers.CustomerCache
    -> 00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
    -> 00007F6C000148A0 testwebapi.Controllers.Customer[]
    -> 00007F6AD0942258 testwebapi.Controllers.Customer
    -> 00007F6AD09421F8 System.String

Found 2 roots.
```

<span data-ttu-id="ed467-161">Как видно, `String` непосредственно содержится в объекте `Customer` и косвенно в объекте `CustomerCache`.</span><span class="sxs-lookup"><span data-stu-id="ed467-161">You can see that the `String` is directly held by the `Customer` object and indirectly held by a `CustomerCache` object.</span></span>

<span data-ttu-id="ed467-162">Вы можете продолжить разгрузку объектов и увидите, что большинство объектов `String` следуют той же модели.</span><span class="sxs-lookup"><span data-stu-id="ed467-162">You can continue dumping out objects to see that most `String` objects follow a similar pattern.</span></span> <span data-ttu-id="ed467-163">На этом этапе в результате исследования получено достаточно информации, чтобы найти основную причину утечки в коде.</span><span class="sxs-lookup"><span data-stu-id="ed467-163">At this point, the investigation provided sufficient information to identify the root cause in your code.</span></span>

<span data-ttu-id="ed467-164">Эта общая процедура позволяет определить источник основных утечек памяти.</span><span class="sxs-lookup"><span data-stu-id="ed467-164">This general procedure allows you to identify the source of major memory leaks.</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="ed467-165">Очистка ресурсов</span><span class="sxs-lookup"><span data-stu-id="ed467-165">Clean up resources</span></span>

<span data-ttu-id="ed467-166">В этом учебнике вы запустили пример веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="ed467-166">In this tutorial, you started a sample web server.</span></span> <span data-ttu-id="ed467-167">Работа этого сервера должна быть завершена, как описано в разделе [Перезапуск неисправного процесса](#restart-the-failed-process).</span><span class="sxs-lookup"><span data-stu-id="ed467-167">This server should have been shut down as explained in the [Restart the failed process](#restart-the-failed-process) section.</span></span>

<span data-ttu-id="ed467-168">Вы также можете удалить созданный файл дампа.</span><span class="sxs-lookup"><span data-stu-id="ed467-168">You can also delete the dump file that was created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed467-169">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ed467-169">Next steps</span></span>

<span data-ttu-id="ed467-170">Поздравляем с завершением этого учебника!</span><span class="sxs-lookup"><span data-stu-id="ed467-170">Congratulations on completing this tutorial.</span></span>

<span data-ttu-id="ed467-171">Мы все еще публикуем дополнительные диагностические учебники.</span><span class="sxs-lookup"><span data-stu-id="ed467-171">We're still publishing more diagnostic tutorials.</span></span> <span data-ttu-id="ed467-172">С черновыми версиями можно ознакомиться в репозитории [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial).</span><span class="sxs-lookup"><span data-stu-id="ed467-172">You can read the draft versions on the [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial) repository.</span></span>

<span data-ttu-id="ed467-173">В этом учебнике были рассмотрены основные инструменты диагностики .NET.</span><span class="sxs-lookup"><span data-stu-id="ed467-173">This tutorial covered the basics of key .NET diagnostic tools.</span></span> <span data-ttu-id="ed467-174">Дополнительные сведения о расширенном использовании см. в следующей справочной документации:</span><span class="sxs-lookup"><span data-stu-id="ed467-174">For advanced usage, see the following reference documentation:</span></span>

* <span data-ttu-id="ed467-175">[dotnet-trace](dotnet-trace.md) для отображения списка процессов.</span><span class="sxs-lookup"><span data-stu-id="ed467-175">[dotnet-trace](dotnet-trace.md) to list processes.</span></span>
* <span data-ttu-id="ed467-176">[dotnet-counters](dotnet-counters.md) для проверки использования управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="ed467-176">[dotnet-counters](dotnet-counters.md) to check managed memory usage.</span></span>
* <span data-ttu-id="ed467-177">[dotnet-dump](dotnet-dump.md) для сбора и анализа файла дампа.</span><span class="sxs-lookup"><span data-stu-id="ed467-177">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file.</span></span>
