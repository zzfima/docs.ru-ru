---
title: Контроль ведения журнала .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 924d209cd1177ffc1702ebe958c58bfc29c22c38
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447688"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="9cbff-102">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9cbff-102">Controlling .NET Framework Logging</span></span>

<span data-ttu-id="9cbff-103">Трассировку событий для Windows (ETW) можно использовать для записи событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9cbff-103">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="9cbff-104">Для создания и просмотра трассировки можно использовать следующие инструменты.</span><span class="sxs-lookup"><span data-stu-id="9cbff-104">You can create and view traces by using the following tools:</span></span>

- <span data-ttu-id="9cbff-105">Программы командной строки [Logman](/windows-server/administration/windows-commands/logman) и [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1), входящие в состав операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="9cbff-105">The [Logman](/windows-server/administration/windows-commands/logman) and [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) command-line tools, which are included with the Windows operating system.</span></span>

- <span data-ttu-id="9cbff-106">Программы [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) в составе [набора средств для оценки производительности Windows](/windows-hardware/test/wpt/).</span><span class="sxs-lookup"><span data-stu-id="9cbff-106">The [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools in the [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span></span> <span data-ttu-id="9cbff-107">Дополнительные сведения о программе Xperf см. в [блоге, посвященном производительности Windows](https://blogs.msdn.microsoft.com/pigscanfly/tag/xperf/).</span><span class="sxs-lookup"><span data-stu-id="9cbff-107">For more information about Xperf, see the [Windows Performance blog](https://blogs.msdn.microsoft.com/pigscanfly/tag/xperf/).</span></span>

<span data-ttu-id="9cbff-108">Для регистрации событий среды CLR на компьютере должен быть установлен поставщик среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9cbff-108">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="9cbff-109">Чтобы проверить, установлен ли этот поставщик, введите в командной строке `logman query providers`.</span><span class="sxs-lookup"><span data-stu-id="9cbff-109">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="9cbff-110">Откроется список поставщиков.</span><span class="sxs-lookup"><span data-stu-id="9cbff-110">A list of providers is displayed.</span></span> <span data-ttu-id="9cbff-111">В этом списке должна находиться следующая запись для поставщика среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9cbff-111">This list should contain an entry for the CLR provider, as follows.</span></span>

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

<span data-ttu-id="9cbff-112">Если поставщик среды CLR не указан, его можно установить в Windows Vista и операционных системах более поздних версий с помощью программы командной строки Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil).</span><span class="sxs-lookup"><span data-stu-id="9cbff-112">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) command-line tool.</span></span> <span data-ttu-id="9cbff-113">Откройте окно командной строки от имени учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="9cbff-113">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="9cbff-114">Change the prompt directory to the .NET Framework 4 folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span><span class="sxs-lookup"><span data-stu-id="9cbff-114">Change the prompt directory to the .NET Framework 4 folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="9cbff-115">Эта папка содержит файл CLR-ETW.man.</span><span class="sxs-lookup"><span data-stu-id="9cbff-115">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="9cbff-116">Чтобы установить поставщик среды CLR, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9cbff-116">At the command prompt, type the following command to install the CLR provider:</span></span>

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a><span data-ttu-id="9cbff-117">Регистрация событий ETW в среде CLR</span><span class="sxs-lookup"><span data-stu-id="9cbff-117">Capturing CLR ETW Events</span></span>

<span data-ttu-id="9cbff-118">Программы командной строки [Logman](/windows-server/administration/windows-commands/logman) и [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) можно использовать для захвата событий трассировки событий Windows, а программы [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) и [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) — для расшифровки событий трассировки.</span><span class="sxs-lookup"><span data-stu-id="9cbff-118">You can use the [Logman](/windows-server/administration/windows-commands/logman) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) command-line tools to capture ETW events, and the [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools to decode the trace events.</span></span>

<span data-ttu-id="9cbff-119">Чтобы включить ведение журнала, пользователь должен указать следующее.</span><span class="sxs-lookup"><span data-stu-id="9cbff-119">To turn on logging, a user must specify three things:</span></span>

- <span data-ttu-id="9cbff-120">Поставщика, с которым следует обмениваться информацией.</span><span class="sxs-lookup"><span data-stu-id="9cbff-120">The provider to communicate to.</span></span>

- <span data-ttu-id="9cbff-121">64-разрядное число, представляющее набор ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="9cbff-121">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="9cbff-122">Каждое ключевое слово представляет набор событий, которые может включить поставщик.</span><span class="sxs-lookup"><span data-stu-id="9cbff-122">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="9cbff-123">Число представляет комбинированный набор ключевых слов, которые необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="9cbff-123">The number represents a combined set of keywords to turn on.</span></span>

- <span data-ttu-id="9cbff-124">Небольшое число, представляющее уровень (детализации) ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="9cbff-124">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="9cbff-125">Уровень 1 является наименее детальным, а уровень 5 — наиболее детальным.</span><span class="sxs-lookup"><span data-stu-id="9cbff-125">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="9cbff-126">Уровень 0 является значением по умолчанию, его назначение зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="9cbff-126">Level 0 is a default whose meaning is provider-specific.</span></span>

### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="9cbff-127">Регистрация событий ETW среды CLR с помощью программы Logman</span><span class="sxs-lookup"><span data-stu-id="9cbff-127">To capture CLR ETW events using Logman</span></span>

1. <span data-ttu-id="9cbff-128">В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="9cbff-128">At the command prompt, type:</span></span>

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     <span data-ttu-id="9cbff-129">Здесь:</span><span class="sxs-lookup"><span data-stu-id="9cbff-129">where:</span></span>

    - <span data-ttu-id="9cbff-130">Параметр `-p` задает GUID поставщика.</span><span class="sxs-lookup"><span data-stu-id="9cbff-130">The `-p` parameter identifies the provider GUID.</span></span>

    - <span data-ttu-id="9cbff-131">`0x1CCBD` задает категории создаваемых событий.</span><span class="sxs-lookup"><span data-stu-id="9cbff-131">`0x1CCBD` specifies the categories of events that will be raised.</span></span>

    - <span data-ttu-id="9cbff-132">`0x5` задает уровень регистрации (в данном случае подробный (5)).</span><span class="sxs-lookup"><span data-stu-id="9cbff-132">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>

    - <span data-ttu-id="9cbff-133">Параметр `-ets` указывает программе Logman отправлять команды сеансам трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="9cbff-133">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>

    - <span data-ttu-id="9cbff-134">Параметр `-ct perf`, определяет, что для записи отметки времени каждого события будет использоваться функция `QueryPerformanceCounter`.</span><span class="sxs-lookup"><span data-stu-id="9cbff-134">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>

2. <span data-ttu-id="9cbff-135">Чтобы остановить регистрацию событий, введите:</span><span class="sxs-lookup"><span data-stu-id="9cbff-135">To stop logging the events, type:</span></span>

     `logman stop clrevents -ets`

     <span data-ttu-id="9cbff-136">Эта команда создает двоичный файл трассировки clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="9cbff-136">This command creates a binary trace file named clrevents.etl.</span></span>

### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="9cbff-137">Регистрация событий ETW среды CLR с помощью программы Xperf</span><span class="sxs-lookup"><span data-stu-id="9cbff-137">To capture CLR ETW events using Xperf</span></span>

1. <span data-ttu-id="9cbff-138">В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="9cbff-138">At the command prompt, type:</span></span>

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     <span data-ttu-id="9cbff-139">где GUID — это GUID поставщика ETW среды CLR, а `0x1CCBD:5` выполняет трассировку всех событий на уровне 5 (детальный) и ниже.</span><span class="sxs-lookup"><span data-stu-id="9cbff-139">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>

2. <span data-ttu-id="9cbff-140">Чтобы остановить трассировку, введите:</span><span class="sxs-lookup"><span data-stu-id="9cbff-140">To stop tracing, type:</span></span>

     `Xperf -stop clr`

     <span data-ttu-id="9cbff-141">Эта команда создает файл трассировки clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="9cbff-141">This command creates a trace file named clrevents.etl.</span></span>

## <a name="viewing-clr-etw-events"></a><span data-ttu-id="9cbff-142">Просмотр событий ETW среды CLR</span><span class="sxs-lookup"><span data-stu-id="9cbff-142">Viewing CLR ETW Events</span></span>

<span data-ttu-id="9cbff-143">Перечисленные ниже команды используются для просмотра событий ETW среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9cbff-143">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="9cbff-144">Описание событий см. в разделе [События трассировки событий Windows в среде CLR](clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="9cbff-144">For a description of the events, see [CLR ETW Events](clr-etw-events.md).</span></span>

### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="9cbff-145">Просмотр событий ETW среды CLR с помощью программы Tracerpt</span><span class="sxs-lookup"><span data-stu-id="9cbff-145">To view CLR ETW events using Tracerpt</span></span>

- <span data-ttu-id="9cbff-146">В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="9cbff-146">At the command prompt, type:</span></span>

     `tracerpt clrevents.etl`

     <span data-ttu-id="9cbff-147">Эта команда создает два файла: dumpfile.xml и summary.txt.</span><span class="sxs-lookup"><span data-stu-id="9cbff-147">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="9cbff-148">Файл dumpfile.xml содержит список всех событий, а файл summary.txt содержит сводку событий.</span><span class="sxs-lookup"><span data-stu-id="9cbff-148">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>

### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="9cbff-149">Просмотр событий ETW среды CLR с помощью программы Xperf</span><span class="sxs-lookup"><span data-stu-id="9cbff-149">To view CLR ETW events using Xperf</span></span>

- <span data-ttu-id="9cbff-150">В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="9cbff-150">At the command prompt, type:</span></span>

     `xperf clrevents.etl`

     <span data-ttu-id="9cbff-151">Эта команда открывает программу Xperf просмотра ETL-файлов.</span><span class="sxs-lookup"><span data-stu-id="9cbff-151">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="9cbff-152">В этом средстве просмотра события CLR показаны в представлении **Универсальные события**.</span><span class="sxs-lookup"><span data-stu-id="9cbff-152">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="9cbff-153">Чтобы отобразить таблицу данных событий, распределенных по типу, в этом представлении выберите часовой пояс, щелкните правой кнопкой мыши и выберите **Сводка**.</span><span class="sxs-lookup"><span data-stu-id="9cbff-153">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="9cbff-154">Преобразование ETL-файла в файл данных с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="9cbff-154">To convert the .etl file to a comma-separated value file</span></span>

- <span data-ttu-id="9cbff-155">В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="9cbff-155">At the command prompt, type:</span></span>

     `xperf -i clrevents.etl -f clrevents.csv`

     <span data-ttu-id="9cbff-156">Эта команда XPerf помещает события в дамп в виде файла с разделителями-запятыми (CSV-файл), который впоследствии можно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="9cbff-156">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="9cbff-157">Поскольку у разных событий поля разные, этот CSV-файл содержит несколько строк заголовков, расположенных перед данными.</span><span class="sxs-lookup"><span data-stu-id="9cbff-157">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="9cbff-158">Первое поле каждой строки является типом события с указанием заголовка, который должен использоваться для определения остальных полей.</span><span class="sxs-lookup"><span data-stu-id="9cbff-158">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cbff-159">См. также</span><span class="sxs-lookup"><span data-stu-id="9cbff-159">See also</span></span>

- [<span data-ttu-id="9cbff-160">Windows Performance Toolkit</span><span class="sxs-lookup"><span data-stu-id="9cbff-160">Windows Performance Toolkit</span></span>](/windows-hardware/test/wpt/)
- [<span data-ttu-id="9cbff-161">События в среде CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="9cbff-161">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
