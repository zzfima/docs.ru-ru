---
title: Сбор данных телеметрии интерфейсом командной строки ML.NET
description: Узнайте о функциях телеметрии в интерфейсе командной строки CLI ML.NET, собирающих сведения об использовании для анализа, а также о собираемых данных и способе отключения этих функций. Также см. ссылки на лицензионное соглашение .NET и информацию о соответствии GDPR корпорации Майкрософт.
ms.topic: conceptual
ms.date: 05/05/2019
ms.custom: ''
ms.openlocfilehash: 49ebd6c9e1b77c85d891b8c9fb8cbd5c66b478a9
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065547"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="43f2d-104">Сбор данных телеметрии интерфейсом командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="43f2d-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="43f2d-105">[Интерфейс командной строки ML.NET](http://aka.ms/mlnet-cli) включает функцию телеметрии, которая собирает анонимные данные об использовании, агрегированные для использования корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="43f2d-105">The [ML.NET CLI](http://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="43f2d-106">Как корпорация Майкрософт использует данные</span><span class="sxs-lookup"><span data-stu-id="43f2d-106">How Microsoft uses the data</span></span>

<span data-ttu-id="43f2d-107">Команда разработчиков использует данные телеметрии интерфейса командной строки ML.NET для улучшения своих инструментов.</span><span class="sxs-lookup"><span data-stu-id="43f2d-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="43f2d-108">Например, если клиенты редко используют ту или иную задачу машинного обучения, команда разработчиков анализирует причины и на основе результатов анализа выбирает приоритетные функции для разработки.</span><span class="sxs-lookup"><span data-stu-id="43f2d-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="43f2d-109">Телеметрия интерфейса командной строки ML.NET CLI также помогает при отладке таких проблем, как сбои и аномалии кода.</span><span class="sxs-lookup"><span data-stu-id="43f2d-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span> 

<span data-ttu-id="43f2d-110">Несмотря на всю пользу этих данных для группы разработчиков, не все готовы отправлять эти данные.</span><span class="sxs-lookup"><span data-stu-id="43f2d-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="43f2d-111">Узнайте, как отключить телеметрию.</span><span class="sxs-lookup"><span data-stu-id="43f2d-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="43f2d-112">Область</span><span class="sxs-lookup"><span data-stu-id="43f2d-112">Scope</span></span>

<span data-ttu-id="43f2d-113">Команда `mlnet` запускает интерфейс командной строки ML.NET, но сама она данные телеметрии не собирает.</span><span class="sxs-lookup"><span data-stu-id="43f2d-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="43f2d-114">Телеметрия *не включается*, если команда `mlnet` используется без дополнительных команд:</span><span class="sxs-lookup"><span data-stu-id="43f2d-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="43f2d-115">Например:</span><span class="sxs-lookup"><span data-stu-id="43f2d-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="43f2d-116">Телеметрия *включается* при выполнении [команды интерфейса командной строки ML.NET](../reference/ml-net-cli-reference.md), такой как `mlnet auto-train`.</span><span class="sxs-lookup"><span data-stu-id="43f2d-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet auto-train`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="43f2d-117">Отказ от сбора данных</span><span class="sxs-lookup"><span data-stu-id="43f2d-117">Opt out of data collection</span></span>

<span data-ttu-id="43f2d-118">Функция телеметрии в интерфейсе командной строки ML.NET по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="43f2d-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="43f2d-119">Чтобы отключить ее, присвойте переменной среды `DOTNET_CLI_TELEMETRY_OPTOUT` значение `1` или `true`.</span><span class="sxs-lookup"><span data-stu-id="43f2d-119">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="43f2d-120">Эта переменная среды применяется к средству командной строки .NET глобально.</span><span class="sxs-lookup"><span data-stu-id="43f2d-120">This environment variable applies globally to the .NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="43f2d-121">Собираемые точки данных</span><span class="sxs-lookup"><span data-stu-id="43f2d-121">Data points collected</span></span>

<span data-ttu-id="43f2d-122">Средство собирает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="43f2d-122">The feature collects the following data:</span></span>

- <span data-ttu-id="43f2d-123">вызываемые команды, такие как `auto-train`;</span><span class="sxs-lookup"><span data-stu-id="43f2d-123">Which commands are invoked, such as `auto-train`</span></span>
- <span data-ttu-id="43f2d-124">хэшированный MAC-адрес: криптографически (SHA256) анонимный и уникальный идентификатор компьютера;</span><span class="sxs-lookup"><span data-stu-id="43f2d-124">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="43f2d-125">метка времени вызова;</span><span class="sxs-lookup"><span data-stu-id="43f2d-125">Timestamp of an invocation</span></span>
- <span data-ttu-id="43f2d-126">состоящий из трех октетов IP-адрес, используемый для определения географического местоположения;</span><span class="sxs-lookup"><span data-stu-id="43f2d-126">Three octet IP address used only to determine geographical location</span></span>
- <span data-ttu-id="43f2d-127">имена всех используемых аргументов и параметров,</span><span class="sxs-lookup"><span data-stu-id="43f2d-127">Name of all arguments/parameters used.</span></span> <span data-ttu-id="43f2d-128">кроме клиентских значений, таких как строки;</span><span class="sxs-lookup"><span data-stu-id="43f2d-128">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="43f2d-129">операционная система и ее версия;</span><span class="sxs-lookup"><span data-stu-id="43f2d-129">Operating system and version</span></span>
- <span data-ttu-id="43f2d-130">значение параметра --ml-task: категориальные значения, такие как `regression`, `binary-classification` и `multiclass-classification`;</span><span class="sxs-lookup"><span data-stu-id="43f2d-130">Value of --ml-task parameter: Categorical values, such as `regression`, `binary-classification`, and `multiclass-classification`</span></span>
- <span data-ttu-id="43f2d-131">[логарифмический округленный](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) размер файла набора данных (ближайшая степень числа 2)</span><span class="sxs-lookup"><span data-stu-id="43f2d-131">[Logarithmic rounded](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) dataset file size (nearest power of 2)</span></span>
- <span data-ttu-id="43f2d-132">`ExitCode` команды;</span><span class="sxs-lookup"><span data-stu-id="43f2d-132">`ExitCode` of the command</span></span>

<span data-ttu-id="43f2d-133">Данные отправляются по защищенному протоколу на серверы Майкрософт с помощью технологии [Azure Application Insights](https://azure.microsoft.com/services/application-insights/), хранятся в режиме ограниченного доступа и используются в защищенных системах [хранилища Azure](https://azure.microsoft.com/services/storage/) с соблюдением строгих мер безопасности.</span><span class="sxs-lookup"><span data-stu-id="43f2d-133">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="43f2d-134">Не собираемые точки данных</span><span class="sxs-lookup"><span data-stu-id="43f2d-134">Data points not collected</span></span>
<span data-ttu-id="43f2d-135">Функция телеметрии *не* собирает:</span><span class="sxs-lookup"><span data-stu-id="43f2d-135">The telemetry feature *doesn't* collect:</span></span>
- <span data-ttu-id="43f2d-136">персональные данные, такие как имена пользователей;</span><span class="sxs-lookup"><span data-stu-id="43f2d-136">personal data, such as usernames</span></span>
- <span data-ttu-id="43f2d-137">имена файлов наборов данных;</span><span class="sxs-lookup"><span data-stu-id="43f2d-137">dataset filenames</span></span>
- <span data-ttu-id="43f2d-138">данные из файлов наборов данных.</span><span class="sxs-lookup"><span data-stu-id="43f2d-138">data from dataset files</span></span>

<span data-ttu-id="43f2d-139">Если есть подозрение, что функция телеметрии в интерфейсе командной строки ML.NET собирает конфиденциальные данные или данные не защищены или неправильно обрабатываются, сообщите об этом в репозиторий [ML.NET](https://github.com/dotnet/machinelearning) для расследования.</span><span class="sxs-lookup"><span data-stu-id="43f2d-139">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="43f2d-140">Лицензия</span><span class="sxs-lookup"><span data-stu-id="43f2d-140">License</span></span>

<span data-ttu-id="43f2d-141">Корпорация Майкрософт предоставляет интерфейс командной строки ML.NET по [Условиям лицензионного соглашения на использование программного обеспечения корпорации Майкрософт: библиотека Microsoft .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="43f2d-141">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="43f2d-142">Дополнительные сведения о сборе и обработке данных см. в разделе "Данные".</span><span class="sxs-lookup"><span data-stu-id="43f2d-142">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="43f2d-143">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="43f2d-143">Disclosure</span></span>

<span data-ttu-id="43f2d-144">При первом выполнении [команды интерфейса командной строки ML.NET](../reference/ml-net-cli-reference.md), такой как `mlnet auto-train`, интерфейс командной строки ML.NET отображает текстовое сообщение о том, как отказаться от телеметрии.</span><span class="sxs-lookup"><span data-stu-id="43f2d-144">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet auto-train`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="43f2d-145">Оно может немного отличаться в зависимости от используемой версии интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="43f2d-145">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="43f2d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="43f2d-146">See also</span></span>
- [<span data-ttu-id="43f2d-147">Справочник по интерфейсу командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="43f2d-147">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="43f2d-148">Условия лицензии на программное обеспечение Майкрософт: библиотека Microsoft .NET</span><span class="sxs-lookup"><span data-stu-id="43f2d-148">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- [<span data-ttu-id="43f2d-149">Конфиденциальность в корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="43f2d-149">Privacy at Microsoft</span></span>](https://www.microsoft.com/en-us/trustcenter/privacy/)
- [<span data-ttu-id="43f2d-150">Заявление о конфиденциальности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="43f2d-150">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/en-us/privacystatement)
