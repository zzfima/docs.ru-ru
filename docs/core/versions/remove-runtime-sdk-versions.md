---
title: Удаление среды выполнения .NET Core и пакета SDK
description: В этой статье объясняется, как определить установленные в текущее время версии среды выполнения .NET Core и пакета SDK и как затем удалить их в Windows, Mac и Linux.
ms.date: 12/17/2019
author: billwagner
ms.author: wiwagn
ms.custom: updateeachrelease
ms.openlocfilehash: 8f8dbf7a8730712dc546643a6ef86425a3e19794
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713989"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a>Как удалить среду выполнения .NET Core и пакет SDK

По мере установки обновленных версий среды выполнения и пакета SDK .NET Core может потребоваться удалить устаревшие версии .NET Core с вашего компьютера. При удалении более ранних версий среды выполнения может измениться среда выполнения, выбранная для запуска приложений общей платформы, как описано в статье [Выбор версии .NET Core](selection.md).

## <a name="should-i-remove-a-version"></a>Нужно ли удалять версию

[Выбор версии .NET Core](selection.md) и совместимость среды выполнения .NET Core для различных обновлений обеспечивает безопасное удаление предыдущих версий. Обновления среды выполнения .NET Core совместимы в пределах основной версии, например 1.x или 2.x. Кроме того, более поздние выпуски пакета SDK для .NET Core обычно позволяют создавать приложения, совместимые с предыдущими версиями среды выполнения.

Как правило, требуется только последняя версия пакета SDK и последняя версия исправлений для сред выполнения, необходимых для вашего приложения. Примеры хранения старых пакетов SDK или версий среды выполнения включают в себя поддержку **project.json** на базе приложений. Если у приложения нет конкретных причин, по которым оно должно использовать ранние версии пакета SDK или среды выполнения, вы можете безопасно удалить старые версии.

## <a name="determine-what-is-installed"></a>Определите компоненты, которые нужно установить

