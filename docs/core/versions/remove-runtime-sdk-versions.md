---
title: Удаление среды выполнения .NET Core и пакета SDK
description: В этой статье объясняется, как определить установленные в текущее время версии среды выполнения .NET Core и пакета SDK и как затем удалить их в Windows, Mac и Linux.
ms.date: 12/17/2019
author: billwagner
ms.author: wiwagn
ms.custom: updateeachrelease
ms.openlocfilehash: 82fbccdec0323b54d313960279fcbfeeb6033319
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920403"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="b6ef9-103">Как удалить среду выполнения .NET Core и пакет SDK</span><span class="sxs-lookup"><span data-stu-id="b6ef9-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="b6ef9-104">По мере установки обновленных версий среды выполнения и пакета SDK .NET Core может потребоваться удалить устаревшие версии .NET Core с вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="b6ef9-105">При удалении более ранних версий среды выполнения может измениться среда выполнения, выбранная для запуска приложений общей платформы, как описано в статье [Выбор версии .NET Core](selection.md).</span><span class="sxs-lookup"><span data-stu-id="b6ef9-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="b6ef9-106">Нужно ли удалять версию</span><span class="sxs-lookup"><span data-stu-id="b6ef9-106">Should I remove a version?</span></span>

<span data-ttu-id="b6ef9-107">[Выбор версии .NET Core](selection.md) и совместимость среды выполнения .NET Core для различных обновлений обеспечивает безопасное удаление предыдущих версий.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-107">The [.NET Core version selection](selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="b6ef9-108">Обновления среды выполнения .NET Core совместимы в пределах основной версии, например 1.x или 2.x.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="b6ef9-109">Кроме того, более поздние выпуски пакета SDK для .NET Core обычно позволяют создавать приложения, совместимые с предыдущими версиями среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="b6ef9-110">Как правило, требуется только последняя версия пакета SDK и последняя версия исправлений для сред выполнения, необходимых для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="b6ef9-111">Примеры хранения старых пакетов SDK или версий среды выполнения включают в себя поддержку **project.json** на базе приложений.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-111">Instances where keeping older SDK or Runtime versions include maintaining **project.json**-based applications.</span></span> <span data-ttu-id="b6ef9-112">Если у приложения нет конкретных причин, по которым оно должно использовать ранние версии пакета SDK или среды выполнения, вы можете безопасно удалить старые версии.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="b6ef9-113">Определите компоненты, которые нужно установить</span><span class="sxs-lookup"><span data-stu-id="b6ef9-113">Determine what is installed</span></span>

