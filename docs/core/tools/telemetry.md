---
title: Телеметрия пакета SDK для .NET Core
description: Сведения о функциях телеметрии пакета SDK для .NET Core, позволяющих собирать сведения об использовании для анализа, а также о собираемых данных и способе отключения этих функций.
author: richlander
ms.date: 06/20/2018
ms.custom: seodec18
ms.openlocfilehash: 40d9f3f698f513306e087753b4c33d09e8df0046
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397754"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="4a9e2-103">Телеметрия пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="4a9e2-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="4a9e2-104">[Пакет SDK для .NET Core](index.md) включает в себя [функцию телеметрии](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry), которая собирает сведения об использовании.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) that collects usage information.</span></span> <span data-ttu-id="4a9e2-105">Команде разработчиков .NET важно знать, как используются эти средства, чтобы их можно было улучшить.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-105">It's important that the .NET Team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="4a9e2-106">Дополнительные сведения см. в разделе [Что мы узнали благодаря данным телеметрии пакета SDK для .NET Core](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).</span><span class="sxs-lookup"><span data-stu-id="4a9e2-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="4a9e2-107">Данные собираются анонимно и публикуются в сводной форме для использования корпорацией Майкрософт и сообществом по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="4a9e2-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="4a9e2-108">Область</span><span class="sxs-lookup"><span data-stu-id="4a9e2-108">Scope</span></span>

