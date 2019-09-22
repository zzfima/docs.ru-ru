---
title: Команда dotnet nuget push
description: Команда dotnet nuget push отправляет пакет на сервер и публикует его.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 3299f79ec62aebdcdbef38f1e8b09a2dc5529ec4
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117491"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="f70ee-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="f70ee-103">dotnet nuget push</span></span>

<span data-ttu-id="f70ee-104">**Этот раздел относится к: ✓** пакету SDK для .NET Core 1.x и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="f70ee-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="f70ee-105">name</span><span class="sxs-lookup"><span data-stu-id="f70ee-105">Name</span></span>

<span data-ttu-id="f70ee-106">`dotnet nuget push` — отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="f70ee-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f70ee-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f70ee-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a><span data-ttu-id="f70ee-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f70ee-108">Description</span></span>

<span data-ttu-id="f70ee-109">Команда `dotnet nuget push` отправляет пакет на сервер и публикует его.</span><span class="sxs-lookup"><span data-stu-id="f70ee-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="f70ee-110">Команда push использует сервер и учетные данные, указанные в системном файле конфигурации NuGet или цепочке файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f70ee-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="f70ee-111">См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="f70ee-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="f70ee-112">Конфигурацию NuGet по умолчанию можно получить, загрузив файл *%AppData%\NuGet\NuGet.config* (Windows) или *$HOME/.local/share* (Linux и macOS). Затем нужно загрузить все файлы *nuget.config* или *.nuget\nuget.config*, начиная с корневого каталога диска и заканчивая текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="f70ee-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="f70ee-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f70ee-113">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="f70ee-114">Указывает путь к файлу пакета для отправки.</span><span class="sxs-lookup"><span data-stu-id="f70ee-114">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="f70ee-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="f70ee-115">Options</span></span>

* **`-d|--disable-buffering`**

  <span data-ttu-id="f70ee-116">Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="f70ee-116">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="f70ee-117">Принудительно запускает приложение с использованием инвариантного английского языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="f70ee-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="f70ee-118">Выводит краткую справку по команде.</span><span class="sxs-lookup"><span data-stu-id="f70ee-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="f70ee-119">Позволяет блокировать команду до выполнения действия пользователем, например аутентификации.</span><span class="sxs-lookup"><span data-stu-id="f70ee-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="f70ee-120">Параметр доступен, начиная с пакета SDK для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f70ee-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="f70ee-121">Ключ API для сервера.</span><span class="sxs-lookup"><span data-stu-id="f70ee-121">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="f70ee-122">Не передает символы (даже если они присутствуют).</span><span class="sxs-lookup"><span data-stu-id="f70ee-122">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="f70ee-123">Не добавляет "api/v2/package" в исходный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f70ee-123">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="f70ee-124">Параметр доступен, начиная с пакета SDK для .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="f70ee-124">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="f70ee-125">Определяет URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="f70ee-125">Specifies the server URL.</span></span> <span data-ttu-id="f70ee-126">Этот параметр является обязательным, если значение параметра конфигурации `DefaultPushSource` задано в файле конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="f70ee-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="f70ee-127">Ключ API для сервера символов.</span><span class="sxs-lookup"><span data-stu-id="f70ee-127">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="f70ee-128">Указывает URL-адрес сервера символов.</span><span class="sxs-lookup"><span data-stu-id="f70ee-128">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="f70ee-129">Указывает время ожидания для передачи на сервер в секундах.</span><span class="sxs-lookup"><span data-stu-id="f70ee-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="f70ee-130">Значение по умолчанию — 300 секунд (5 минут).</span><span class="sxs-lookup"><span data-stu-id="f70ee-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="f70ee-131">При указании 0 (ноль секунд) применяется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f70ee-131">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="f70ee-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="f70ee-132">Examples</span></span>

* <span data-ttu-id="f70ee-133">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="f70ee-133">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="f70ee-134">Отправляет *foo.nupkg* в пользовательский источник push-уведомлений `https://customsource`, предоставляя ключ API:</span><span class="sxs-lookup"><span data-stu-id="f70ee-134">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="f70ee-135">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f70ee-135">Pushes *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="f70ee-136">Отправляет *foo.symbols.nupkg* в источник символов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f70ee-136">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="f70ee-137">Отправляет *foo.nupkg* в источник push-уведомлений по умолчанию, указав время ожидания 360 секунд:</span><span class="sxs-lookup"><span data-stu-id="f70ee-137">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="f70ee-138">Отправляет все файлы *NUPKG* из текущего каталога в источник push-уведомлений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f70ee-138">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```
  
  > [!NOTE]
  > <span data-ttu-id="f70ee-139">Если эта команда не работает, возможно, это связано с ошибкой, которая существовала в более старых версиях пакета SDK (пакет SDK для .NET Core 2.1 и более ранних версий).</span><span class="sxs-lookup"><span data-stu-id="f70ee-139">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="f70ee-140">Чтобы устранить эту проблему, обновите версию пакета SDK или выполните следующую команду: `dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="f70ee-140">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>