Начиная с .NET Core 2.1 можно определить версии пакета SDK и среды выполнения, установленных на вашем компьютере, с помощью команд в .NET CLI.  Чтобы просмотреть список пакетов SDK, установленных на вашем компьютере, выполните команду [`dotnet --list-sdks`](../tools/dotnet.md#options). Чтобы просмотреть список сред выполнения, установленных на вашем компьютере, выполните команду [`dotnet --list-runtimes`](../tools/dotnet.md#options). Ниже приведены типичные выходные данные для Windows, macOS и Linux:

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

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

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

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

# <a name="macostabmacos"></a>[macOS](#tab/macos)

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

## <a name="uninstalling-net-core"></a>Удаление .NET Core

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

Для удаления версий среды выполнения и пакета SDK .NET Core используется диалоговое окно **Установка и удаление программ** Windows. На следующем рисунке показано диалоговое окно **Установка и удаление программ** с несколькими установленными версиями среды выполнения и пакета SDK .NET.

![Диалоговое окно "Установка и удаление программ" для удаления .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

Выберите все версии, которые необходимо удалить, и нажмите кнопку **Удалить**.

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

В Linux есть несколько вариантов удаления .NET Core (пакета SDK или среды выполнения). Лучший способ удаления .NET Core — выполнить действие, противоположное тому, которое использовалось при установке .NET Core. Конкретные действия зависят от выбранного дистрибутива и метода установки.

> [!IMPORTANT]
> Сведения об установке и удалении .NET Core для систем Red Hat см. в [Руководстве по началу работы с Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).

Начиная с .NET Core 2.1 нет необходимости удалять пакет SDK для .NET Core при его обновлении с помощью диспетчера пакетов. Диспетчер пакетов `update` или команды `refresh` автоматически удалят старую версию после успешной установки более новой версии.

Если вы установили .NET Core с помощью диспетчера пакетов, для удаления пакета SDK для .NET или среды выполнения используется тот же диспетчер пакетов. .NET Core поддерживает большинство популярных менеджеров пакетов. Точный синтаксис команды для вашей среды см. в документации по вашему дистрибутиву:

- [apt-get(8)](https://linux.die.net/man/8/apt-get) используется в системах на основе Debian, включая Ubuntu.
- [yum(8)](https://linux.die.net/man/8/yum) используется в Fedora, CentOS и Oracle Linux.
- [zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) используется в openSUSE и SUSE Linux Enterprise System (SLES).
- [dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) используется в Fedora.

Практически во всех случаях для удаления пакета используется команда `remove`.

Для установки пакета SDK для .NET Core в большинстве диспетчеров пакетов используется имя пакета `dotnet-sdk`, за которым следует номер версии. Начиная с версии 2.1.300 пакета SDK для .NET Core и версии `2.1` среды выполнения необходимы только основной номер версии и дополнительный номер версии: например, для версии 2.1.300 пакета SDK для .NET Core можно указать пакет `dotnet-sdk-2.1`. В предыдущих версиях необходимо указать полную строку версии, например, для версии 2.1.200 пакета SDK для .NET Core потребовалось бы указать `dotnet-sdk-2.1.200`.

Для компьютеров, на которых установлена только среда выполнения без пакета SDK, используется имя пакета `dotnet-runtime-<version>` для среды выполнения .NET Core и `aspnetcore-runtime-<version>` для стека всей среды выполнения.

Для .NET Core версий ниже 2.0 ведущее приложение не удалялось при удалении пакета SDK с помощью диспетчера пакетов. При использовании `apt-get` применяется следующая команда:

```bash
apt-get remove dotnet-host
```

Обратите внимание, что с `dotnet-host`не связана версия.

Если вы установили .NET Core из tar-архива, необходимо выполнить удаление вручную.

Необходимо отдельно удалить пакеты SDK и среды выполнения, удалив каталог, содержащий эту версию. Например, чтобы удалить пакет SDK и среду выполнения версии 1.0.1, можно использовать следующие команды Bash:

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

Родительские каталоги для пакета SDK и среды выполнения указаны в выходных данных команд `dotnet --list-sdks` и `dotnet --list-runtimes`, как показано в приведенной выше таблице.

# <a name="macostabmacos"></a>[macOS](#tab/macos)

На компьютерах Mac необходимо отдельно удалить пакеты SDK и среды выполнения, удалив каталог, содержащий эту версию. Например, чтобы удалить пакет SDK и среду выполнения версии 1.0.1, можно использовать следующие команды Bash:

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

Родительские каталоги для пакета SDK и среды выполнения указаны в выходных данных команд `dotnet --list-sdks` и `dotnet --list-runtimes`, как показано в приведенной выше таблице.

---

## <a name="net-core-uninstall-tool"></a>Средство удаления .NET Core

[Средство удаления .NET Core](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) позволяет удалять пакеты SDK и среды выполнения .NET Core из системы. Указать удаляемые версии можно с помощью ряда параметров.

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a>Зависимость Visual Studio от версий пакетов SDK для .NET Core

До появления Visual Studio 2019 версии 16.3, установщики Visual Studio пользовались автономным установщиком пакета SDK для .NET Core. В результате версии пакета SDK отображаются в диалоговом окне Windows **Установка и удаление программ**. Удаление пакетов SDK для .NET Core, установленных Visual Studio с помощью автономного установщика, может нарушить работу Visual Studio. Если после удаления пакетов SDK в Visual Studio возникают проблемы, запустите "Восстановление" для этой конкретной версии Visual Studio. В следующей таблице показаны некоторые зависимости Visual Studio от пакета SDK для версий .NET Core.

| Версия Visual Studio | Версия пакета SDK для .NET Core |
| -- | -- |
| Visual Studio 2019 версии 16.2 | пакет SDK для NET Core 2.2.4xx, 2.1.8xx |
| Visual Studio 2019 версии 16.1 | пакет SDK для .NET Core 2.2.3xx, 2.1.7xx |
| Visual Studio 2019 версии 16.0 | пакет SDK для .NET Core 2.2.2xx, 2.1.6xx |
| Visual Studio 2017 версии 15.9 | Пакет SDK для .NET Core 2.2.1xx, 2.1.5xx |
| Visual Studio 2017 версии 15.8 | Пакет SDK для .NET Core 2.1.4xx |

Начиная с Visual Studio 2019 версии 16.3, Visual Studio управляет собственной копией пакета SDK для .NET Core. По этой причине вы больше не встретите эти версии пакета SDK в диалоговом окне **Установка и удаление программ**.

## <a name="remove-the-nuget-fallback-folder"></a>Удаление резервной папки NuGet

До создания пакета SDK для версии .NET Core 3.0, установщики пакета SDK для .NET Core использовали *NuGetFallbackFolder* для хранения кэша пакетов NuGet. Этот кэш использовался во время таких операций, как `dotnet restore` или `dotnet build /t:Restore`. `NuGetFallbackFolder` находится в папке *C:\Program Files\dotnet\sdk* в Windows и в папке */usr/local/share/dotnet/sdk* в macOS.

Вы можете удалить эту папку, если:

* Разработка выполняется только с использованием пакета SDK для .NET Core 3.0 или более поздних версий.
* Разработка выполняется с использованием пакета SDK для .NET Core более ранних версий, чем 3.0, но вы можете работать в режиме "в сети", что может привести к замедлению.

Если необходимо, вы можете удалить резервную папку NuGet, но для этого вам понадобятся права администратора.

Не рекомендуется удалять папку *dotnet*. Это приведет к удалению всех ранее установленных глобальных средств. Также, в Windows:

- Работа Visual Studio 2019 версии 16.3 и более поздних версий будет нарушена. Для восстановления можно запустить **Восстановление**.
- Если в диалоговом окне **Установка и удаление программ** есть записи пакета SDK для .NET Core — они будут потеряны.
