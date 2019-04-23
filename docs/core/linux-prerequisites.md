---
title: Необходимые компоненты для .NET Core в Linux
description: Поддерживаемые версии Linux и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с Linux.
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 0bd3287535ba2c398f6577890d1d39f42a806364
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612229"
---
# <a name="prerequisites-for-net-core-on-linux"></a>Необходимые компоненты для .NET Core в Linux

В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Linux. Поддерживаемые дистрибутивы и версии Linux, а также перечисленные ниже зависимости относятся к двум способам разработки приложений .NET Core в Linux:

* [командная строка и любой редактор;](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code.](https://code.visualstudio.com/)

> [!NOTE]
> Пакет SDK для .NET Core не требуется для рабочих серверов и сред. Для приложений, развертываемых в рабочих средах, требуется только пакет среды выполнения .NET Core. Среда выполнения .NET Core развертывается вместе с приложениями в рамках автономного развертывания, однако для приложений, зависимых от платформы, ее необходимо развертывать отдельно. Дополнительные сведения о зависимых от платформы и автономных типах развертывания см. в статье [Развертывание приложений .NET Core](./deploying/index.md). Также см. статью [Автономные приложения Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

## <a name="supported-linux-versions"></a>Поддерживаемые версии Linux

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x воспринимает Linux как отдельную операционную систему. Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux. 

Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания для [.NET Core 2.2](https://www.microsoft.com/net/download/dotnet-core/2.2) или [.NET Core 2.1](https://www.microsoft.com/net/download/dotnet-core/2.1).

.NET Core 2.x поддерживается в следующих дистрибутивах и версиях Linux:

* Red Hat Enterprise Linux 7, 6 — 64-разрядная версия (`x86_64` или `amd64`);
* CentOS 7 — 64-разрядная версия (`x86_64` или `amd64`); 
* Oracle Linux 7 — 64-разрядная версия (`x86_64` или `amd64`); 
* Fedora 28, 27 — 64-разрядная версия (`x86_64` или `amd64`); 
* Debian 9 (64-разрядная версия, версия `arm32`), а также версия 8.7 или более поздние для 64-разрядных платформ — (`x86_64` или `amd64`)
* Ubuntu 18.04 (64-разрядная версия, версия `arm32`), а также версии 16.04 и 14.04 для 64-разрядных платформ (`x86_64` или `amd64`)
* Linux Mint 18, 17 — 64-разрядная версия (`x86_64` или `amd64`);
* openSUSE 42.3 или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`);
* SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`);
* Alpine Linux 3.7 или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`).

Полный список операционных систем, дистрибутивов, версий, поддерживаемых .NET Core 2.1 и .NET Core 2.2, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на соответствующих страницах для [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) и [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания для [.NET Core 1.1](https://www.microsoft.com/net/download/dotnet-core/1.1) или [.NET Core 1.0](https://www.microsoft.com/net/download/dotnet-core/1.0).

.NET Core 1.x поддерживается в следующих дистрибутивах и версиях 64-разрядной версии Linux (`x86_64` или `amd64`):

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 28 (.NET Core 1.1), 27
* Debian 8.2 или более поздней версии
* Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04
* Linux Mint 17
* openSUSE 42.3 или более поздней версии (.NET Core 1.1)

Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).

# <a name="net-core-30-preview-1tabnetcore30"></a>[.NET Core 3.0 (предварительная версия 1)](#tab/netcore30)

.NET Core 3.0 (предварительная версия 1) воспринимает Linux как отдельную операционную систему. Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux. 

Ознакомьтесь с дополнительными сведениями и воспользуйтесь ссылками для скачивания [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).

.NET Core 3.0 (предварительная версия 1) поддерживается в следующих дистрибутивах и версиях Linux: 

Операционная система                            | Версия               | Архитектуры  
------------------------------|-----------------------|----------------
Red Hat Enterprise Linux      | 6                     | X64
Red Hat Enterprise Linux<br>CentOS<br>Oracle Linux  | 7                     | X64
Fedora                        | 28                    | X64
Debian                        | 9                     | x64, ARM32\*, ARM64\*
Ubuntu                        | 16.04+, 18.04+        | x64, ARM32\*, ARM64\*
Linux Mint                    | 18                    | X64
openSUSE                      | 42.3+                 | X64
SUSE Enterprise Linux (SLES)  | 12 с пакетом обновления 2+               | X64
Alpine Linux                  | 3.8+                  | x64, ARM64

\* Поддержка ARM32 и ARM64 начинается с Debian 9 и Ubuntu 16.04. Более ранние версии этих дистрибутивов не поддерживаются на микросхемах ARM.

Полный список операционных систем, дистрибутивов и версий, поддерживаемых .NET Core 3.0, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [версий ОС, поддерживаемых .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

Дополнительные сведения об установке .NET Core 3.0 в ARM64 см. в [этой статье](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).

---

## <a name="linux-distribution-dependencies"></a>Зависимости дистрибутивов Linux

Ниже представлены примеры. Точные версии и имена могут немного отличаться в зависимости от используемого дистрибутива Linux.

### <a name="ubuntu"></a>Ubuntu

Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:

* liblttng-ust0
* libcurl3 (для 14.x и 16.x)
* libcurl4 (для 18.x)
* libssl1.0.0
* libkrb5-3
* zlib1g
* libicu52 (для 14.x)
* libicu55 (для 16.x)
* libicu57 (для 17.x)
* libicu60 (для 18.x)

Для версий более ранних, чем .NET Core 2.1, также требуются следующие зависимости:

* libunwind8
* libuuid1

### <a name="centos-and-fedora"></a>CentOS и Fedora

Для дистрибутивов CentOS должны быть установлены следующие библиотеки:

* lttng-ust
* libcurl
* openssl-libs
* krb5-libs
* libicu
* zlib

Для пользователей Fedora: если вы используете openssl версии до 1.1, вам потребуется установить compat-openssl10.

Для версий более ранних, чем .NET Core 2.1, также требуются следующие зависимости:

* libunwind
* libuuid

Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Установка зависимостей .NET Core с помощью собственных установщиков

Для поддерживаемых дистрибутивов и версий Linux доступны собственные установщики .NET Core. Собственные установщики требуют доступа администратора (sudo) к серверу. Преимущество использования собственного установщика заключается в том, что он устанавливает все собственные зависимости .NET Core. Собственные установщики также устанавливают пакет SDK для .NET Core в масштабе всей системы.

В Linux есть два варианта выбора пакета установщика:

* диспетчер пакетов на основе веб-канала, например apt-get для Ubuntu или yum для CentOS/RHEL;
* сами пакеты (DEB или RPM).

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Установка с помощью скрипта установщика .NET Core

[Скрипты dotnet-install](./tools/dotnet-install-script.md) служат для установки цепочки инструментов CLI и общей среды выполнения без прав администратора. Скрипт можно скачать на странице <https://dot.net/v1/dotnet-install.sh>.

Скрипт по умолчанию устанавливает последнюю версию LTS. В данный момент это .NET Core 1.1. Чтобы установить .NET Core 2.1, запустите скрипт с таким параметром.

```console
./dotnet-install.sh -c Current
```

Скрипт bash установщика используется в сценариях автоматизации и установки без прав администратора. Скрипт также считывает параметры PowerShell, чтобы их можно было использовать с этим скриптом в системах Linux и OS X.

## <a name="troubleshoot"></a>Устранение неполадок

Если при установке .NET Core в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к статье для используемого дистрибутива и версии:

* [Известные проблемы в .NET Core 3.0](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [Известные проблемы в .NET Core 2.2](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [Известные проблемы в .NET Core 2.1](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [Известные проблемы в .NET Core 1.1](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [Известные проблемы в .NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0)
