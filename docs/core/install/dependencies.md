---
title: Зависимости пакета SDK для .NET Core и среды выполнения .NET Core — .NET Core
description: Сведения о предварительных требованиях к операционной системе и архитектуре ЦП для установки пакета SDK для .NET Core и среды выполнения .NET Core в Windows, Linux и macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546566"
---
# <a name="net-core-dependencies-and-requirements"></a>Зависимости и требования для .NET Core

Эта статья описывает, какие операционные системы и архитектура ЦП поддерживаются в .NET Core.

## <a name="supported-operating-systems"></a>Поддерживаемые операционные системы

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1 поддерживает следующие версии Windows:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                            | Version                        | Архитектуры   |
| ----------------------------- | ------------------------------ | --------------- |
| Клиент Windows                | 7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1                    | x64, x86        |
| Клиент Windows 10             | Версия 1607+                  | x64, x86        |
| Windows Server                | 2012 R2+                       | x64, x86        |
| Nano Server                   | Версия 1803+                  | x64, ARM32      |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.1, см. в статье [Поддерживаемые .NET Core 3.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*Сейчас .NET Core 3.0 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 3.0 поддерживает следующие версии Windows:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                            | Version                        | Архитектуры   |
| ----------------------------- | ------------------------------ | --------------- |
| Клиент Windows                | 7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1                    | x64, x86        |
| Клиент Windows 10             | Версия 1607+                  | x64, x86        |
| Windows Server                | 2012 R2+                       | x64, x86        |
| Nano Server                   | Версия 1803+                  | x64, ARM32      |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.0, см. в статье [Поддерживаемые .NET Core 3.0 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*Сейчас .NET Core 2.2 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 2.2 поддерживает следующие версии Windows:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                            | Version                        | Архитектуры   |
| ----------------------------- | ------------------------------ | --------------- |
| Клиент Windows                | 7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1                    | x64, x86        |
| Клиент Windows 10             | Версия 1607+                  | x64, x86        |
| Windows Server                | 2008 R2 с пакетом обновления 1 или более поздней версии (SP1+)                   | x64, x86        |
| Nano Server                   | Версия 1803+                   | x64, ARM32      |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.2, см. в статье [Поддерживаемые .NET Core 2.2 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 поддерживает следующие версии Windows:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                            | Version                        | Архитектуры   |
| ----------------------------- | ------------------------------ | --------------- |
| Клиент Windows                | 7 с пакетом обновления 1 и более поздних версий (SP1+), 8.1                    | x64, x86        |
| Клиент Windows 10             | Версия 1607+                  | x64, x86        |
| Windows Server                | 2008 R2 с пакетом обновления 1 или более поздней версии (SP1+)                   | x64, x86        |
| Nano Server                   | Версия 1803+                  | x64,            |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.1, см. в статье [Поддерживаемые .NET Core 2.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a>Windows 7/Vista/8.1/Server 2008 R2

При установке пакета SDK для .NET или среды выполнения .NET в следующих версиях Windows требуются дополнительные зависимости:

- Windows 7 SP1
- Windows Vista с пакетом обновления 2 (SP2)
- Windows 8.1
- Windows Server 2008 R2
- Windows Server 2012 R2

Установите следующие компоненты:

- [Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685).
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

Приведенные выше требования также применяются, если возникает одна из следующих ошибок:

> Запуск программы невозможен, так как на компьютере отсутствует *api-ms-win-crt-runtime-l1-1-0.dll*. Попробуйте переустановить программу.
>
> \- или -
>
> Библиотека *hostfxr.dll* найдена, но при ее загрузке из *C:\\\<путь_к_приложению>\\hostfxr.dll* произошел сбой.

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1 воспринимает Linux как отдельную операционную систему. Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.

.NET Core 3.1 поддерживается в следующих дистрибутивах и версиях Linux:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                             | Version               | Архитектуры    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | X64 |
| CentOS                         | 7 или выше                    | X64 |
| Oracle Linux                   | 7 или выше                    | X64 |
| Fedora                         | 30 или выше                   | X64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18+                   | X64 |
| openSUSE                       | 15+                   | X64 |
| SUSE Enterprise Linux (SLES)   | 12 с пакетом обновления 2+               | X64 |
| Alpine Linux                   | 3.10+                 | x64, ARM64 |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.1, см. в статье [Поддерживаемые .NET Core 3.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

Дополнительные сведения об установке .NET Core 3.1 в ARM64 (ядро 4.14+) см. в статье [Установка .NET Core 3.0 в Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).

> [!IMPORTANT]
> Для поддержки ARM64 требуется ядро Linux 4.14 или более высокой версии. Некоторые дистрибутивы Linux отвечают этому требованию, а другие — нет. Например, Ubuntu 18.04 поддерживается, а Ubuntu 16.04 — нет.

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*Сейчас .NET Core 3.0 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 3.0 воспринимает Linux как отдельную операционную систему. Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.

.NET Core 3.0 поддерживается в следующих дистрибутивах и версиях Linux:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                             | Version               | Архитектуры    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | X64 |
| CentOS                         | 7 или выше                    | X64 |
| Oracle Linux                   | 7 или выше                    | X64 |
| Fedora                         | 29+                   | X64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18+                   | X64 |
| openSUSE                       | 15+                   | X64 |
| SUSE Enterprise Linux (SLES)   | 12 с пакетом обновления 2+               | X64 |
| Alpine Linux                   | 3.8+                  | x64, ARM64 |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 3.0, см. в статье [Поддерживаемые .NET Core 3.0 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

Дополнительные сведения об установке .NET Core 3.0 в ARM64 см. в [этой статье](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*Сейчас .NET Core 2.2 не поддерживается. Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 2.2 воспринимает Linux как отдельную операционную систему. Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.

.NET Core 2.2 поддерживается в следующих дистрибутивах и версиях Linux.

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                             |  Version                |  Архитектуры   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7                   | X64 |
| CentOS                         |  7                      | X64 |
| Oracle Linux                   |  7                      | X64 |
| Fedora                         |  29, 30                 | X64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 18.10    | x64, ARM32 |
| Linux Mint                     |  17, 18                 | X64 |
| openSUSE                       |  15+                    | X64 |
| SUSE Enterprise Linux (SLES)   |  12 с пакетом обновления 2+                | X64 |
| Alpine Linux                   |  3.8+                   | X64 |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.2, см. в статье [Поддерживаемые .NET Core 2.2 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 воспринимает Linux как отдельную операционную систему. Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.

.NET Core 2.1 поддерживается в следующих дистрибутивах и версиях Linux.

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Операционная система                             |  Version                |  Архитектуры   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7, 8                | X64 |
| CentOS                         |  7 или выше                     | X64 |
| Oracle Linux                   |  7 или выше                     | X64 |
| Fedora                         |  30 или выше                    | X64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 19.04, 19.10    | x64, ARM32 |
| Linux Mint                     |  17+                    | X64 |
| openSUSE                       |  15+                    | X64 |
| SUSE Enterprise Linux (SLES)   |  12 с пакетом обновления 2+                | X64 |
| Alpine Linux                   |  3.8+                   | X64 |

Дополнительные сведения об операционных системах, дистрибутивах и политике жизненного цикла, поддерживаемых .NET Core 2.1, см. в статье [Поддерживаемые .NET Core 2.1 версии ОС](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

## <a name="linux-distribution-dependencies"></a>Зависимости дистрибутивов Linux

В зависимости от дистрибутива Linux может потребоваться установить дополнительные зависимости.

> [!IMPORTANT]
> Точные версии и имена могут немного отличаться в зависимости от используемого дистрибутива Linux.

### <a name="ubuntu"></a>Ubuntu

Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:

- liblttng-ust0
- libcurl3 (для 14.x и 16.x)
- libcurl4 (для 18.x)
- libssl1.0.0
- libkrb5-3
- zlib1g
- libicu52 (для 14.x)
- libicu55 (для 16.x)
- libicu57 (для 17.x)
- libicu60 (для 18.x)

Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:

- libgdiplus (версия 6.0.1 или выше)

> [!WARNING]
> В большинство версий Ubuntu входит более ранняя версия libgdiplus. Вы можете установить последнюю версию libgdiplus, добавив в систему репозиторий Mono. Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.

### <a name="centos-and-fedora"></a>CentOS и Fedora

Для дистрибутивов CentOS должны быть установлены следующие библиотеки:

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib

Для пользователей Fedora: Если ваша версия OpenSSL не ниже 1.1, потребуется установить **compat-openssl10**.

Для .NET Core 2.0 также требуются следующие зависимости:

- libunwind
- libuuid

Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:

- libgdiplus (версия 6.0.1 или выше)

> [!WARNING]
> В большинство версий CentOS и Fedora входит более ранняя версия libgdiplus. Вы можете установить последнюю версию libgdiplus, добавив в систему репозиторий Mono. Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.

::: zone-end

::: zone pivot="os-macos"

Платформа .NET Core поддерживается в следующих выпусках macOS:

> [!NOTE]
> Символ `+` представляет минимальную версию.

| Версия .NET Core | macOS                 | Архитектуры |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra (10.13+)  | X64 | [Дополнительные сведения](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra (10.13+)  | X64 | [Дополнительные сведения](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12+)       | X64 | [Дополнительные сведения](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12+)       | X64 | [Дополнительные сведения](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

Начиная с macOS Catalina (версия 10.15) все программное обеспечение, созданное после 1 июня 2019 года и распространяемое с идентификатором разработчика, должно быть заверено. Это требование относится к среде выполнения .NET Core, пакету SDK для .NET Core и программному обеспечению, созданному с помощью .NET Core.

Установщики для .NET Core (среда выполнения и пакет SDK) версии 3.1, 3.0 и 2.1 были заверены с 18 февраля 2020 г. Более ранние версии не заверены. При запуске незаверенного приложения появится ошибка, аналогичная следующей:

![Оповещение о заверении macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

Дополнительные сведения о том, как принудительное заверение влияет на .NET Core (и ваши приложения .NET Core), см. в разделе [Работа с заверением macOS Catalina](macos-notarization-issues.md).

## <a name="libgdiplus"></a>libgdiplus

Приложения .NET Core, которые используют сборку *System.Drawing.Common*, требуют установки libgdiplus.

Легко получить libgdiplus можно с помощью диспетчера пакетов [Homebrew ("brew")](https://brew.sh/) для macOS. После установки *brew* установите libgdiplus, выполнив следующие команды в окне терминала (аналог командной строки):

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a>Следующие шаги

- Для разработки и запуска приложений установите [пакет SDK для .NET Core](sdk.md) (включает в себя среду выполнения).
- Для запуска приложений, созданных другими пользователями, установите [среду выполнения .NET Core](runtime.md).
