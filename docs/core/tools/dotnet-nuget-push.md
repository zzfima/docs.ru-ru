---
title: Команда dotnet nuget push — CLI .NET Core
description: Команда dotnet nuget push отправляет пакет на сервер и публикует его.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 090dbfbe3db83b2bb234867aed295ac416b27865
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143065"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="61cf0-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="61cf0-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="61cf0-104">name</span><span class="sxs-lookup"><span data-stu-id="61cf0-104">Name</span></span>

<span data-ttu-id="61cf0-105">`dotnet nuget push` — отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="61cf0-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="61cf0-106">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="61cf0-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="61cf0-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="61cf0-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="61cf0-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="61cf0-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="61cf0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="61cf0-109">Description</span></span>

<span data-ttu-id="61cf0-110">Команда `dotnet nuget push` отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="61cf0-110">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="61cf0-111">Команда push использует сервер и учетные данные, указанные в системном файле конфигурации NuGet или цепочке файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="61cf0-111">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="61cf0-112">См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="61cf0-112">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="61cf0-113">Конфигурацию NuGet по умолчанию можно получить, загрузив файл *%AppData%\NuGet\NuGet.config* (Windows) или *$HOME/.local/share* (Linux и macOS). Затем нужно загрузить все файлы *nuget.config* или *.nuget\nuget.config*, начиная с корневого каталога диска и заканчивая текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="61cf0-113">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="61cf0-114">Аргументы</span><span class="sxs-lookup"><span data-stu-id="61cf0-114">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="61cf0-115">Указывает путь к файлу пакета для отправки.</span><span class="sxs-lookup"><span data-stu-id="61cf0-115">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="61cf0-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="61cf0-116">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="61cf0-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="61cf0-117">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="61cf0-118">Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="61cf0-118">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="61cf0-119">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="61cf0-119">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="61cf0-120">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="61cf0-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="61cf0-121">Позволяет блокировать команду до выполнения действия пользователем, например аутентификации.</span><span class="sxs-lookup"><span data-stu-id="61cf0-121">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="61cf0-122">Параметр доступен, начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="61cf0-122">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="61cf0-123">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="61cf0-123">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="61cf0-124">Не передает символы (даже если они присутствуют).</span><span class="sxs-lookup"><span data-stu-id="61cf0-124">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="61cf0-125">Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="61cf0-125">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="61cf0-126">Параметр доступен, начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="61cf0-126">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="61cf0-127">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="61cf0-127">Specifies the server URL.</span></span> <span data-ttu-id="61cf0-128">Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="61cf0-128">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="61cf0-129">Ключ API для сервера символов.</span><span class="sxs-lookup"><span data-stu-id="61cf0-129">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="61cf0-130">Указывает URL-адрес сервера символов.</span><span class="sxs-lookup"><span data-stu-id="61cf0-130">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="61cf0-131">Указывает время ожидания для передачи на сервер в секундах.</span><span class="sxs-lookup"><span data-stu-id="61cf0-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="61cf0-132">Значение по умолчанию — 300 секунд (5 минут).</span><span class="sxs-lookup"><span data-stu-id="61cf0-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="61cf0-133">При указании 0 (ноль секунд) применяется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61cf0-133">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="61cf0-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="61cf0-134">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="61cf0-135">Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="61cf0-135">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="61cf0-136">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="61cf0-136">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="61cf0-137">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="61cf0-137">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="61cf0-138">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="61cf0-138">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="61cf0-139">Не передает символы (даже если они присутствуют).</span><span class="sxs-lookup"><span data-stu-id="61cf0-139">Doesn't push symbols (even if present).</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="61cf0-140">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="61cf0-140">Specifies the server URL.</span></span> <span data-ttu-id="61cf0-141">Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="61cf0-141">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="61cf0-142">Ключ API для сервера символов.</span><span class="sxs-lookup"><span data-stu-id="61cf0-142">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="61cf0-143">Указывает URL-адрес сервера символов.</span><span class="sxs-lookup"><span data-stu-id="61cf0-143">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="61cf0-144">Указывает время ожидания для передачи на сервер в секундах.</span><span class="sxs-lookup"><span data-stu-id="61cf0-144">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="61cf0-145">Значение по умолчанию — 300 секунд (5 минут).</span><span class="sxs-lookup"><span data-stu-id="61cf0-145">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="61cf0-146">При указании 0 (ноль секунд) применяется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61cf0-146">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="61cf0-147">Примеры</span><span class="sxs-lookup"><span data-stu-id="61cf0-147">Examples</span></span>

* <span data-ttu-id="61cf0-148">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="61cf0-148">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="61cf0-149">Отправляет *foo.nupkg* в пользовательский источник push-уведомлений `https://customsource`, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="61cf0-149">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="61cf0-150">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61cf0-150">Pushes *foo.nupkg* to the default push source:</span></span>

  ```console
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="61cf0-151">Отправляет *foo.symbols.nupkg* в источник символов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61cf0-151">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="61cf0-152">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, указав время ожидания 360 секунд:</span><span class="sxs-lookup"><span data-stu-id="61cf0-152">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="61cf0-153">Отправляет все файлы *NUPKG* из текущего каталога в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61cf0-153">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```console
  dotnet nuget push *.nupkg
  ```