<span data-ttu-id="4a9e2-109">Команда `dotnet` служит для запуска как приложений, так и интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="4a9e2-110">Сама по себе команда `dotnet` не собирает данные телеметрии.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="4a9e2-111">Этим занимаются команды интерфейса командной строки .NET Core, которые выполняются с помощью команды `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="4a9e2-112">Телеметрия *не включена*, если команда `dotnet` используется без дополнительных команд:</span><span class="sxs-lookup"><span data-stu-id="4a9e2-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="4a9e2-113">Телеметрия *включена* при использовании [команд интерфейса командной строки .NET Core](index.md), например:</span><span class="sxs-lookup"><span data-stu-id="4a9e2-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="4a9e2-114">Как отключить функцию</span><span class="sxs-lookup"><span data-stu-id="4a9e2-114">How to opt out</span></span>

<span data-ttu-id="4a9e2-115">Функция телеметрии пакета SDK для .NET Core по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-115">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="4a9e2-116">Чтобы отключить ее, присвойте переменной среды `DOTNET_CLI_TELEMETRY_OPTOUT` значение `1` или `true`.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-116">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="4a9e2-117">Точки данных</span><span class="sxs-lookup"><span data-stu-id="4a9e2-117">Data points</span></span>

<span data-ttu-id="4a9e2-118">Средство собирает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="4a9e2-118">The feature collects the following data:</span></span>

- <span data-ttu-id="4a9e2-119">метка времени вызова&#8224;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="4a9e2-120">вызываемая команда (например, build)&#8224;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="4a9e2-121">состоящий из трех октетов IP-адрес, используемый для определения географического местоположения&#8224;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="4a9e2-122">`ExitCode` команды;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="4a9e2-123">средство выполнения тестов (для тестовых проектов);</span><span class="sxs-lookup"><span data-stu-id="4a9e2-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="4a9e2-124">операционная система и ее версия&#8224;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="4a9e2-125">наличие идентификаторов сред выполнения в узле runtimes;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="4a9e2-126">версия пакета SDK для .NET Core&#8224.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="4a9e2-127">&#8224;Эта метрика публикуется.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="4a9e2-128">Начиная с пакета SDK для .NET Core 2.0, собираются новые точки данных:</span><span class="sxs-lookup"><span data-stu-id="4a9e2-128">Starting with .NET Core 2.0 SDK, new data points are collected:</span></span>

- <span data-ttu-id="4a9e2-129">аргументы и параметры команды `dotnet`: собираются только известные аргументы и параметры (но не произвольные строки);</span><span class="sxs-lookup"><span data-stu-id="4a9e2-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="4a9e2-130">выполняется ли пакет SDK в контейнере;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="4a9e2-131">целевые платформы;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-131">Target frameworks.</span></span>
- <span data-ttu-id="4a9e2-132">хэшированный MAC-адрес: криптографически (SHA256) анонимный и уникальный идентификатор компьютера;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="4a9e2-133">эта метрика не публикуется;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-133">This metric isn't published.</span></span>
- <span data-ttu-id="4a9e2-134">хэшированный текущий рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-134">Hashed current working directory.</span></span>

<span data-ttu-id="4a9e2-135">Функция не собирает личные данные, например имена пользователей и их адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="4a9e2-136">Она не проверяет код и не извлекает конфиденциальные данные уровня проекта, например имена и репозиторий.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="4a9e2-137">Данные отправляются по защищенному протоколу на серверы Майкрософт с помощью технологии [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), хранятся в режиме ограниченного доступа и публикуются из защищенных систем [хранилища Azure](https://azure.microsoft.com/services/storage/) с соблюдением строгих мер безопасности.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="4a9e2-138">Команда разработчиков .NET хочет узнать, как используются средства и правильно ли они работают, а не что вы создаете с их помощью.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-138">The .NET team wants to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="4a9e2-139">Если у вас есть подозрения, что функция телеметрии собирает конфиденциальные данные или что мы обрабатываем данные небезопасным либо неподобающим образом, отправьте сообщение о проблеме в репозитории [dotnet/cli](https://github.com/dotnet/cli/issues) для изучения.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-139">If you suspect that the telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="4a9e2-140">Опубликованные данные</span><span class="sxs-lookup"><span data-stu-id="4a9e2-140">Published data</span></span>

<span data-ttu-id="4a9e2-141">Данные публикуются ежеквартально и доступны на странице [данных по использованию пакета SDK для .NET](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="4a9e2-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="4a9e2-142">Файл данных содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="4a9e2-142">The columns of a data file are:</span></span>

- <span data-ttu-id="4a9e2-143">Метка времени</span><span class="sxs-lookup"><span data-stu-id="4a9e2-143">Timestamp</span></span>
- <span data-ttu-id="4a9e2-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="4a9e2-145">Команда</span><span class="sxs-lookup"><span data-stu-id="4a9e2-145">Command</span></span>
- <span data-ttu-id="4a9e2-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="4a9e2-146">Geography&#8225;</span></span>
- <span data-ttu-id="4a9e2-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="4a9e2-147">OSFamily</span></span>
- <span data-ttu-id="4a9e2-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="4a9e2-148">RuntimeID</span></span>
- <span data-ttu-id="4a9e2-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="4a9e2-149">OSVersion</span></span>
- <span data-ttu-id="4a9e2-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="4a9e2-150">SDKVersion</span></span>

<span data-ttu-id="4a9e2-151">&#8224;В столбце *Occurrences* приводится совокупное число раз, которое команда использовалась для метрики соответствующей строки в указанный день.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span>

<span data-ttu-id="4a9e2-152">&#8225;В столбце *Geography*, как правило, отображается название страны или региона.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-152">&#8225;Typically, the *Geography* column displays the name of a country/region.</span></span> <span data-ttu-id="4a9e2-153">В некоторых случаях в этом столбце может указываться Антарктида, либо потому что исследователи используют .NET Core в Антарктиде, либо из-за неправильных сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="4a9e2-154">Пример</span><span class="sxs-lookup"><span data-stu-id="4a9e2-154">Example</span></span>

| <span data-ttu-id="4a9e2-155">Метка времени</span><span class="sxs-lookup"><span data-stu-id="4a9e2-155">Timestamp</span></span>      | <span data-ttu-id="4a9e2-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="4a9e2-156">Occurrences</span></span> | <span data-ttu-id="4a9e2-157">Команда</span><span class="sxs-lookup"><span data-stu-id="4a9e2-157">Command</span></span> | <span data-ttu-id="4a9e2-158">Geography</span><span class="sxs-lookup"><span data-stu-id="4a9e2-158">Geography</span></span> | <span data-ttu-id="4a9e2-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="4a9e2-159">OSFamily</span></span> | <span data-ttu-id="4a9e2-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="4a9e2-160">RuntimeID</span></span>     | <span data-ttu-id="4a9e2-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="4a9e2-161">OSVersion</span></span> | <span data-ttu-id="4a9e2-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="4a9e2-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="4a9e2-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="4a9e2-163">4/16/2017 0:00</span></span> | <span data-ttu-id="4a9e2-164">8</span><span class="sxs-lookup"><span data-stu-id="4a9e2-164">8</span></span>           | <span data-ttu-id="4a9e2-165">запуск</span><span class="sxs-lookup"><span data-stu-id="4a9e2-165">run</span></span>     | <span data-ttu-id="4a9e2-166">Уганда</span><span class="sxs-lookup"><span data-stu-id="4a9e2-166">Uganda</span></span>    | <span data-ttu-id="4a9e2-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="4a9e2-167">Darwin</span></span>   | <span data-ttu-id="4a9e2-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="4a9e2-168">osx.10.12-x64</span></span> | <span data-ttu-id="4a9e2-169">10.12</span><span class="sxs-lookup"><span data-stu-id="4a9e2-169">10.12</span></span>     | <span data-ttu-id="4a9e2-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="4a9e2-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="4a9e2-171">Наборы данных</span><span class="sxs-lookup"><span data-stu-id="4a9e2-171">Datasets</span></span>

- [<span data-ttu-id="4a9e2-172">2016 — КВ3</span><span class="sxs-lookup"><span data-stu-id="4a9e2-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)
- [<span data-ttu-id="4a9e2-173">2016 — КВ4</span><span class="sxs-lookup"><span data-stu-id="4a9e2-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)
- [<span data-ttu-id="4a9e2-174">2017 — КВ1</span><span class="sxs-lookup"><span data-stu-id="4a9e2-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)
- [<span data-ttu-id="4a9e2-175">2017 — КВ2</span><span class="sxs-lookup"><span data-stu-id="4a9e2-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)
- [<span data-ttu-id="4a9e2-176">2017 — КВ3</span><span class="sxs-lookup"><span data-stu-id="4a9e2-176">2017 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)
- [<span data-ttu-id="4a9e2-177">2017 — КВ4</span><span class="sxs-lookup"><span data-stu-id="4a9e2-177">2017 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)

<span data-ttu-id="4a9e2-178">Дополнительные наборы данных публикуются с помощью стандартного формата URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-178">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="4a9e2-179">Замените `<YEAR>` на год, а `<QUARTER>` — на квартал (используйте `1`, `2`, `3` или `4`).</span><span class="sxs-lookup"><span data-stu-id="4a9e2-179">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="4a9e2-180">Файлы имеют формат значений с разделением знаками табуляции (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="4a9e2-180">The files are in tab-separated values (*TSV*) format.</span></span>

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a><span data-ttu-id="4a9e2-181">Лицензия</span><span class="sxs-lookup"><span data-stu-id="4a9e2-181">License</span></span>

<span data-ttu-id="4a9e2-182">Корпорация Майкрософт предоставляет .NET Core по [условиям лицензионного соглашения на использование библиотека Microsoft .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="4a9e2-182">The Microsoft distribution of .NET Core is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="4a9e2-183">Дополнительные сведения о сборе и обработке данных см. в разделе "Данные".</span><span class="sxs-lookup"><span data-stu-id="4a9e2-183">For details on data collection and processing, see the section entitled "Data."</span></span>

<span data-ttu-id="4a9e2-184">Эта же лицензия распространяется на [пакеты NuGet .NET](https://www.nuget.org/profiles/dotnetframework), для которых, однако, телеметрия не включена (см. раздел [Область действия](#scope)).</span><span class="sxs-lookup"><span data-stu-id="4a9e2-184">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

## <a name="disclosure"></a><span data-ttu-id="4a9e2-185">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="4a9e2-185">Disclosure</span></span>

<span data-ttu-id="4a9e2-186">При первом выполнении одной из [команд .NET Core CLI](index.md) (например, `dotnet restore`) пакет SDK для .NET Core выводит следующий текст.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-186">The .NET Core SDK displays the following text when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet restore`).</span></span> <span data-ttu-id="4a9e2-187">Он может немного отличаться в зависимости от используемой версии пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-187">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="4a9e2-188">Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных.</span><span class="sxs-lookup"><span data-stu-id="4a9e2-188">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core: https://aka.ms/dotnet-docs
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli-docs

Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience.
The data is anonymous and doesn't include command-line arguments.
The data is collected by Microsoft and shared with the community.
You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="see-also"></a><span data-ttu-id="4a9e2-189">См. также</span><span class="sxs-lookup"><span data-stu-id="4a9e2-189">See also</span></span>

- [<span data-ttu-id="4a9e2-190">Что мы узнали благодаря данным телеметрии пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="4a9e2-190">What we've learned from .NET Core SDK Telemetry</span></span>](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/)
- [<span data-ttu-id="4a9e2-191">Справочные материалы по телеметрии (репозиторий dotnet/cli)</span><span class="sxs-lookup"><span data-stu-id="4a9e2-191">Telemetry reference source (dotnet/cli repo)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
- [<span data-ttu-id="4a9e2-192">Данные по использованию пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="4a9e2-192">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
