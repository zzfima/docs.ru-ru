---
title: Телеметрия средств интерфейса командной строки для .NET Core
description: Сведения о функциях телеметрии средств .NET Core, позволяющих собирать сведения об использовании для анализа, а также о собираемых данных и способе отключения этих функций.
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.openlocfilehash: 4c04867f5db512ef53c23ec41ea66db570a82021
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216087"
---
# <a name="net-core-cli-tools-telemetry"></a><span data-ttu-id="56b12-103">Телеметрия средств интерфейса командной строки для .NET Core</span><span class="sxs-lookup"><span data-stu-id="56b12-103">.NET Core CLI Tools telemetry</span></span>

<span data-ttu-id="56b12-104">[Пакет SDK для .NET Core](index.md) включает в себя [функцию телеметрии](https://github.com/dotnet/cli/pull/2145), которая собирает сведения об использовании.</span><span class="sxs-lookup"><span data-stu-id="56b12-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="56b12-105">Команде разработчиков .NET важно знать, как используются эти средства, чтобы иметь возможность улучшить их.</span><span class="sxs-lookup"><span data-stu-id="56b12-105">It's important that the .NET Team understands how the tools are used so that we can improve them.</span></span> <span data-ttu-id="56b12-106">Дополнительные сведения см. в разделе [Что мы узнали благодаря данным телеметрии пакета SDK для .NET Core](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span><span class="sxs-lookup"><span data-stu-id="56b12-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="56b12-107">Данные собираются анонимно и публикуются в сводной форме для использования корпорацией Майкрософт и сообществом по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="56b12-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="56b12-108">Область</span><span class="sxs-lookup"><span data-stu-id="56b12-108">Scope</span></span>

<span data-ttu-id="56b12-109">Команда `dotnet` служит для запуска как приложений, так и интерфейса командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="56b12-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="56b12-110">Сама по себе команда `dotnet` не собирает данные телеметрии.</span><span class="sxs-lookup"><span data-stu-id="56b12-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="56b12-111">Этим занимаются команды интерфейса командной строки .NET Core, которые выполняются с помощью команды `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="56b12-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="56b12-112">Телеметрия *не включена*, если команда `dotnet` используется без дополнительных команд:</span><span class="sxs-lookup"><span data-stu-id="56b12-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="56b12-113">Телеметрия *включена* при использовании [команд интерфейса командной строки .NET Core](index.md), например:</span><span class="sxs-lookup"><span data-stu-id="56b12-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`


## <a name="behavior"></a><span data-ttu-id="56b12-114">Поведение</span><span class="sxs-lookup"><span data-stu-id="56b12-114">Behavior</span></span>

<span data-ttu-id="56b12-115">Функция телеметрии средств интерфейса командной строки .NET Core по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="56b12-115">The .NET Core CLI Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="56b12-116">Чтобы отключить ее, присвойте переменной среды `DOTNET_CLI_TELEMETRY_OPTOUT` значение `1` или `true`.</span><span class="sxs-lookup"><span data-stu-id="56b12-116">Opt-out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="56b12-117">Точки данных</span><span class="sxs-lookup"><span data-stu-id="56b12-117">Data points</span></span>

<span data-ttu-id="56b12-118">Средство собирает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="56b12-118">The feature collects the following data:</span></span>

- <span data-ttu-id="56b12-119">метка времени вызова&#8224;</span><span class="sxs-lookup"><span data-stu-id="56b12-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="56b12-120">вызываемая команда (например, build)&#8224;</span><span class="sxs-lookup"><span data-stu-id="56b12-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="56b12-121">состоящий из трех октетов IP-адрес, используемый для определения географического местоположения&#8224;</span><span class="sxs-lookup"><span data-stu-id="56b12-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="56b12-122">`ExitCode` команды;</span><span class="sxs-lookup"><span data-stu-id="56b12-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="56b12-123">средство выполнения тестов (для тестовых проектов);</span><span class="sxs-lookup"><span data-stu-id="56b12-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="56b12-124">операционная система и ее версия&#8224;</span><span class="sxs-lookup"><span data-stu-id="56b12-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="56b12-125">наличие идентификаторов сред выполнения в узле runtimes;</span><span class="sxs-lookup"><span data-stu-id="56b12-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="56b12-126">версия пакета SDK для .NET Core&#8224.</span><span class="sxs-lookup"><span data-stu-id="56b12-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="56b12-127">&#8224;Эта метрика публикуется.</span><span class="sxs-lookup"><span data-stu-id="56b12-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="56b12-128">Начиная с версии .NET Core SDK 2.0, собираются новые точки данных:</span><span class="sxs-lookup"><span data-stu-id="56b12-128">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="56b12-129">аргументы и параметры команды `dotnet`: собираются только известные аргументы и параметры (но не произвольные строки);</span><span class="sxs-lookup"><span data-stu-id="56b12-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="56b12-130">выполняется ли пакет SDK в контейнере;</span><span class="sxs-lookup"><span data-stu-id="56b12-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="56b12-131">целевые платформы;</span><span class="sxs-lookup"><span data-stu-id="56b12-131">Target frameworks.</span></span>
- <span data-ttu-id="56b12-132">хэшированный MAC-адрес: криптографически (SHA256) анонимный и уникальный идентификатор компьютера;</span><span class="sxs-lookup"><span data-stu-id="56b12-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="56b12-133">эта метрика не публикуется;</span><span class="sxs-lookup"><span data-stu-id="56b12-133">This metric is not published.</span></span>
- <span data-ttu-id="56b12-134">хэшированный текущий рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="56b12-134">Hashed current working directory.</span></span>

<span data-ttu-id="56b12-135">Функция не собирает личные данные, например имена пользователей и их адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="56b12-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="56b12-136">Она не проверяет код и не извлекает конфиденциальные данные уровня проекта, например имена и репозиторий.</span><span class="sxs-lookup"><span data-stu-id="56b12-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="56b12-137">Данные отправляются по защищенному протоколу на серверы Майкрософт с помощью технологии [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), хранятся в режиме ограниченного доступа и публикуются из защищенных систем [хранилища Azure](https://azure.microsoft.com/services/storage/) с соблюдением строгих мер безопасности.</span><span class="sxs-lookup"><span data-stu-id="56b12-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="56b12-138">Мы хотим узнать, как используются средства и правильно ли они работают, а не что вы создаете с их помощью.</span><span class="sxs-lookup"><span data-stu-id="56b12-138">We want to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="56b12-139">Если у вас есть подозрения, что функция телеметрии собирает конфиденциальные данные или что мы обрабатываем данные небезопасным либо неподобающим образом, [отправьте сообщение о проблеме в репозитории dotnet/cli](https://github.com/dotnet/cli/issues) для изучения.</span><span class="sxs-lookup"><span data-stu-id="56b12-139">If you suspect that the telemetry is collecting sensitive data or that we're insecurely or inappropriately handling data, [file an issue in the dotnet/cli repo issues](https://github.com/dotnet/cli/issues) for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="56b12-140">Опубликованные данные</span><span class="sxs-lookup"><span data-stu-id="56b12-140">Published data</span></span>

<span data-ttu-id="56b12-141">Данные публикуются ежеквартально и доступны на странице [данных по использованию пакета SDK для .NET](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="56b12-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="56b12-142">Файл данных содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="56b12-142">The columns of a data file are:</span></span>
- <span data-ttu-id="56b12-143">Метка времени</span><span class="sxs-lookup"><span data-stu-id="56b12-143">Timestamp</span></span>
- <span data-ttu-id="56b12-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="56b12-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="56b12-145">Команда</span><span class="sxs-lookup"><span data-stu-id="56b12-145">Command</span></span>
- <span data-ttu-id="56b12-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="56b12-146">Geography&#8225;</span></span>
- <span data-ttu-id="56b12-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="56b12-147">OSFamily</span></span>
- <span data-ttu-id="56b12-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="56b12-148">RuntimeID</span></span>
- <span data-ttu-id="56b12-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="56b12-149">OSVersion</span></span>
- <span data-ttu-id="56b12-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="56b12-150">SDKVersion</span></span>

<span data-ttu-id="56b12-151">&#8224;В столбце *Occurrences* приводится совокупное число раз, которое команда использовалась для метрики соответствующей строки в указанный день.</span><span class="sxs-lookup"><span data-stu-id="56b12-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span> 

<span data-ttu-id="56b12-152">&#8225;В столбце *Geography*, как правило, содержится название страны.</span><span class="sxs-lookup"><span data-stu-id="56b12-152">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="56b12-153">В некоторых случаях в этом столбце может указываться Антарктида, либо потому что исследователи используют .NET Core в Антарктиде, либо из-за неправильных сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="56b12-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="56b12-154">Пример</span><span class="sxs-lookup"><span data-stu-id="56b12-154">Example</span></span>

| <span data-ttu-id="56b12-155">Метка времени</span><span class="sxs-lookup"><span data-stu-id="56b12-155">Timestamp</span></span>      | <span data-ttu-id="56b12-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="56b12-156">Occurrences</span></span> | <span data-ttu-id="56b12-157">Команда</span><span class="sxs-lookup"><span data-stu-id="56b12-157">Command</span></span> | <span data-ttu-id="56b12-158">Geography</span><span class="sxs-lookup"><span data-stu-id="56b12-158">Geography</span></span> | <span data-ttu-id="56b12-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="56b12-159">OSFamily</span></span> | <span data-ttu-id="56b12-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="56b12-160">RuntimeID</span></span>     | <span data-ttu-id="56b12-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="56b12-161">OSVersion</span></span> | <span data-ttu-id="56b12-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="56b12-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="56b12-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="56b12-163">4/16/2017 0:00</span></span> | <span data-ttu-id="56b12-164">8</span><span class="sxs-lookup"><span data-stu-id="56b12-164">8</span></span>           | <span data-ttu-id="56b12-165">запуск</span><span class="sxs-lookup"><span data-stu-id="56b12-165">run</span></span>     | <span data-ttu-id="56b12-166">Уганда</span><span class="sxs-lookup"><span data-stu-id="56b12-166">Uganda</span></span>    | <span data-ttu-id="56b12-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="56b12-167">Darwin</span></span>   | <span data-ttu-id="56b12-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="56b12-168">osx.10.12-x64</span></span> | <span data-ttu-id="56b12-169">10.12</span><span class="sxs-lookup"><span data-stu-id="56b12-169">10.12</span></span>     | <span data-ttu-id="56b12-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="56b12-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="56b12-171">Наборы данных</span><span class="sxs-lookup"><span data-stu-id="56b12-171">Datasets</span></span>

[<span data-ttu-id="56b12-172">2016 — КВ3</span><span class="sxs-lookup"><span data-stu-id="56b12-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="56b12-173">2016 — КВ4</span><span class="sxs-lookup"><span data-stu-id="56b12-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="56b12-174">2017 — КВ1</span><span class="sxs-lookup"><span data-stu-id="56b12-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="56b12-175">2017 — КВ2</span><span class="sxs-lookup"><span data-stu-id="56b12-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

<span data-ttu-id="56b12-176">Дополнительные наборы данных публикуются с помощью стандартного формата URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="56b12-176">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="56b12-177">Замените `<YEAR>` на год, а `<QUARTER>` — на квартал (используйте `1`, `2`, `3` или `4`).</span><span class="sxs-lookup"><span data-stu-id="56b12-177">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="56b12-178">Файлы имеют формат значений с разделением знаками табуляции (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="56b12-178">The files are in tab-separated values (*TSV*) format.</span></span> 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a><span data-ttu-id="56b12-179">Лицензия</span><span class="sxs-lookup"><span data-stu-id="56b12-179">License</span></span>

<span data-ttu-id="56b12-180">Платформа .NET Core распространяется корпорацией Майкрософт на условиях [ЛИЦЕНЗИОННОГО СОГЛАШЕНИЯ НА ИСПОЛЬЗОВАНИЕ БИБЛИОТЕКИ MICROSOFT .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="56b12-180">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="56b12-181">Использование телеметрии определяется разделом "ДАННЫЕ" этого соглашения, который приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="56b12-181">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="56b12-182">Эта же лицензия распространяется на [пакеты NuGet .NET](https://www.nuget.org/profiles/dotnetframework), для которых, однако, телеметрия не включена (см. раздел [Область действия](#scope)).</span><span class="sxs-lookup"><span data-stu-id="56b12-182">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="56b12-183">Данные</span><span class="sxs-lookup"><span data-stu-id="56b12-183">DATA.</span></span> <span data-ttu-id="56b12-184">Программное обеспечение может собирать сведения о вас и его использовании, а также отправлять эти данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="56b12-184">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="56b12-185">Корпорация Майкрософт может использовать эти сведения для совершенствования своих продуктов и услуг.</span><span class="sxs-lookup"><span data-stu-id="56b12-185">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="56b12-186">Сведения о сборе и использовании данных в справочной документации и заявлении о конфиденциальности см. на странице http://go.microsoft.com/fwlink/?LinkId=528096.</span><span class="sxs-lookup"><span data-stu-id="56b12-186">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="56b12-187">Использование этого программного обеспечения рассматривается как согласие на применение ваших данных.</span><span class="sxs-lookup"><span data-stu-id="56b12-187">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="56b12-188">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="56b12-188">Disclosure</span></span>

<span data-ttu-id="56b12-189">При первом выполнении одной из команд (например, `dotnet restore`) средства интерфейса командной строки .NET Core выводят приведенный ниже текст.</span><span class="sxs-lookup"><span data-stu-id="56b12-189">The .NET Core CLI Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="56b12-190">Он может немного отличаться в зависимости от используемой версии пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="56b12-190">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="56b12-191">Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных.</span><span class="sxs-lookup"><span data-stu-id="56b12-191">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="56b12-192">См. также</span><span class="sxs-lookup"><span data-stu-id="56b12-192">See also</span></span>

[<span data-ttu-id="56b12-193">Что мы узнали благодаря данным телеметрии пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="56b12-193">What we've learned from .NET Core SDK Telemetry</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)  
<span data-ttu-id="56b12-194">[Справочные материалы по телеметрии (репозиторий dotnet/cli; ветвь release/2.0.0)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry) </span><span class="sxs-lookup"><span data-stu-id="56b12-194">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry) </span></span>  
[<span data-ttu-id="56b12-195">Данные по использованию пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="56b12-195">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
