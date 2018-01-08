---
title: "Команда dotnet nuget push — CLI .NET Core"
description: "Команда dotnet nuget push отправляет пакет на сервер и публикует его."
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 52aac5ff1862397616287a77eac063582703d509
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="6209d-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="6209d-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6209d-104">name</span><span class="sxs-lookup"><span data-stu-id="6209d-104">Name</span></span>

<span data-ttu-id="6209d-105">`dotnet nuget push` — отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="6209d-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6209d-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6209d-106">Synopsis</span></span>

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="6209d-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="6209d-107">Description</span></span>

<span data-ttu-id="6209d-108">Команда `dotnet nuget push` отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="6209d-108">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="6209d-109">Команда push использует сервер и учетные данные, указанные в системном файле конфигурации NuGet или цепочке файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6209d-109">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="6209d-110">См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="6209d-110">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="6209d-111">Конфигурацию NuGet по умолчанию можно получить, загрузив файл *%AppData%\NuGet\NuGet.config* (Windows) или *$HOME/.local/share* (Linux и macOS). Затем нужно загрузить все файлы *nuget.config* или *.nuget\nuget.config*, начиная с корневого каталога диска и заканчивая текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="6209d-111">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="6209d-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6209d-112">Arguments</span></span>

`ROOT`

<span data-ttu-id="6209d-113">Укажите путь к пакету и ключ API для отправки пакета на сервер.</span><span class="sxs-lookup"><span data-stu-id="6209d-113">Specify the path to the package and your API key to push the package to the server.</span></span>

## <a name="options"></a><span data-ttu-id="6209d-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="6209d-114">Options</span></span>

`-h|--help`

<span data-ttu-id="6209d-115">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="6209d-115">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="6209d-116">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="6209d-116">Specifies the server URL.</span></span> <span data-ttu-id="6209d-117">Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="6209d-117">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`--symbol-source <SOURCE>`

<span data-ttu-id="6209d-118">Указывает URL-адрес сервера символов.</span><span class="sxs-lookup"><span data-stu-id="6209d-118">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="6209d-119">Указывает время ожидания для передачи на сервер в секундах.</span><span class="sxs-lookup"><span data-stu-id="6209d-119">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="6209d-120">Значение по умолчанию — 300 секунд (5 минут).</span><span class="sxs-lookup"><span data-stu-id="6209d-120">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="6209d-121">При указании 0 (ноль секунд) применяется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6209d-121">Specifying 0 (zero seconds) applies the default value.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="6209d-122">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="6209d-122">The API key for the server.</span></span>

`--symbol-api-key <API_KEY>`

<span data-ttu-id="6209d-123">Ключ API для сервера символов.</span><span class="sxs-lookup"><span data-stu-id="6209d-123">The API key for the symbol server.</span></span>

`-d|--disable-buffering`

<span data-ttu-id="6209d-124">Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="6209d-124">Disables buffering when pushing to an HTTP(S) server to decrease memory usage.</span></span>

`-n|--no-symbols`

<span data-ttu-id="6209d-125">Не передает символы (даже если они присутствуют).</span><span class="sxs-lookup"><span data-stu-id="6209d-125">Doesn't push symbols (even if present).</span></span>

`--force-english-output`

<span data-ttu-id="6209d-126">Принудительно отображает все зарегистрированные выходные данные на английском языке.</span><span class="sxs-lookup"><span data-stu-id="6209d-126">Forces all logged output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="6209d-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="6209d-127">Examples</span></span>

<span data-ttu-id="6209d-128">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, предоставляя ключ API.</span><span class="sxs-lookup"><span data-stu-id="6209d-128">Pushes *foo.nupkg* to the default push source, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="6209d-129">Отправляет *foo.nupkg* в пользовательский источник push-уведомлений `http://customsource`, предоставляя ключ API.</span><span class="sxs-lookup"><span data-stu-id="6209d-129">Push *foo.nupkg* to the custom push source `http://customsource`, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="6209d-130">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6209d-130">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="6209d-131">Отправляет *foo.symbols.nupkg* в источник символов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6209d-131">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="6209d-132">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, указав время ожидания 360 секунд.</span><span class="sxs-lookup"><span data-stu-id="6209d-132">Pushes *foo.nupkg* to the default push source, specifying a 360 second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="6209d-133">Отправляет все файлы *NUPKG* из текущего каталога в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6209d-133">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="6209d-134">Отправляет все файлы *NUPKG* из текущего каталога в источник push-уведомлений по умолчанию, указав собственный файл конфигурации *./config/My.Config*.</span><span class="sxs-lookup"><span data-stu-id="6209d-134">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`
