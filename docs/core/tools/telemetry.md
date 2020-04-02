---
title: Телеметрия пакета SDK для .NET Core
description: Сведения о функциях телеметрии пакета SDK для .NET Core, позволяющих собирать сведения об использовании для анализа, а также о собираемых данных и способе отключения этих функций.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: a79b791abc99331ff39f5e281ee0fdc62b258989
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507286"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="c34c6-103">Телеметрия пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="c34c6-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="c34c6-104">[Пакет SDK для .NET Core](index.md) включает функцию телеметрии, которая собирает данные об использовании и сведения об исключениях при сбоях .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="c34c6-104">The [.NET Core SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET Core CLI crashes.</span></span> <span data-ttu-id="c34c6-105">.NET Core CLI поставляется с пакетом SDK для .NET Core и представляет собой набор команд, позволяющих создавать, тестировать и публиковать приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c34c6-105">The .NET Core CLI comes with the .NET Core SDK and is the set of verbs that enable you to build, test, and publish your .NET Core apps.</span></span> <span data-ttu-id="c34c6-106">Команде разработчиков .NET важно знать, как используются эти средства, чтобы их можно было улучшить.</span><span class="sxs-lookup"><span data-stu-id="c34c6-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="c34c6-107">Сведения об ошибках помогают команде решать проблемы и устранять ошибки.</span><span class="sxs-lookup"><span data-stu-id="c34c6-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="c34c6-108">Данные собираются анонимно и публикуются в сводной форме по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="c34c6-108">The collected data is anonymous and published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="c34c6-109">Область</span><span class="sxs-lookup"><span data-stu-id="c34c6-109">Scope</span></span>

<span data-ttu-id="c34c6-110">`dotnet` имеет две функции: для запуска приложений и для выполнения команд CLI.</span><span class="sxs-lookup"><span data-stu-id="c34c6-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="c34c6-111">Данные телеметрии *не собираются* при использовании `dotnet` для запуска приложения в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="c34c6-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="c34c6-112">Данные телеметрии *собираются* при использовании [команд CLI .NET Core](index.md), например:</span><span class="sxs-lookup"><span data-stu-id="c34c6-112">Telemetry *is collected* when using any of the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="c34c6-113">Как отключить функцию</span><span class="sxs-lookup"><span data-stu-id="c34c6-113">How to opt out</span></span>

<span data-ttu-id="c34c6-114">Функция телеметрии пакета SDK для .NET Core по умолчанию включена.</span><span class="sxs-lookup"><span data-stu-id="c34c6-114">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="c34c6-115">Чтобы отключить ее, присвойте переменной среды `DOTNET_CLI_TELEMETRY_OPTOUT` значение `1` или `true`.</span><span class="sxs-lookup"><span data-stu-id="c34c6-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="c34c6-116">При успешной установке программа установки пакета SDK для .NET Core отправляет единую запись телеметрии.</span><span class="sxs-lookup"><span data-stu-id="c34c6-116">A single telemetry entry is also sent by the .NET Core SDK installer when a successful installation happens.</span></span> <span data-ttu-id="c34c6-117">Чтобы отказаться от этого, задайте переменную среды `DOTNET_CLI_TELEMETRY_OPTOUT` перед установкой пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c34c6-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET Core SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="c34c6-118">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="c34c6-118">Disclosure</span></span>

<span data-ttu-id="c34c6-119">При первом выполнении одной из [команд .NET Core CLI](index.md) (например, `dotnet build`) пакет SDK для .NET Core выводит следующий текст.</span><span class="sxs-lookup"><span data-stu-id="c34c6-119">The .NET Core SDK displays text similar to the following when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="c34c6-120">Он может немного отличаться в зависимости от используемой версии пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="c34c6-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="c34c6-121">Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных.</span><span class="sxs-lookup"><span data-stu-id="c34c6-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is anonymous. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

<span data-ttu-id="c34c6-122">Чтобы отключить отображение этого сообщения и приветственного сообщения .NET Core, задайте для переменной среды `DOTNET_NOLOGO` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="c34c6-122">To disable this message and the .NET Core welcome message, set the `DOTNET_NOLOGO` environment variable to `true`.</span></span> <span data-ttu-id="c34c6-123">Обратите внимание, что эта переменная не влияет на отказ от отправки данных телеметрии.</span><span class="sxs-lookup"><span data-stu-id="c34c6-123">Note that this variable has no effect on telemetry opt out.</span></span>

## <a name="data-points"></a><span data-ttu-id="c34c6-124">Точки данных</span><span class="sxs-lookup"><span data-stu-id="c34c6-124">Data points</span></span>

<span data-ttu-id="c34c6-125">Функция телеметрии не собирает персональные данные, например имена пользователей и их адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c34c6-125">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="c34c6-126">Она не проверяет код и не извлекает данные уровня проекта, например имя, репозиторий или автора.</span><span class="sxs-lookup"><span data-stu-id="c34c6-126">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="c34c6-127">Данные отправляются по защищенному протоколу на серверы Майкрософт с помощью технологии [Azure Monitor](https://azure.microsoft.com/services/monitor/), хранятся в режиме ограниченного доступа и используются в защищенных системах [хранилища Azure](https://azure.microsoft.com/services/storage/) с соблюдением строгих мер безопасности.</span><span class="sxs-lookup"><span data-stu-id="c34c6-127">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="c34c6-128">Мы заботимся о вашей конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="c34c6-128">Protecting your privacy is important to us.</span></span> <span data-ttu-id="c34c6-129">Если у вас есть подозрения, что функция телеметрии собирает конфиденциальные данные или что мы обрабатываем данные небезопасным либо неподобающим образом, отправьте сообщение о проблеме в репозитории [dotnet/cli](https://github.com/dotnet/cli/issues) или по адресу [dotnet@microsoft.com](mailto:dotnet@microsoft.com) для изучения.</span><span class="sxs-lookup"><span data-stu-id="c34c6-129">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="c34c6-130">Функция телеметрии собирает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="c34c6-130">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="c34c6-131">Версии пакета SDK</span><span class="sxs-lookup"><span data-stu-id="c34c6-131">SDK versions</span></span> | <span data-ttu-id="c34c6-132">Данные</span><span class="sxs-lookup"><span data-stu-id="c34c6-132">Data</span></span> |
|--------------|------|
| <span data-ttu-id="c34c6-133">Все</span><span class="sxs-lookup"><span data-stu-id="c34c6-133">All</span></span>          | <span data-ttu-id="c34c6-134">Метка времени вызова.</span><span class="sxs-lookup"><span data-stu-id="c34c6-134">Timestamp of invocation.</span></span> |
| <span data-ttu-id="c34c6-135">Все</span><span class="sxs-lookup"><span data-stu-id="c34c6-135">All</span></span>          | <span data-ttu-id="c34c6-136">Вызываемая команда (например, build), хэшируется с версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="c34c6-136">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="c34c6-137">Все</span><span class="sxs-lookup"><span data-stu-id="c34c6-137">All</span></span>          | <span data-ttu-id="c34c6-138">Состоящий из трех октетов IP-адрес, используемый для определения географического местоположения.</span><span class="sxs-lookup"><span data-stu-id="c34c6-138">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="c34c6-139">Все</span><span class="sxs-lookup"><span data-stu-id="c34c6-139">All</span></span>          | <span data-ttu-id="c34c6-140">Операционная система и ее версия.</span><span class="sxs-lookup"><span data-stu-id="c34c6-140">Operating system and version.</span></span> |
| <span data-ttu-id="c34c6-141">Все</span><span class="sxs-lookup"><span data-stu-id="c34c6-141">All</span></span>          | <span data-ttu-id="c34c6-142">Идентификатор среды выполнения (RID), в которой работает пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="c34c6-142">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="c34c6-143">Все</span><span class="sxs-lookup"><span data-stu-id="c34c6-143">All</span></span>          | <span data-ttu-id="c34c6-144">Версия пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c34c6-144">.NET Core SDK version.</span></span> |
| <span data-ttu-id="c34c6-145">Все</span><span class="sxs-lookup"><span data-stu-id="c34c6-145">All</span></span>          | <span data-ttu-id="c34c6-146">Профиль телеметрии: необязательное значение используется только при явном включении пользователем и внутри корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c34c6-146">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="c34c6-147">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="c34c6-147">>=2.0</span></span>        | <span data-ttu-id="c34c6-148">Аргументы и параметры команды: собираются только известные аргументы и параметры (но не произвольные строки).</span><span class="sxs-lookup"><span data-stu-id="c34c6-148">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="c34c6-149">См. раздел о [собираемых параметрах](#collected-options).</span><span class="sxs-lookup"><span data-stu-id="c34c6-149">See [collected options](#collected-options).</span></span> <span data-ttu-id="c34c6-150">Хэшируется после версии 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="c34c6-150">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="c34c6-151">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="c34c6-151">>=2.0</span></span>         | <span data-ttu-id="c34c6-152">выполняется ли пакет SDK в контейнере;</span><span class="sxs-lookup"><span data-stu-id="c34c6-152">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="c34c6-153">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="c34c6-153">>=2.0</span></span>         | <span data-ttu-id="c34c6-154">Целевые платформы (из события `TargetFramework`), хэшируются начиная с версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="c34c6-154">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="c34c6-155">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="c34c6-155">>=2.0</span></span>         | <span data-ttu-id="c34c6-156">Хэшированный MAC-адрес: криптографически (SHA256) анонимный и уникальный идентификатор компьютера.</span><span class="sxs-lookup"><span data-stu-id="c34c6-156">Hashed Media Access Control (MAC) address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> |
| <span data-ttu-id="c34c6-157">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="c34c6-157">>=2.0</span></span>         | <span data-ttu-id="c34c6-158">хэшированный текущий рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="c34c6-158">Hashed current working directory.</span></span> |
| <span data-ttu-id="c34c6-159">>= 2.0</span><span class="sxs-lookup"><span data-stu-id="c34c6-159">>=2.0</span></span>         | <span data-ttu-id="c34c6-160">Отчет об успешном выполнении установки с хэшированным именем EXE-файла установщика.</span><span class="sxs-lookup"><span data-stu-id="c34c6-160">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="c34c6-161">>= 2.1.300</span><span class="sxs-lookup"><span data-stu-id="c34c6-161">>=2.1.300</span></span>     | <span data-ttu-id="c34c6-162">Версия ядра.</span><span class="sxs-lookup"><span data-stu-id="c34c6-162">Kernel version.</span></span> |
| <span data-ttu-id="c34c6-163">>= 2.1.300</span><span class="sxs-lookup"><span data-stu-id="c34c6-163">>=2.1.300</span></span>     | <span data-ttu-id="c34c6-164">Выпуск или версия libc.</span><span class="sxs-lookup"><span data-stu-id="c34c6-164">Libc release/version.</span></span> |
| <span data-ttu-id="c34c6-165">>= 3.0.100</span><span class="sxs-lookup"><span data-stu-id="c34c6-165">>=3.0.100</span></span>     | <span data-ttu-id="c34c6-166">Были ли перенаправлены выходные данные (true или false).</span><span class="sxs-lookup"><span data-stu-id="c34c6-166">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="c34c6-167">>= 3.0.100</span><span class="sxs-lookup"><span data-stu-id="c34c6-167">>=3.0.100</span></span>     | <span data-ttu-id="c34c6-168">При сбое интерфейса командной строки или пакета SDK тип исключения и его трассировка стека (в отправляемую трассировку стека включается только код CLI или SDK).</span><span class="sxs-lookup"><span data-stu-id="c34c6-168">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="c34c6-169">Дополнительные сведения см. в разделе [Сбор данных телеметрии об исключениях при сбоях .NET Core CLI и SDK](#net-core-clisdk-crash-exception-telemetry-collected).</span><span class="sxs-lookup"><span data-stu-id="c34c6-169">For more information, see [.NET Core CLI/SDK crash exception telemetry collected](#net-core-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="c34c6-170">Собираемые параметры</span><span class="sxs-lookup"><span data-stu-id="c34c6-170">Collected options</span></span>

<span data-ttu-id="c34c6-171">Некоторые команды отправляют дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="c34c6-171">Certain commands send additional data.</span></span> <span data-ttu-id="c34c6-172">Подмножество команд отправляет первый аргумент:</span><span class="sxs-lookup"><span data-stu-id="c34c6-172">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="c34c6-173">Команда</span><span class="sxs-lookup"><span data-stu-id="c34c6-173">Command</span></span>               | <span data-ttu-id="c34c6-174">Данные первого аргумента отправлены</span><span class="sxs-lookup"><span data-stu-id="c34c6-174">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="c34c6-175">Запрашивается справка по командам.</span><span class="sxs-lookup"><span data-stu-id="c34c6-175">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="c34c6-176">Имя шаблона (хэшированное).</span><span class="sxs-lookup"><span data-stu-id="c34c6-176">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="c34c6-177">Слово `package` или `reference`.</span><span class="sxs-lookup"><span data-stu-id="c34c6-177">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="c34c6-178">Слово `package` или `reference`.</span><span class="sxs-lookup"><span data-stu-id="c34c6-178">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="c34c6-179">Слово `package` или `reference`.</span><span class="sxs-lookup"><span data-stu-id="c34c6-179">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="c34c6-180">Слово `add`, `list` или `remove`.</span><span class="sxs-lookup"><span data-stu-id="c34c6-180">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="c34c6-181">Слово `delete`, `locals` или `push`.</span><span class="sxs-lookup"><span data-stu-id="c34c6-181">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="c34c6-182">Подмножество команд отправляет выбранные параметры, если они используются, а также их значения:</span><span class="sxs-lookup"><span data-stu-id="c34c6-182">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="c34c6-183">Параметр</span><span class="sxs-lookup"><span data-stu-id="c34c6-183">Option</span></span>                  | <span data-ttu-id="c34c6-184">Команды</span><span class="sxs-lookup"><span data-stu-id="c34c6-184">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="c34c6-185">Все команды</span><span class="sxs-lookup"><span data-stu-id="c34c6-185">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="c34c6-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="c34c6-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="c34c6-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="c34c6-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="c34c6-188">`dotnet build`, `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="c34c6-188">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="c34c6-189">За исключением `--verbosity` и `--sdk-package-version` все остальные значения хэшируются, начиная с пакета SDK для .NET Core 2.1.100.</span><span class="sxs-lookup"><span data-stu-id="c34c6-189">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="c34c6-190">Сбор данных телеметрии об исключениях при сбоях .NET Core CLI и SDK</span><span class="sxs-lookup"><span data-stu-id="c34c6-190">.NET Core CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="c34c6-191">В случае сбоя .NET Core CLI или пакета SDK он собирает имя исключения и трассировку стека кода CLI/SDK.</span><span class="sxs-lookup"><span data-stu-id="c34c6-191">If the .NET Core CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="c34c6-192">Эти сведения собираются для оценки проблем и улучшения качества пакета SDK для .NET Core и интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="c34c6-192">This information is collected to assess problems and improve the quality of the .NET Core SDK and CLI.</span></span> <span data-ttu-id="c34c6-193">В этой статье приводятся сведения о данных, которые мы собираем.</span><span class="sxs-lookup"><span data-stu-id="c34c6-193">This article provides information about the data we collect.</span></span> <span data-ttu-id="c34c6-194">Кроме того, она содержит советы, помогающие пользователям, создающим собственную версию пакета SDK для .NET Core, избежать случайного раскрытия личных или конфиденциальных сведений.</span><span class="sxs-lookup"><span data-stu-id="c34c6-194">It also provides tips on how users building their own version of the .NET Core SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="c34c6-195">Типы собираемых данных</span><span class="sxs-lookup"><span data-stu-id="c34c6-195">Types of collected data</span></span>

<span data-ttu-id="c34c6-196">.NET Core CLI собирает сведения только об исключениях CLI/SDK, а не об исключениях в приложении.</span><span class="sxs-lookup"><span data-stu-id="c34c6-196">.NET Core CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="c34c6-197">Собранные данные содержат имя исключения и трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="c34c6-197">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="c34c6-198">Эта трассировка стека относится к коду CLI или пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="c34c6-198">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="c34c6-199">В следующем примере показан тип собираемых данных:</span><span class="sxs-lookup"><span data-stu-id="c34c6-199">The following example shows the kind of data that is collected:</span></span>

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="c34c6-200">Избегайте случайного разглашения информации</span><span class="sxs-lookup"><span data-stu-id="c34c6-200">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="c34c6-201">Участники .NET Core и все остальные, кто использует версию пакета SDK для .NET Core, которую они создали сами, должны учитывать путь к исходному коду пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="c34c6-201">.NET Core contributors and anyone else running a version of the .NET Core SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="c34c6-202">Если сбой происходит при использовании пакета SDK для .NET Core, который является пользовательской сборкой отладки или настроен с помощью файлов пользовательских символов сборки, путь к исходному файлу пакета SDK с компьютера сборки собирается как часть трассировки стека и не хэшируется.</span><span class="sxs-lookup"><span data-stu-id="c34c6-202">If a crash occurs while using a .NET Core SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="c34c6-203">По этой причине пользовательские сборки пакета SDK для .NET Core не должны размещаться в каталогах, имена путей которых раскрывают персональные или конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="c34c6-203">Because of this, custom builds of the .NET Core SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="c34c6-204">См. также</span><span class="sxs-lookup"><span data-stu-id="c34c6-204">See also</span></span>

- [<span data-ttu-id="c34c6-205">Телеметрия .NET Core CLI, данные за 2 кв 2019 г.</span><span class="sxs-lookup"><span data-stu-id="c34c6-205">.NET Core CLI Telemetry - 2019 Q2 Data</span></span>](https://dotnet.microsoft.com/platform/telemetry/dotnet-core-cli-2019q2)
- [<span data-ttu-id="c34c6-206">Справочные материалы по телеметрии (репозиторий dotnet/cli)</span><span class="sxs-lookup"><span data-stu-id="c34c6-206">Telemetry reference source (dotnet/cli repository)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
