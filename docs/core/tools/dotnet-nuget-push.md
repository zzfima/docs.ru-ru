---
title: Команда dotnet nuget push — CLI .NET Core
description: Команда dotnet nuget push отправляет пакет на сервер и публикует его.
author: karann-msft
ms.author: mairaw
ms.date: 09/04/2018
ms.openlocfilehash: 23d27cef29008955850f9ed9f4a8baed9e7ad982
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45610013"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="349be-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="349be-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="349be-104">name</span><span class="sxs-lookup"><span data-stu-id="349be-104">Name</span></span>

<span data-ttu-id="349be-105">`dotnet nuget push` — отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="349be-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="349be-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="349be-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="349be-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="349be-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="349be-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="349be-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="349be-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="349be-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="349be-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="349be-110">Description</span></span>

<span data-ttu-id="349be-111">Команда `dotnet nuget push` отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="349be-111">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="349be-112">Команда push использует сервер и учетные данные, указанные в системном файле конфигурации NuGet или цепочке файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="349be-112">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="349be-113">См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="349be-113">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="349be-114">Конфигурацию NuGet по умолчанию можно получить, загрузив файл *%AppData%\NuGet\NuGet.config* (Windows) или *$HOME/.local/share* (Linux и macOS). Затем нужно загрузить все файлы *nuget.config* или *.nuget\nuget.config*, начиная с корневого каталога диска и заканчивая текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="349be-114">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="349be-115">Аргументы</span><span class="sxs-lookup"><span data-stu-id="349be-115">Arguments</span></span>

`ROOT`

<span data-ttu-id="349be-116">Указывает путь к файлу пакета для отправки.</span><span class="sxs-lookup"><span data-stu-id="349be-116">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="349be-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="349be-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="349be-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="349be-118">.NET Core 2.1</span></span>](#tab/netcore21)

`-d|--disable-buffering`

<span data-ttu-id="349be-119">Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="349be-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="349be-120">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="349be-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="349be-121">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="349be-121">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="349be-122">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="349be-122">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="349be-123">Не передает символы (даже если они присутствуют).</span><span class="sxs-lookup"><span data-stu-id="349be-123">Doesn't push symbols (even if present).</span></span>

`--no-service-endpoint`

<span data-ttu-id="349be-124">Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="349be-124">Doesn't append "api/v2/package" to the source URL.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="349be-125">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="349be-125">Specifies the server URL.</span></span> <span data-ttu-id="349be-126">Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="349be-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="349be-127">Ключ API для сервера символов.</span><span class="sxs-lookup"><span data-stu-id="349be-127">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="349be-128">Указывает URL-адрес сервера символов.</span><span class="sxs-lookup"><span data-stu-id="349be-128">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="349be-129">Указывает время ожидания для передачи на сервер в секундах.</span><span class="sxs-lookup"><span data-stu-id="349be-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="349be-130">Значение по умолчанию — 300 секунд (5 минут).</span><span class="sxs-lookup"><span data-stu-id="349be-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="349be-131">При указании 0 (ноль секунд) применяется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="349be-131">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="349be-132">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="349be-132">.NET Core 2.0</span></span>](#tab/netcore20)

`-d|--disable-buffering`

<span data-ttu-id="349be-133">Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="349be-133">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="349be-134">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="349be-134">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="349be-135">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="349be-135">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="349be-136">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="349be-136">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="349be-137">Не передает символы (даже если они присутствуют).</span><span class="sxs-lookup"><span data-stu-id="349be-137">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="349be-138">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="349be-138">Specifies the server URL.</span></span> <span data-ttu-id="349be-139">Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="349be-139">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="349be-140">Ключ API для сервера символов.</span><span class="sxs-lookup"><span data-stu-id="349be-140">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="349be-141">Указывает URL-адрес сервера символов.</span><span class="sxs-lookup"><span data-stu-id="349be-141">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="349be-142">Указывает время ожидания для передачи на сервер в секундах.</span><span class="sxs-lookup"><span data-stu-id="349be-142">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="349be-143">Значение по умолчанию — 300 секунд (5 минут).</span><span class="sxs-lookup"><span data-stu-id="349be-143">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="349be-144">При указании 0 (ноль секунд) применяется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="349be-144">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="349be-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="349be-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`-d|--disable-buffering`

<span data-ttu-id="349be-146">Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="349be-146">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="349be-147">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="349be-147">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="349be-148">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="349be-148">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="349be-149">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="349be-149">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="349be-150">Не передает символы (даже если они присутствуют).</span><span class="sxs-lookup"><span data-stu-id="349be-150">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="349be-151">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="349be-151">Specifies the server URL.</span></span> <span data-ttu-id="349be-152">Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="349be-152">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="349be-153">Ключ API для сервера символов.</span><span class="sxs-lookup"><span data-stu-id="349be-153">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="349be-154">Указывает URL-адрес сервера символов.</span><span class="sxs-lookup"><span data-stu-id="349be-154">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="349be-155">Указывает время ожидания для передачи на сервер в секундах.</span><span class="sxs-lookup"><span data-stu-id="349be-155">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="349be-156">Значение по умолчанию — 300 секунд (5 минут).</span><span class="sxs-lookup"><span data-stu-id="349be-156">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="349be-157">При указании 0 (ноль секунд) применяется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="349be-157">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="349be-158">Примеры</span><span class="sxs-lookup"><span data-stu-id="349be-158">Examples</span></span>

<span data-ttu-id="349be-159">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="349be-159">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="349be-160">Отправляет *foo.nupkg* в пользовательский источник push-уведомлений `http://customsource`, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="349be-160">Push *foo.nupkg* to the custom push source `http://customsource`, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="349be-161">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="349be-161">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="349be-162">Отправляет *foo.symbols.nupkg* в источник символов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="349be-162">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="349be-163">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, указав время ожидания 360 секунд:</span><span class="sxs-lookup"><span data-stu-id="349be-163">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="349be-164">Отправляет все файлы *NUPKG* из текущего каталога в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="349be-164">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`
