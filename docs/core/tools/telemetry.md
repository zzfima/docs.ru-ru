---
title: "Телеметрия средств интерфейса командной строки для .NET Core"
description: "Сведения о функциях телеметрии средств .NET Core, позволяющих собирать сведения об использовании для анализа, а также о собираемых данных и способе отключения этих функций."
keywords: ".NET,.NET Core, телеметрия"
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.translationtype: HT
ms.sourcegitcommit: c58ed1b3c09f1e358d0b66f6cf7186821601fd69
ms.openlocfilehash: 8ea8ee44a58c6aabfd09afbc7ef53239a9029c57
ms.contentlocale: ru-ru
ms.lasthandoff: 08/12/2017

---

# <a name="net-core-cli-tools-telemetry"></a><span data-ttu-id="ae2fa-104">Телеметрия средств интерфейса командной строки для .NET Core</span><span class="sxs-lookup"><span data-stu-id="ae2fa-104">.NET Core CLI Tools telemetry</span></span>

<span data-ttu-id="ae2fa-105">[Пакет SDK для .NET Core](index.md) включает в себя [функцию телеметрии](https://github.com/dotnet/cli/pull/2145), которая собирает сведения об использовании.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-105">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="ae2fa-106">Команде разработчиков .NET важно знать, как используются эти средства, чтобы иметь возможность улучшить их.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-106">It's important that the .NET Team understands how the tools are used so that we can improve them.</span></span> <span data-ttu-id="ae2fa-107">Дополнительные сведения см. в разделе [Что мы узнали благодаря данным телеметрии пакета SDK для .NET Core](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span><span class="sxs-lookup"><span data-stu-id="ae2fa-107">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="ae2fa-108">Данные собираются анонимно и публикуются в сводной форме для использования корпорацией Майкрософт и сообществом по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="ae2fa-108">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="ae2fa-109">Область</span><span class="sxs-lookup"><span data-stu-id="ae2fa-109">Scope</span></span>

<span data-ttu-id="ae2fa-110">Команда `dotnet` служит для запуска как приложений, так и интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-110">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="ae2fa-111">Сама по себе команда `dotnet` не собирает данные телеметрии.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-111">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="ae2fa-112">Этим занимаются команды интерфейса командной строки .NET Core, которые выполняются с помощью команды `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-112">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="ae2fa-113">Телеметрия *не включена*, если команда `dotnet` используется без дополнительных команд:</span><span class="sxs-lookup"><span data-stu-id="ae2fa-113">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="ae2fa-114">Телеметрия *включена* при использовании [команд интерфейса командной строки .NET Core](index.md), например:</span><span class="sxs-lookup"><span data-stu-id="ae2fa-114">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="behavior"></a><span data-ttu-id="ae2fa-115">Поведение</span><span class="sxs-lookup"><span data-stu-id="ae2fa-115">Behavior</span></span>

<span data-ttu-id="ae2fa-116">Функция телеметрии средств интерфейса командной строки .NET Core по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-116">The .NET Core CLI Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="ae2fa-117">Чтобы отключить ее, присвойте переменной среды `DOTNET_CLI_TELEMETRY_OPTOUT` значение `1` или `true`.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-117">Opt-out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="ae2fa-118">Точки данных</span><span class="sxs-lookup"><span data-stu-id="ae2fa-118">Data points</span></span>

<span data-ttu-id="ae2fa-119">Средство собирает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="ae2fa-119">The feature collects the following data:</span></span>

- <span data-ttu-id="ae2fa-120">метка времени вызова&#8224;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-120">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="ae2fa-121">вызываемая команда (например, build)&#8224;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-121">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="ae2fa-122">состоящий из трех октетов IP-адрес, используемый для определения географического местоположения&#8224;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-122">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="ae2fa-123">`ExitCode` команды;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-123">`ExitCode` of the command</span></span>
- <span data-ttu-id="ae2fa-124">средство выполнения тестов (для тестовых проектов);</span><span class="sxs-lookup"><span data-stu-id="ae2fa-124">Test runner (for test projects)</span></span>
- <span data-ttu-id="ae2fa-125">операционная система и ее версия&#8224;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-125">Operating system and version&#8224;</span></span>
- <span data-ttu-id="ae2fa-126">наличие идентификаторов сред выполнения в узле runtimes;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-126">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="ae2fa-127">версия пакета SDK для .NET Core&#8224.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-127">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="ae2fa-128">&#8224;Эта метрика публикуется.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-128">&#8224;This metric is published.</span></span>

<span data-ttu-id="ae2fa-129">Начиная с версии .NET Core SDK 2.0, собираются новые точки данных:</span><span class="sxs-lookup"><span data-stu-id="ae2fa-129">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="ae2fa-130">аргументы и параметры команды `dotnet`: собираются только известные аргументы и параметры (но не произвольные строки);</span><span class="sxs-lookup"><span data-stu-id="ae2fa-130">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="ae2fa-131">выполняется ли пакет SDK в контейнере;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-131">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="ae2fa-132">целевые платформы;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-132">Target frameworks.</span></span>
- <span data-ttu-id="ae2fa-133">хэшированный MAC-адрес: криптографически (SHA256) анонимный и уникальный идентификатор компьютера;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-133">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="ae2fa-134">эта метрика не публикуется;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-134">This metric is not published.</span></span>
- <span data-ttu-id="ae2fa-135">хэшированный текущий рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-135">Hashed current working directory.</span></span>

<span data-ttu-id="ae2fa-136">Функция не собирает личные данные, например имена пользователей и их адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-136">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="ae2fa-137">Она не проверяет код и не извлекает конфиденциальные данные уровня проекта, например имена и репозиторий.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-137">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="ae2fa-138">Данные отправляются по защищенному протоколу на серверы Майкрософт с помощью технологии [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), хранятся в режиме ограниченного доступа и публикуются из защищенных систем [хранилища Azure](https://azure.microsoft.com/services/storage/) с соблюдением строгих мер безопасности.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-138">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="ae2fa-139">Мы хотим узнать, как используются средства и правильно ли они работают, а не что вы создаете с их помощью.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-139">We want to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="ae2fa-140">Если у вас есть подозрения, что функция телеметрии собирает конфиденциальные данные или что мы обрабатываем данные небезопасным либо неподобающим образом, [отправьте сообщение о проблеме в репозитории dotnet/cli](https://github.com/dotnet/cli/issues) для изучения.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-140">If you suspect that the telemetry is collecting sensitive data or that we're insecurely or inappropriately handling data, [file an issue in the dotnet/cli repo issues](https://github.com/dotnet/cli/issues) for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="ae2fa-141">Опубликованные данные</span><span class="sxs-lookup"><span data-stu-id="ae2fa-141">Published data</span></span>

<span data-ttu-id="ae2fa-142">Данные публикуются ежеквартально и доступны на странице [данных по использованию пакета SDK для .NET](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae2fa-142">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="ae2fa-143">Файл данных содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="ae2fa-143">The columns of a data file are:</span></span>
- <span data-ttu-id="ae2fa-144">Метка времени</span><span class="sxs-lookup"><span data-stu-id="ae2fa-144">Timestamp</span></span>
- <span data-ttu-id="ae2fa-145">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-145">Occurrences&#8224;</span></span>
- <span data-ttu-id="ae2fa-146">Команда</span><span class="sxs-lookup"><span data-stu-id="ae2fa-146">Command</span></span>
- <span data-ttu-id="ae2fa-147">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="ae2fa-147">Geography&#8225;</span></span>
- <span data-ttu-id="ae2fa-148">OSFamily</span><span class="sxs-lookup"><span data-stu-id="ae2fa-148">OSFamily</span></span>
- <span data-ttu-id="ae2fa-149">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="ae2fa-149">RuntimeID</span></span>
- <span data-ttu-id="ae2fa-150">OSVersion</span><span class="sxs-lookup"><span data-stu-id="ae2fa-150">OSVersion</span></span>
- <span data-ttu-id="ae2fa-151">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="ae2fa-151">SDKVersion</span></span>

<span data-ttu-id="ae2fa-152">&#8224;В столбце *Occurrences* приводится совокупное число раз, которое команда использовалась для метрики соответствующей строки в указанный день.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-152">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span> 

<span data-ttu-id="ae2fa-153">&#8225;В столбце *Geography*, как правило, содержится название страны.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-153">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="ae2fa-154">В некоторых случаях в этом столбце может указываться Антарктида, либо потому что исследователи используют .NET Core в Антарктиде, либо из-за неправильных сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-154">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="ae2fa-155">Пример</span><span class="sxs-lookup"><span data-stu-id="ae2fa-155">Example</span></span>

| <span data-ttu-id="ae2fa-156">Метка времени</span><span class="sxs-lookup"><span data-stu-id="ae2fa-156">Timestamp</span></span>      | <span data-ttu-id="ae2fa-157">Occurrences</span><span class="sxs-lookup"><span data-stu-id="ae2fa-157">Occurrences</span></span> | <span data-ttu-id="ae2fa-158">Команда</span><span class="sxs-lookup"><span data-stu-id="ae2fa-158">Command</span></span> | <span data-ttu-id="ae2fa-159">Geography</span><span class="sxs-lookup"><span data-stu-id="ae2fa-159">Geography</span></span> | <span data-ttu-id="ae2fa-160">OSFamily</span><span class="sxs-lookup"><span data-stu-id="ae2fa-160">OSFamily</span></span> | <span data-ttu-id="ae2fa-161">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="ae2fa-161">RuntimeID</span></span>     | <span data-ttu-id="ae2fa-162">OSVersion</span><span class="sxs-lookup"><span data-stu-id="ae2fa-162">OSVersion</span></span> | <span data-ttu-id="ae2fa-163">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="ae2fa-163">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="ae2fa-164">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="ae2fa-164">4/16/2017 0:00</span></span> | <span data-ttu-id="ae2fa-165">8</span><span class="sxs-lookup"><span data-stu-id="ae2fa-165">8</span></span>           | <span data-ttu-id="ae2fa-166">запуск</span><span class="sxs-lookup"><span data-stu-id="ae2fa-166">run</span></span>     | <span data-ttu-id="ae2fa-167">Уганда</span><span class="sxs-lookup"><span data-stu-id="ae2fa-167">Uganda</span></span>    | <span data-ttu-id="ae2fa-168">Darwin</span><span class="sxs-lookup"><span data-stu-id="ae2fa-168">Darwin</span></span>   | <span data-ttu-id="ae2fa-169">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="ae2fa-169">osx.10.12-x64</span></span> | <span data-ttu-id="ae2fa-170">10.12</span><span class="sxs-lookup"><span data-stu-id="ae2fa-170">10.12</span></span>     | <span data-ttu-id="ae2fa-171">1.0.1</span><span class="sxs-lookup"><span data-stu-id="ae2fa-171">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="ae2fa-172">Наборы данных</span><span class="sxs-lookup"><span data-stu-id="ae2fa-172">Datasets</span></span>

[<span data-ttu-id="ae2fa-173">2016 — КВ3</span><span class="sxs-lookup"><span data-stu-id="ae2fa-173">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="ae2fa-174">2016 — КВ4</span><span class="sxs-lookup"><span data-stu-id="ae2fa-174">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="ae2fa-175">2017 — КВ1</span><span class="sxs-lookup"><span data-stu-id="ae2fa-175">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="ae2fa-176">2017 — КВ2</span><span class="sxs-lookup"><span data-stu-id="ae2fa-176">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

<span data-ttu-id="ae2fa-177">Дополнительные наборы данных публикуются с помощью стандартного формата URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-177">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="ae2fa-178">Замените `<YEAR>` на год, а `<QUARTER>` — на квартал (используйте `1`, `2`, `3` или `4`).</span><span class="sxs-lookup"><span data-stu-id="ae2fa-178">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="ae2fa-179">Файлы имеют формат значений с разделением знаками табуляции (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="ae2fa-179">The files are in tab-separated values (*TSV*) format.</span></span> 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a><span data-ttu-id="ae2fa-180">Лицензия</span><span class="sxs-lookup"><span data-stu-id="ae2fa-180">License</span></span>

<span data-ttu-id="ae2fa-181">Платформа .NET Core распространяется корпорацией Майкрософт на условиях [ЛИЦЕНЗИОННОГО СОГЛАШЕНИЯ НА ИСПОЛЬЗОВАНИЕ БИБЛИОТЕКИ MICROSOFT .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="ae2fa-181">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="ae2fa-182">Использование телеметрии определяется разделом "ДАННЫЕ" этого соглашения, который приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-182">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="ae2fa-183">Эта же лицензия распространяется на [пакеты NuGet .NET](https://www.nuget.org/profiles/dotnetframework), для которых, однако, телеметрия не включена (см. раздел [Область действия](#scope)).</span><span class="sxs-lookup"><span data-stu-id="ae2fa-183">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="ae2fa-184">Данные</span><span class="sxs-lookup"><span data-stu-id="ae2fa-184">DATA.</span></span> <span data-ttu-id="ae2fa-185">Программное обеспечение может собирать сведения о вас и его использовании, а также отправлять эти данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-185">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="ae2fa-186">Корпорация Майкрософт может использовать эти сведения для совершенствования своих продуктов и услуг.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-186">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="ae2fa-187">Сведения о сборе и использовании данных в справочной документации и заявлении о конфиденциальности см. на странице http://go.microsoft.com/fwlink/?LinkId=528096.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-187">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="ae2fa-188">Использование этого программного обеспечения рассматривается как согласие на применение ваших данных.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-188">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="ae2fa-189">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="ae2fa-189">Disclosure</span></span>

<span data-ttu-id="ae2fa-190">При первом выполнении одной из команд (например, `dotnet restore`) средства интерфейса командной строки .NET Core выводят приведенный ниже текст.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-190">The .NET Core CLI Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="ae2fa-191">Он может немного отличаться в зависимости от используемой версии пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-191">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="ae2fa-192">Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных.</span><span class="sxs-lookup"><span data-stu-id="ae2fa-192">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.
 
Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.
```

## <a name="see-also"></a><span data-ttu-id="ae2fa-193">См. также</span><span class="sxs-lookup"><span data-stu-id="ae2fa-193">See also</span></span>

[<span data-ttu-id="ae2fa-194">Что мы узнали благодаря данным телеметрии пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="ae2fa-194">What we've learned from .NET Core SDK Telemetry</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)  
<span data-ttu-id="ae2fa-195">[Справочные материалы по телеметрии (репозиторий dotnet/cli; ветвь release/2.0.0)](https://github.com/dotnet/cli/blob/release/2.0.0/src/dotnet/Telemetry.cs) </span><span class="sxs-lookup"><span data-stu-id="ae2fa-195">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/blob/release/2.0.0/src/dotnet/Telemetry.cs) </span></span>  
[<span data-ttu-id="ae2fa-196">Данные по использованию пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="ae2fa-196">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)

