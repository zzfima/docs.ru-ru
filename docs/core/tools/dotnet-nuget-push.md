---
title: Команда dotnet nuget push
description: Команда dotnet nuget push отправляет пакет на сервер и публикует его.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: d4ef8e58908fe488c712debff3b313ac0908b43e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503656"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="ea53d-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="ea53d-103">dotnet nuget push</span></span>

<span data-ttu-id="ea53d-104">**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="ea53d-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ea53d-105">Имя</span><span class="sxs-lookup"><span data-stu-id="ea53d-105">Name</span></span>

<span data-ttu-id="ea53d-106">`dotnet nuget push` — отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="ea53d-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ea53d-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ea53d-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [--skip-duplicate] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a><span data-ttu-id="ea53d-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="ea53d-108">Description</span></span>

<span data-ttu-id="ea53d-109">Команда `dotnet nuget push` отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="ea53d-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="ea53d-110">Команда push использует сервер и учетные данные, указанные в системном файле конфигурации NuGet или цепочке файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ea53d-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="ea53d-111">См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="ea53d-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="ea53d-112">Конфигурацию NuGet по умолчанию можно получить, загрузив файл *%AppData%\NuGet\NuGet.config* (Windows) или *$HOME/.local/share* (Linux и macOS). Затем нужно загрузить все файлы *nuget.config* или *.nuget\nuget.config*, начиная с корневого каталога диска и заканчивая текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="ea53d-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="ea53d-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ea53d-113">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="ea53d-114">Указывает путь к файлу пакета для отправки.</span><span class="sxs-lookup"><span data-stu-id="ea53d-114">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="ea53d-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea53d-115">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="ea53d-116">Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="ea53d-116">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="ea53d-117">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ea53d-117">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ea53d-118">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="ea53d-118">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="ea53d-119">Позволяет блокировать команду до выполнения действия пользователем, например аутентификации.</span><span class="sxs-lookup"><span data-stu-id="ea53d-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="ea53d-120">Параметр доступен, начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="ea53d-120">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="ea53d-121">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="ea53d-121">The API key for the server.</span></span>

- **`-n|--no-symbols`**

  <span data-ttu-id="ea53d-122">Не передает символы (даже если они присутствуют).</span><span class="sxs-lookup"><span data-stu-id="ea53d-122">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="ea53d-123">Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="ea53d-123">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="ea53d-124">Параметр доступен, начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="ea53d-124">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="ea53d-125">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="ea53d-125">Specifies the server URL.</span></span> <span data-ttu-id="ea53d-126">Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="ea53d-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="ea53d-127">При принудительной отправке нескольких пакетов на сервер HTTP(S) обрабатывает любой ответ с кодом состояния 409 Conflict (конфликт) в виде предупреждения, чтобы можно было продолжить принудительную отправку.</span><span class="sxs-lookup"><span data-stu-id="ea53d-127">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="ea53d-128">Доступно, начиная с пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="ea53d-128">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="ea53d-129">Ключ API для сервера символов.</span><span class="sxs-lookup"><span data-stu-id="ea53d-129">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="ea53d-130">Указывает URL-адрес сервера символов.</span><span class="sxs-lookup"><span data-stu-id="ea53d-130">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="ea53d-131">Указывает время ожидания для передачи на сервер в секундах.</span><span class="sxs-lookup"><span data-stu-id="ea53d-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="ea53d-132">Значение по умолчанию — 300 секунд (5 минут).</span><span class="sxs-lookup"><span data-stu-id="ea53d-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="ea53d-133">При указании 0 (ноль секунд) применяется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea53d-133">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="ea53d-134">Примеры</span><span class="sxs-lookup"><span data-stu-id="ea53d-134">Examples</span></span>

- <span data-ttu-id="ea53d-135">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="ea53d-135">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="ea53d-136">Отправляет *foo.nupkg* на официальный сервер NuGet, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="ea53d-136">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="ea53d-137">Отправляет *foo.nupkg* в пользовательский источник push-уведомлений `https://customsource`, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="ea53d-137">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="ea53d-138">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea53d-138">Pushes *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="ea53d-139">Отправляет *foo.symbols.nupkg* в источник символов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea53d-139">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="ea53d-140">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, указав время ожидания 360 секунд:</span><span class="sxs-lookup"><span data-stu-id="ea53d-140">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="ea53d-141">Отправляет все файлы *NUPKG* из текущего каталога в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea53d-141">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="ea53d-142">Если эта команда не работает, возможно, это связано с ошибкой, которая существовала в более старых версиях пакета SDK (пакет SDK для .NET Core 2.1 и более ранних версий).</span><span class="sxs-lookup"><span data-stu-id="ea53d-142">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="ea53d-143">Чтобы устранить эту проблему, обновите версию пакета SDK или выполните следующую команду: `dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="ea53d-143">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

- <span data-ttu-id="ea53d-144">Принудительно отправляет все файлы *.nupkg*, даже если сервер HTTP(S) возвращает код состояния 409 Conflict (конфликт):</span><span class="sxs-lookup"><span data-stu-id="ea53d-144">Pushes all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```
