---
title: Команда dotnet nuget add source
description: Команда dotnet nuget add source добавляет новый источник пакета в файлы конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: c1e398699c7482a69b750cde718e6f9178b5c4bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148492"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="d4723-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="d4723-103">dotnet nuget add source</span></span>

<span data-ttu-id="d4723-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="d4723-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d4723-105">name</span><span class="sxs-lookup"><span data-stu-id="d4723-105">Name</span></span>

<span data-ttu-id="d4723-106">`dotnet nuget add source` — добавляет источник NuGet.</span><span class="sxs-lookup"><span data-stu-id="d4723-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d4723-107">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d4723-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget add source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="d4723-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d4723-108">Description</span></span>

<span data-ttu-id="d4723-109">Команда `dotnet nuget add source` добавляет новый источник пакета в файлы конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="d4723-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="d4723-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d4723-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="d4723-111">Путь к источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="d4723-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="d4723-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4723-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="d4723-113">Файл конфигурации NuGet.</span><span class="sxs-lookup"><span data-stu-id="d4723-113">The NuGet configuration file.</span></span> <span data-ttu-id="d4723-114">Если этот параметр указан, будут использоваться только параметры из этого файла.</span><span class="sxs-lookup"><span data-stu-id="d4723-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="d4723-115">Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="d4723-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="d4723-116">Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="d4723-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name`**

  <span data-ttu-id="d4723-117">Имя источника.</span><span class="sxs-lookup"><span data-stu-id="d4723-117">Name of the source.</span></span>

- **`-p|--password`**

  <span data-ttu-id="d4723-118">Пароль, используемый при подключении к источнику, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d4723-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="d4723-119">Включает сохранение учетных данных переносимого источника пакетов путем отключения шифрования паролей.</span><span class="sxs-lookup"><span data-stu-id="d4723-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="d4723-120">Имя пользователя, используемое при подключении к источнику, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d4723-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="d4723-121">Разделенный запятыми список допустимых типов проверки подлинности для этого источника.</span><span class="sxs-lookup"><span data-stu-id="d4723-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="d4723-122">Задайте значение `basic`, если сервер объявляет NTLM или Negotiate. Ваши учетные данные следует отправлять с помощью базового механизма, например, при использовании PAT с локальным Azure DevOps Server.</span><span class="sxs-lookup"><span data-stu-id="d4723-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="d4723-123">К другим допустимым значениям относятся `negotiate`, `kerberos`, `ntlm` и `digest`, но они вряд ли будут полезны.</span><span class="sxs-lookup"><span data-stu-id="d4723-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="d4723-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="d4723-124">Examples</span></span>

- <span data-ttu-id="d4723-125">Добавьте `nuget.org` в качестве источника:</span><span class="sxs-lookup"><span data-stu-id="d4723-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="d4723-126">Добавьте `c:\packages` в качестве локального источника:</span><span class="sxs-lookup"><span data-stu-id="d4723-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="d4723-127">Добавьте источник, требующий проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="d4723-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="d4723-128">Добавьте источник, требующий проверки подлинности (затем установите поставщик учетных данных):</span><span class="sxs-lookup"><span data-stu-id="d4723-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="d4723-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d4723-129">See also</span></span>

- [<span data-ttu-id="d4723-130">Разделы источников пакетов в файлах NuGet.config</span><span class="sxs-lookup"><span data-stu-id="d4723-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="d4723-131">Команда sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="d4723-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