<span data-ttu-id="b6ef9-114">Начиная с .NET Core 2.1 можно определить версии пакета SDK и среды выполнения, установленных на вашем компьютере, с помощью команд в .NET CLI.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="b6ef9-115">Чтобы просмотреть список пакетов SDK, установленных на вашем компьютере, выполните команду [`dotnet --list-sdks`](../tools/dotnet.md#options).</span><span class="sxs-lookup"><span data-stu-id="b6ef9-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="b6ef9-116">Чтобы просмотреть список сред выполнения, установленных на вашем компьютере, выполните команду [`dotnet --list-runtimes`](../tools/dotnet.md#options).</span><span class="sxs-lookup"><span data-stu-id="b6ef9-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="b6ef9-117">Ниже приведены типичные выходные данные для Windows, macOS и Linux:</span><span class="sxs-lookup"><span data-stu-id="b6ef9-117">The following text shows typical output for Windows, macOS, or Linux:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="b6ef9-118">Windows</span><span class="sxs-lookup"><span data-stu-id="b6ef9-118">Windows</span></span>](#tab/windows)

```console
C:\> dotnet --list-sdks
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]

C:\> dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linuxtablinux"></a>[<span data-ttu-id="b6ef9-119">Linux</span><span class="sxs-lookup"><span data-stu-id="b6ef9-119">Linux</span></span>](#tab/linux)

```console
$ dotnet --list-sdks
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macostabmacos"></a>[<span data-ttu-id="b6ef9-120">macOS</span><span class="sxs-lookup"><span data-stu-id="b6ef9-120">macOS</span></span>](#tab/macos)

```console
$ dotnet --list-sdks
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]

$ dotnet --list-runtimes
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

---

## <a name="uninstall-net-core"></a><span data-ttu-id="b6ef9-121">Удаление .NET Core</span><span class="sxs-lookup"><span data-stu-id="b6ef9-121">Uninstall .NET Core</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="b6ef9-122">Windows</span><span class="sxs-lookup"><span data-stu-id="b6ef9-122">Windows</span></span>](#tab/windows)

<span data-ttu-id="b6ef9-123">Для удаления версий среды выполнения и пакета SDK .NET Core используется диалоговое окно **Установка и удаление программ** Windows.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-123">.NET Core uses the Windows **Add/Remove Programs** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="b6ef9-124">На следующем рисунке показано диалоговое окно **Установка и удаление программ** с несколькими установленными версиями среды выполнения и пакета SDK .NET.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-124">The following figure shows the **Add/Remove Programs** dialog with several versions of the .NET runtime and SDK installed.</span></span>

![Диалоговое окно "Установка и удаление программ" для удаления .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="b6ef9-126">Выберите все версии, которые необходимо удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-126">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="b6ef9-127">Linux</span><span class="sxs-lookup"><span data-stu-id="b6ef9-127">Linux</span></span>](#tab/linux)

<span data-ttu-id="b6ef9-128">В Linux есть несколько вариантов удаления .NET Core (пакета SDK или среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="b6ef9-128">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="b6ef9-129">Лучший способ удаления .NET Core — выполнить действие, противоположное тому, которое использовалось при установке .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-129">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="b6ef9-130">Конкретные действия зависят от выбранного дистрибутива и метода установки.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-130">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6ef9-131">Сведения об установке и удалении .NET Core для систем Red Hat см. в [Руководстве по началу работы с Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).</span><span class="sxs-lookup"><span data-stu-id="b6ef9-131">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="b6ef9-132">Начиная с .NET Core 2.1 нет необходимости удалять пакет SDK для .NET Core при его обновлении с помощью диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-132">Starting with .NET Core 2.1, there's no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="b6ef9-133">Диспетчер пакетов `update` или команды `refresh` автоматически удалят старую версию после успешной установки более новой версии.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-133">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="b6ef9-134">Если вы установили .NET Core с помощью диспетчера пакетов, для удаления пакета SDK для .NET или среды выполнения используется тот же диспетчер пакетов.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-134">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="b6ef9-135">.NET Core поддерживает большинство популярных менеджеров пакетов.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-135">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="b6ef9-136">Точный синтаксис команды для вашей среды см. в документации по вашему дистрибутиву:</span><span class="sxs-lookup"><span data-stu-id="b6ef9-136">Consult the documentation for your distribution's package manager for the precise syntax on your environment:</span></span>

- <span data-ttu-id="b6ef9-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) используется в системах на основе Debian, включая Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-137">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="b6ef9-138">[yum(8)](https://linux.die.net/man/8/yum) используется в Fedora, CentOS и Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-138">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="b6ef9-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) используется в openSUSE и SUSE Linux Enterprise System (SLES).</span><span class="sxs-lookup"><span data-stu-id="b6ef9-139">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="b6ef9-140">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) используется в Fedora.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-140">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="b6ef9-141">Практически во всех случаях для удаления пакета используется команда `remove`.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-141">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="b6ef9-142">Для установки пакета SDK для .NET Core в большинстве диспетчеров пакетов используется имя пакета `dotnet-sdk`, за которым следует номер версии.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-142">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="b6ef9-143">Начиная с версии 2.1.300 пакета SDK для .NET Core и версии `2.1` среды выполнения необходимы только основной номер версии и дополнительный номер версии: например, для версии 2.1.300 пакета SDK для .NET Core можно указать пакет `dotnet-sdk-2.1`.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-143">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="b6ef9-144">В предыдущих версиях необходимо указать полную строку версии, например, для версии 2.1.200 пакета SDK для .NET Core потребовалось бы указать `dotnet-sdk-2.1.200`.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-144">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="b6ef9-145">Для компьютеров, на которых установлена только среда выполнения без пакета SDK, используется имя пакета `dotnet-runtime-<version>` для среды выполнения .NET Core и `aspnetcore-runtime-<version>` для стека всей среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-145">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="b6ef9-146">Для .NET Core версий ниже 2.0 ведущее приложение не удалялось при удалении пакета SDK с помощью диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-146">.NET Core installations earlier than 2.0 didn't uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="b6ef9-147">При использовании `apt-get` применяется следующая команда:</span><span class="sxs-lookup"><span data-stu-id="b6ef9-147">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="b6ef9-148">Обратите внимание, что с `dotnet-host`не связана версия.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-148">Note that there's no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="b6ef9-149">Если вы установили .NET Core из tar-архива, необходимо выполнить удаление вручную.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-149">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="b6ef9-150">Необходимо отдельно удалить пакеты SDK и среды выполнения, удалив каталог, содержащий эту версию.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-150">You remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="b6ef9-151">Например, чтобы удалить пакет SDK и среду выполнения версии 1.0.1, можно использовать следующие команды Bash:</span><span class="sxs-lookup"><span data-stu-id="b6ef9-151">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="b6ef9-152">Родительские каталоги для пакета SDK и среды выполнения указаны в выходных данных команд `dotnet --list-sdks` и `dotnet --list-runtimes`, как показано в приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-152">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="b6ef9-153">macOS</span><span class="sxs-lookup"><span data-stu-id="b6ef9-153">macOS</span></span>](#tab/macos)

<span data-ttu-id="b6ef9-154">На компьютерах Mac необходимо отдельно удалить пакеты SDK и среды выполнения, удалив каталог, содержащий эту версию.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-154">On Mac, you must remove the SDKs and runtimes separately, by removing the directory that contains that version.</span></span> <span data-ttu-id="b6ef9-155">Например, чтобы удалить пакет SDK и среду выполнения версии 1.0.1, можно использовать следующие команды Bash:</span><span class="sxs-lookup"><span data-stu-id="b6ef9-155">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

<span data-ttu-id="b6ef9-156">Родительские каталоги для пакета SDK и среды выполнения указаны в выходных данных команд `dotnet --list-sdks` и `dotnet --list-runtimes`, как показано в приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-156">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

---

## <a name="net-core-uninstall-tool"></a><span data-ttu-id="b6ef9-157">Средство удаления .NET Core</span><span class="sxs-lookup"><span data-stu-id="b6ef9-157">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="b6ef9-158">[Средство удаления .NET Core](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) позволяет удалять пакеты SDK и среды выполнения .NET Core из системы.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-158">The [.NET Core Uninstall Tool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and runtimes from a system.</span></span> <span data-ttu-id="b6ef9-159">Указать удаляемые версии можно с помощью ряда параметров.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-159">A collection of options is available to specify which versions should be uninstalled.</span></span>

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a><span data-ttu-id="b6ef9-160">Зависимость Visual Studio от версий пакетов SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="b6ef9-160">Visual Studio dependency on .NET Core SDK versions</span></span>

<span data-ttu-id="b6ef9-161">До появления Visual Studio 2019 версии 16.3, установщики Visual Studio пользовались автономным установщиком пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-161">Before Visual Studio 2019 version 16.3, Visual Studio installers called the standalone .NET Core SDK installer.</span></span> <span data-ttu-id="b6ef9-162">В результате версии пакета SDK отображаются в диалоговом окне Windows **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-162">As a result, the SDK versions appear in the Windows **Add/Remove Programs** dialog.</span></span> <span data-ttu-id="b6ef9-163">Удаление пакетов SDK для .NET Core, установленных Visual Studio с помощью автономного установщика, может нарушить работу Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-163">Removing .NET Core SDKs that were installed by Visual Studio using the standalone installer may break Visual Studio.</span></span> <span data-ttu-id="b6ef9-164">Если после удаления пакетов SDK в Visual Studio возникают проблемы, запустите "Восстановление" для этой конкретной версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-164">If Visual Studio has problems after you uninstall SDKs, run Repair on that specific version of Visual Studio.</span></span> <span data-ttu-id="b6ef9-165">В следующей таблице показаны некоторые зависимости Visual Studio от пакета SDK для версий .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-165">The following table shows some of the Visual Studio dependencies on .NET Core SDK versions:</span></span>

| <span data-ttu-id="b6ef9-166">Версия Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6ef9-166">Visual Studio version</span></span> | <span data-ttu-id="b6ef9-167">Версия пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="b6ef9-167">.NET Core SDK version</span></span> |
| -- | -- |
| <span data-ttu-id="b6ef9-168">Visual Studio 2019 версии 16.2</span><span class="sxs-lookup"><span data-stu-id="b6ef9-168">Visual Studio 2019 version 16.2</span></span> | <span data-ttu-id="b6ef9-169">пакет SDK для NET Core 2.2.4xx, 2.1.8xx</span><span class="sxs-lookup"><span data-stu-id="b6ef9-169">.NET Core SDK 2.2.4xx, 2.1.8xx</span></span> |
| <span data-ttu-id="b6ef9-170">Visual Studio 2019 версии 16.1</span><span class="sxs-lookup"><span data-stu-id="b6ef9-170">Visual Studio 2019 version 16.1</span></span> | <span data-ttu-id="b6ef9-171">пакет SDK для .NET Core 2.2.3xx, 2.1.7xx</span><span class="sxs-lookup"><span data-stu-id="b6ef9-171">.NET Core SDK 2.2.3xx, 2.1.7xx</span></span> |
| <span data-ttu-id="b6ef9-172">Visual Studio 2019 версии 16.0</span><span class="sxs-lookup"><span data-stu-id="b6ef9-172">Visual Studio 2019 version 16.0</span></span> | <span data-ttu-id="b6ef9-173">пакет SDK для .NET Core 2.2.2xx, 2.1.6xx</span><span class="sxs-lookup"><span data-stu-id="b6ef9-173">.NET Core SDK 2.2.2xx, 2.1.6xx</span></span> |
| <span data-ttu-id="b6ef9-174">Visual Studio 2017 версии 15.9</span><span class="sxs-lookup"><span data-stu-id="b6ef9-174">Visual Studio 2017 version 15.9</span></span> | <span data-ttu-id="b6ef9-175">Пакет SDK для .NET Core 2.2.1xx, 2.1.5xx</span><span class="sxs-lookup"><span data-stu-id="b6ef9-175">.NET Core SDK 2.2.1xx, 2.1.5xx</span></span> |
| <span data-ttu-id="b6ef9-176">Visual Studio 2017 версии 15.8</span><span class="sxs-lookup"><span data-stu-id="b6ef9-176">Visual Studio 2017 version 15.8</span></span> | <span data-ttu-id="b6ef9-177">Пакет SDK для .NET Core 2.1.4xx</span><span class="sxs-lookup"><span data-stu-id="b6ef9-177">.NET Core SDK 2.1.4xx</span></span> |

<span data-ttu-id="b6ef9-178">Visual Studio 2019 версии 16.3 и выше управляет собственной копией пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-178">Starting with Visual Studio 2019 version 16.3, Visual Studio is in charge of its own copy of the .NET Core SDK.</span></span> <span data-ttu-id="b6ef9-179">По этой причине вы больше не встретите эти версии пакета SDK в диалоговом окне **Установка и удаление программ**.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-179">For that reason, you no longer see those SDK versions in the **Add/Remove Programs** dialog.</span></span>

## <a name="remove-the-nuget-fallback-folder"></a><span data-ttu-id="b6ef9-180">Удаление резервной папки NuGet</span><span class="sxs-lookup"><span data-stu-id="b6ef9-180">Remove the NuGet fallback folder</span></span>

<span data-ttu-id="b6ef9-181">До создания пакета SDK для версии .NET Core 3.0, установщики пакета SDK для .NET Core использовали *NuGetFallbackFolder* для хранения кэша пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-181">Before .NET Core 3.0 SDK, the .NET Core SDK installers used the *NuGetFallbackFolder* to store a cache of NuGet packages.</span></span> <span data-ttu-id="b6ef9-182">Этот кэш использовался во время таких операций, как `dotnet restore` или `dotnet build /t:Restore`.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-182">This cache was used during operations such as `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="b6ef9-183">`NuGetFallbackFolder` находится в папке *C:\Program Files\dotnet\sdk* в Windows и в папке */usr/local/share/dotnet/sdk* в macOS.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-183">The `NuGetFallbackFolder` is located at *C:\Program Files\dotnet\sdk* on Windows and at */usr/local/share/dotnet/sdk* on macOS.</span></span>

<span data-ttu-id="b6ef9-184">Вы можете удалить эту папку, если:</span><span class="sxs-lookup"><span data-stu-id="b6ef9-184">You may want to remove this folder, if:</span></span>

* <span data-ttu-id="b6ef9-185">Разработка выполняется только с использованием пакета SDK для .NET Core 3.0 или более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-185">You're only developing using .NET Core 3.0 SDK or later versions.</span></span>
* <span data-ttu-id="b6ef9-186">Разработка выполняется с использованием пакета SDK для .NET Core более ранних версий, чем 3.0, но вы можете работать в режиме "в сети", что может привести к замедлению.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-186">You're developing using .NET Core SDK versions earlier than 3.0, but you can work online and things can be slower once.</span></span>

<span data-ttu-id="b6ef9-187">Если необходимо, вы можете удалить резервную папку NuGet, но для этого вам понадобятся права администратора.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-187">If you want to remove the NuGet fallback folder, you can delete it, but you'll need admin privileges to do so.</span></span>

<span data-ttu-id="b6ef9-188">Не рекомендуется удалять папку *dotnet*.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-188">It's not recommended to delete the *dotnet* folder.</span></span> <span data-ttu-id="b6ef9-189">Это приведет к удалению всех ранее установленных глобальных средств.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-189">Doing so would remove any global tools you've previously installed.</span></span> <span data-ttu-id="b6ef9-190">Также, в Windows:</span><span class="sxs-lookup"><span data-stu-id="b6ef9-190">Also, on Windows:</span></span>

- <span data-ttu-id="b6ef9-191">Работа Visual Studio 2019 версии 16.3 и более поздних версий будет нарушена.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-191">You'll break Visual Studio 2019 version 16.3 and later versions.</span></span> <span data-ttu-id="b6ef9-192">Для восстановления можно запустить **Восстановление**.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-192">You can run **Repair** to recover.</span></span>
- <span data-ttu-id="b6ef9-193">Если в диалоговом окне **Установка и удаление программ** есть записи пакета SDK для .NET Core — они будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="b6ef9-193">If there are .NET Core SDK entries in the **Add/Remove Programs** dialog, they'll be orphaned.</span></span>
