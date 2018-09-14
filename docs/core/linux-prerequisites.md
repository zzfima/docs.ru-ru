---
title: Необходимые компоненты для .NET Core в Linux
description: Поддерживаемые версии Linux и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с Linux.
author: jralexander
ms.author: johalex
ms.date: 08/20/2018
ms.openlocfilehash: d0e5b203dc8e1ec6807f28de7d910c74a2ffe665
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506853"
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

**NET Core 2.1**

.NET Core 2.1 поддерживается в следующих дистрибутивах и версиях Linux:

* Red Hat Enterprise Linux 7, 6 — 64-разрядная версия (`x86_64` или `amd64`);
* CentOS 7 — 64-разрядная версия (`x86_64` или `amd64`); 
* Oracle Linux 7 — 64-разрядная версия (`x86_64` или `amd64`); 
* Fedora 28, 27 — 64-разрядная версия (`x86_64` или `amd64`); 
* Debian 9 (64-разрядная версия, ARM32), 8.7 или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`);
* Ubuntu 18.04 (64-разрядная версия, ARM32), 16.04, 14.04 — 64-разрядная версия (`x86_64` или `amd64`);
* Linux Mint 18, 17 — 64-разрядная версия (`x86_64` или `amd64`);
* openSUSE 42.3 или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`);
* SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`);
* Alpine Linux 3.7 или более поздней версии — 64-разрядная версия (`x86_64` или `amd64`).

Полный список операционных систем, дистрибутивов и версий, поддерживаемых .NET Core 2.1, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

**NET Core 2.0**

.NET Core 2.0 поддерживается в следующих дистрибутивах и версиях 64-разрядной версии Linux (`x86_64` или `amd64`):

* Red Hat Enterprise Linux 7, 6
* CentOS 7
* Oracle Linux 7
* Fedora 27
* Debian 9, 8.7 или более поздней версии
* Ubuntu 18.04, 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 или более поздней версии
* SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздней версии

Полный список операционных систем, дистрибутивов и версий, поддерживаемых .NET Core 2.0, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.0](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

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

---

## <a name="linux-distribution-dependencies"></a>Зависимости дистрибутивов Linux

Ниже представлены примеры. Точные версии и имена могут немного отличаться в зависимости от используемого дистрибутива Linux.

### <a name="ubuntu"></a>Ubuntu

Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:

* liblttng-ust0
* libcurl3
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

[Скрипты dotnet-install](./tools/dotnet-install-script.md) служат для установки цепочки инструментов CLI и общей среды выполнения без прав администратора. Скрипт можно скачать на странице [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).

Скрипт по умолчанию устанавливает последнюю версию LTS. В данный момент это .NET Core 1.1. Чтобы установить .NET Core 2.x, запустите скрипт со следующим параметром:

```console
./dotnet-install.sh -c Current
```

Скрипт bash установщика используется в сценариях автоматизации и установки без прав администратора. Скрипт также считывает параметры PowerShell, чтобы их можно было использовать с этим скриптом в системах Linux и OS X.

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a>Установка .NET Core для поддерживаемых версий Red Hat Enterprise Linux (RHEL)

Чтобы установить .NET Core в поддерживаемых версиях RHEL, выполните указанные ниже действия.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**.NET Core 2.1**

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Актуальные сведения об установке .NET Core 2.1 в Red Hat Enterprise Linux см. в [руководстве по началу работы с .NET Core 2.1](https://access.redhat.com/documentation/en-us/net_core/2.1/html/getting_started_guide/).

**.NET Core 2.0**

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Актуальные сведения об установке .NET Core 2.0 в Red Hat Enterprise Linux см. в [руководстве по началу работы с .NET Core 2.0](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/). 

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2.  Актуальные сведения об установке .NET Core 1.1 в Red Hat Enterprise Linux см. в [руководстве по началу работы с .NET Core 1.1](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/).
     
**.NET Core 1.0**

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2.  Актуальные сведения об установке .NET Core 1.0 в Red Hat Enterprise Linux см. в [руководстве по началу работы с .NET Core 1.0](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/).

Справку по регистрации для доступа к каналу Red Hat .NET см. в [главе 1 руководства по началу работы с .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) на сайте Red Hat.

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a>Установка .NET Core для поддерживаемых дистрибутивов и версий Ubuntu и Linux Mint (64-разрядных)

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core  2.x в поддерживаемых дистрибутивах и версиях Ubuntu или Linux Mint (64-разрядных).

**.NET Core 2.0**

|Среды выполнения и пакеты SDK          |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04 и Linux Mint 18|Ubuntu 14.04 и Linux Mint 17|
|-------------------------|----------------|----------------|----------------------------|----------------------------|
|Среда выполнения .NET Core 2.0.9  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.9)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.9)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.9)          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.9)            |
|Среда выполнения .NET Core 2.0.8  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.8)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.8)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.8)          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.8)            |
|Среда выполнения .NET Core 2.0.7  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.7)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.7)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.7)          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.7)            |
|Среда выполнения .NET Core 2.0.6  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.6)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|Среда выполнения .NET Core 2.0.5  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.5)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|Пакет SDK для .NET Core 2.1.202    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.202)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.202)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.202)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.202)            |
|Пакет SDK для .NET Core 2.1.201    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.201)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.201)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.201)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.201)            |
|Пакет SDK для .NET Core 2.1.200    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.200)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.200)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.200)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.200)            |
|Пакет SDK для .NET Core 2.1.105    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.105)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.105)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.105)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.105)            |
|Пакет SDK для .NET Core 2.1.103    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.103)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|Пакет SDK для .NET Core 2.0.3      |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.3)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |
|Пакет SDK для .NET Core 2.0.0      |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.0)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.0)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.0)          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.0)            |

**.NET Core 2.1**

>[!IMPORTANT]
> Чтобы использовать .NET Core 2.1 с Visual Studio, необходимо [установить Visual Studio 2017 15.7 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

|Среды выполнения и пакеты SDK          |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04 и Linux Mint 18|Ubuntu 14.04 и Linux Mint 17|
|-------------------------|----------------|----------------|----------------------------|----------------------------|
|Среда выполнения .NET Core 2.1.2          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.2)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.2)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.2)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.2)            |
|Пакет SDK для .NET Core 2.1.400     |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.400)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.400)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.400)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.400)            |
|Пакет SDK для .NET Core 2.1.302     |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.302)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.302)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.302)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.302)            |
|Среда выполнения .NET Core 2.1.1          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.1)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.1)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.1)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.1)            |
|Пакет SDK для .NET Core 2.1.301     |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.301)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.301)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.301)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.301)            |
|Среда выполнения .NET Core 2.1.0          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0)            |
|Пакет SDK для .NET Core 2.1.300     |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300)|[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300)            |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300)            |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core  1.x в поддерживаемых дистрибутивах и версиях Ubuntu или Linux Mint (64-разрядных).

| Среды выполнения и пакеты SDK         |Ubuntu 16.04 и Linux Mint 18|Ubuntu 14.04 и Linux Mint 17|
|-------------------------|----------------------------|----------------------------|
|Среда выполнения .NET Core 1.1.9  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.1.8  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.1.7  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.1.6  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.1.5  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.1.4  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.0.10 |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.0.9  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.0.8  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.0.7  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.0.5  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-ubuntu-14.04-x64-binaries)            |
|Среда выполнения .NET Core 1.0.4  |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|Пакет SDK для .NET Core 1.1.10     |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-ubuntu-14.04-x64-binaries)            |
|Пакет SDK для .NET Core 1.1.9      |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-ubuntu-14.04-x64-binaries)            |
|Пакет SDK для .NET Core 1.1.8      |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|Пакет SDK для .NET Core 1.1.7      |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|Пакет SDK для .NET Core 1.1.5      |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-ubuntu-14.04-x64-binaries)            |
|Пакет SDK для .NET Core 1.1.4      |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-ubuntu-14.04-x64-binaries)            |
|Пакет SDK для .NET Core 1.0.4      |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|Пакет SDK для .NET Core 1.0.1      |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[Ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a>Установка .NET Core для поддерживаемых версий Debian (64-разрядных)

Чтобы установить .NET Core в поддерживаемых версиях Debian (64-разрядных), выполните указанные ниже действия.

> [!NOTE]
> Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core 2.x в поддерживаемых версиях Debian (64-разрядных).

**.NET Core 2.0**

|Среды выполнения и пакеты SDK          |Debian 9       |Debian 8       |
|-------------------------|---------------|---------------|
|Среда выполнения .NET Core 2.0.9  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.9)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.9)   |
|Среда выполнения .NET Core 2.0.8  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.8)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.8)   |
|Среда выполнения .NET Core 2.0.7  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.7)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.7)   |
|Среда выполнения .NET Core 2.0.6  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|Среда выполнения .NET Core 2.0.5  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|Среда выполнения .NET Core 2.0.3  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.3)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.3)   |
|Среда выполнения .NET Core 2.0.0  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.0)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.0)   |
|Пакет SDK для .NET Core 2.1.202    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.202)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.202)   |
|Пакет SDK для .NET Core 2.1.201    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.201)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.201)   |
|Пакет SDK для .NET Core 2.1.200    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.200)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.200)   |
|Пакет SDK для .NET Core 2.1.105    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.105)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.105)   |
|Пакет SDK для .NET Core 2.1.105    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.105)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.105)   |
|Пакет SDK для .NET Core 2.1.104    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.104)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.104)   |
|Пакет SDK для .NET Core 2.1.103    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|Пакет SDK для .NET Core 2.1.102    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.102)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.102)   |
|Пакет SDK для .NET Core 2.1.101    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.101)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.101)   |
|Пакет SDK для .NET Core 2.0.3      |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |
|Пакет SDK для .NET Core 2.0.0      |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.0)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.0)   |

**.NET Core 2.1**

>[!IMPORTANT]
> Чтобы использовать .NET Core 2.1 с Visual Studio, необходимо [установить Visual Studio 2017 15.7 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

|Среды выполнения и пакеты SDK                  |Debian 9       |Debian 8       |
|---------------------------------|---------------|---------------|
|Среда выполнения .NET Core 2.1.2          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.2)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.2)   |
|Пакет SDK для .NET Core 2.1.400        |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.400)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.400)        |
|Пакет SDK для .NET Core 2.1.302        |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.302)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.302)        |
|Среда выполнения .NET Core 2.1.1          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.1)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.1)   |
|Пакет SDK для .NET Core 2.1.301        |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.301)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.301)        |
|Среда выполнения .NET Core 2.1.0          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0)   |
|Пакет SDK для .NET Core 2.1.300        |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300)   |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300)        |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core 1.x в Debian 9 или Debian 8.

* Среда выполнения .NET Core 1.1.9: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.1.8: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.1.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.1.6: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.1.5: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.1.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.1.2: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.1.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.1.0: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.0-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.0.10: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.0.9: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.0.8: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.0.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.0.5: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-debian-x64-binaries)
* Среда выполнения .NET Core 1.0.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-debian-x64-binaries)
* Пакет SDK для .NET Core 1.1.10: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-debian-x64-binaries)
* Пакет SDK для .NET Core 1.1.9: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-debian-x64-binaries)
* Пакет SDK для .NET Core 1.1.8: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)
* Пакет SDK для .NET Core 1.1.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)
* Пакет SDK для .NET Core 1.1.5: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-debian-x64-binaries)
* Пакет SDK для .NET Core 1.1.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-debian-x64-binaries)
* Пакет SDK для .NET Core 1.0.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)
* Пакет SDK для .NET Core 1.0.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a>Установка .NET Core для поддерживаемых версий Fedora (64-разрядных)

Чтобы установить .NET Core в поддерживаемых версиях Fedora, выполните указанные ниже действия.

> [!NOTE]
> Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core 2.x в поддерживаемых версиях Fedora (64-разрядных).

**.NET Core 2.0**

|Среды выполнения и пакеты SDK          |Fedora 26 или более поздней версии |Fedora 25 или более ранней версии |
|-------------------------|-------------------|----------------------|
|Среда выполнения .NET Core 2.0.9  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.9)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.9)           |
|Среда выполнения .NET Core 2.0.8  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.8)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.8)           |
|Среда выполнения .NET Core 2.0.7  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.7)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.7)           |
|Среда выполнения .NET Core 2.0.6  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|Среда выполнения .NET Core 2.0.5  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|Среда выполнения .NET Core 2.0.3  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.3)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.3)           |
|Среда выполнения .NET Core 2.0.0  |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.0)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.0)           |
|Пакет SDK для .NET Core 2.1.200    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.200)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.200)           |
|Пакет SDK для .NET Core 2.1.105    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.105)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.105)           |
|Пакет SDK для .NET Core 2.1.103    |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|Пакет SDK для .NET Core 2.0.3      |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

**.NET Core 2.1**

>[!IMPORTANT]
> Чтобы использовать .NET Core 2.1 с Visual Studio, необходимо [установить Visual Studio 2017 15.7 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

|Среды выполнения и пакеты SDK                  |Fedora 28          |Fedora 27             |
|---------------------------------|-------------------|----------------------|
|Среда выполнения .NET Core 2.1.2          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.2)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.2)           |
|Пакет SDK для .NET Core 2.1.400          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.400)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.400)           |
|Пакет SDK для .NET Core 2.1.302          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.302)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.302)           |
|Среда выполнения .NET Core 2.1.1          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.1)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.1)           |
|Пакет SDK для .NET Core 2.1.301          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.301)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.301)           |
|Среда выполнения .NET Core 2.1.0          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.0)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0)           |
|Пакет SDK для .NET Core 2.1.300          |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.300)       |[Ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.300)           |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core 1.x в поддерживаемых версиях Fedora (64-разрядных).

**Fedora 24**

* Среда выполнения .NET Core 1.1.8: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-fedora-24-x64-binaries)
* Среда выполнения .NET Core 1.1.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)
* Среда выполнения .NET Core 1.1.6: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)
* Среда выполнения .NET Core 1.1.5: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-fedora-24-x64-binaries)
* Среда выполнения .NET Core 1.1.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-fedora-24-x64-binaries)
* Среда выполнения .NET Core 1.1.2: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-fedora-24-x64-binaries)
* Среда выполнения .NET Core 1.1.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-fedora-24-x64-binaries)
* Пакет SDK для .NET Core 1.1.9: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-fedora-24-x64-binaries)
* Пакет SDK для .NET Core 1.1.8: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)
* Пакет SDK для .NET Core 1.1.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)
* Пакет SDK для .NET Core 1.1.5: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5linux-fedora-24-x64-binaries)
* Пакет SDK для .NET Core 1.1.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5linux-fedora-24-x64-binaries)
* Пакет SDK для .NET Core 1.0.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

**Fedora 23**

* Среда выполнения .NET Core 1.1.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-fedora-23-x64-binaries)
* Среда выполнения .NET Core 1.1.2: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-fedora-23-x64-binaries)
* Среда выполнения .NET Core 1.1.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-fedora-23-x64-binaries)
* Среда выполнения .NET Core 1.0.9: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)
* Среда выполнения .NET Core 1.0.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-fedora-23-x64-binaries)
* Пакет SDK для .NET Core 1.1.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4linux-fedora-23-x64-binaries)
* Пакет SDK для .NET Core 1.1.2: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.2linux-fedora-23-x64-binaries)
* Пакет SDK для .NET Core 1.1.2: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.2linux-fedora-23-x64-binaries)
* Пакет SDK для .NET Core 1.0.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)
* Пакет SDK для .NET Core 1.0.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a>Установка .NET Core для поддерживаемых дистрибутивов и версий CentOS и Oracle Linux (64-разрядных)

Чтобы установить .NET Core для поддерживаемых дистрибутивов и версий CentOS и Oracle Linux (64-разрядных), выполните указанные ниже действия.

> [!NOTE]
> Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core 2.x в поддерживаемых дистрибутивах и версиях CentOS и Oracle Linux (64-разрядных).

**.NET Core 2.0**

* Среда выполнения .NET Core 2.0.9: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.9)
* Среда выполнения .NET Core 2.0.8: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.8)
* Среда выполнения .NET Core 2.0.7: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.7)
* Среда выполнения .NET Core 2.0.6: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)
* Среда выполнения .NET Core 2.0.5: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)
* Среда выполнения .NET Core 2.0.3: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.3)
* Среда выполнения .NET Core 2.0.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.0)
* Пакет SDK для .NET Core 2.1.202: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.202)
* Пакет SDK для .NET Core 2.1.201: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.201)
* Пакет SDK для .NET Core 2.1.200: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.200)
* Пакет SDK для .NET Core 2.1.105: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.105)
* Пакет SDK для .NET Core 2.1.104: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.104)
* Пакет SDK для .NET Core 2.1.103: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)
* Пакет SDK для .NET Core 2.1.102: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.102)
* Пакет SDK для .NET Core 2.0.3: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)
* Пакет SDK для .NET Core 2.0.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.0)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Чтобы использовать .NET Core 2.1 с Visual Studio, необходимо [установить Visual Studio 2017 15.7 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

* Среда выполнения .NET Core 2.1.2: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.2)
* Пакет SDK для .NET Core 2.1.400: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.400)
* Пакет SDK для .NET Core 2.1.302: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.302)
* Среда выполнения .NET Core 2.1.1: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.1)
* Пакет SDK для .NET Core 2.1.301: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.301)
* Среда выполнения .NET Core 2.1.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0)
* Пакет SDK для .NET Core 2.1.300: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core 1.x в поддерживаемых дистрибутивах и версиях CentOS и Oracle Linux (64-разрядных).

* Среда выполнения .NET Core 1.1.9: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.1.8: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.1.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.1.6: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.1.5: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.1.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.1.2: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.1.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.0.12: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.12-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.0.11: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.11-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.0.10: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.0.9: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.0.8: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.0.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.0.5: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-centos-x64-binaries)
* Среда выполнения .NET Core 1.0.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-centos-x64-binaries)
* Пакет SDK для .NET Core 1.1.10: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-centos-x64-binaries)
* Пакет SDK для .NET Core 1.1.9: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-centos-x64-binaries)
* Пакет SDK для .NET Core 1.1.8: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)
* Пакет SDK для .NET Core 1.1.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)
* Пакет SDK для .NET Core 1.1.5: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-centos-x64-binaries)
* Пакет SDK для .NET Core 1.1.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-centos-x64-binaries)
* Пакет SDK для .NET Core 1.0.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)
* Пакет SDK для .NET Core 1.0.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a>Установка .NET Core для поддерживаемых дистрибутивов и версий SUSE Linux Enterprise Server и OpenSUSE (64-разрядных)

Чтобы установить .NET Core для поддерживаемых дистрибутивов и версий SUSE Linux Enterprise Server и OpenSUSE (64-разрядных), выполните указанные ниже действия.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core 2.x в поддерживаемых дистрибутивах и версиях SUSE Linux Enterprise Server и OpenSUSE (64-разрядных).

**.NET Core 2.0**

**SUSE Linux Enterprise Server**

* Среда выполнения .NET Core 2.0.9: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.9)
* Среда выполнения .NET Core 2.0.8: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.8)
* Среда выполнения .NET Core 2.0.7: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.7)
* Среда выполнения .NET Core 2.0.6: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.6)
* Среда выполнения .NET Core 2.0.5: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.5)
* Среда выполнения .NET Core 2.0.3: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.3)
* Среда выполнения .NET Core 2.0.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.0)
* Пакет SDK для .NET Core 2.1.202: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.202)
* Пакет SDK для .NET Core 2.1.201: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.201)
* Пакет SDK для .NET Core 2.1.200: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.200)
* Пакет SDK для .NET Core 2.1.105: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.105)
* Пакет SDK для .NET Core 2.1.104: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.104)
* Пакет SDK для .NET Core 2.1.103: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.103)
* Пакет SDK для .NET Core 2.1.102: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.102)
* Пакет SDK для .NET Core 2.1.101: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.101)
* Пакет SDK для .NET Core 2.1.100: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.100)
* Пакет SDK для .NET Core 2.1.4: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.4)
* Пакет SDK для .NET Core 2.1.2: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.2)
* Пакет SDK для .NET Core 2.0.3: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.3)
* Пакет SDK для .NET Core 2.0.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.0)

**openSUSE**

* Среда выполнения .NET Core 2.0.9: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.9)
* Среда выполнения .NET Core 2.0.8: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.8)
* Среда выполнения .NET Core 2.0.7: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.7)
* Среда выполнения .NET Core 2.0.6: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)
* Среда выполнения .NET Core 2.0.5: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)
* Среда выполнения .NET Core 2.0.3: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.3)
* Среда выполнения .NET Core 2.0.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.0)
* Пакет SDK для .NET Core 2.1.202: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.202)
* Пакет SDK для .NET Core 2.1.201: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.201)
* Пакет SDK для .NET Core 2.1.200: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.200)
* Пакет SDK для .NET Core 2.1.105: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.105)
* Пакет SDK для .NET Core 2.1.103: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)
* Пакет SDK для .NET Core 2.1.102: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.102)
* Пакет SDK для .NET Core 2.1.101: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.101)
* Пакет SDK для .NET Core 2.1.100: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.100)
* Пакет SDK для .NET Core 2.1.4: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.4)
* Пакет SDK для .NET Core 2.1.2: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.2)
* Пакет SDK для .NET Core 2.0.3: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)
* Пакет SDK для .NET Core 2.0.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.0)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Чтобы использовать .NET Core 2.1 с Visual Studio, необходимо [установить Visual Studio 2017 15.7 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

**SUSE Linux Enterprise Server**

* Среда выполнения .NET Core 2.1.2: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.2)
* Пакет SDK для .NET Core 2.1.400: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.400)
* Пакет SDK для .NET Core 2.1.302: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.302)
* Среда выполнения .NET Core 2.1.1: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.1)
* Пакет SDK для .NET Core 2.1.301: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.301)
* Среда выполнения .NET Core 2.1.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0)
* Пакет SDK для .NET Core 2.1.300: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300)

**openSUSE**

* Среда выполнения .NET Core 2.1.2: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.2)
* Пакет SDK для .NET Core 2.1.400: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.400)
* Пакет SDK для .NET Core 2.1.302: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.302)
* Среда выполнения .NET Core 2.1.1: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.1)
* Пакет SDK для .NET Core 2.1.301: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.301)
* Среда выполнения .NET Core 2.1.0: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0)
* Пакет SDK для .NET Core 2.1.300: [ссылка для установки](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Установите .NET Core 1.x в поддерживаемых дистрибутивах и версиях SUSE Linux Enterprise Server и OpenSUSE (64-разрядных).

**SUSE Linux Enterprise Server 13.2**

* Среда выполнения .NET Core 1.1.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)
* Среда выполнения .NET Core 1.1.6: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)
* Пакет SDK для .NET Core 1.1.7: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)
* Пакет SDK для .NET Core 1.0.4: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-13.2-x64-binaries)
* Пакет SDK для .NET Core 1.0.1: [ссылка для установки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-13.2-x64-binaries)

---

## <a name="install-net-core-for-supported-alpine-linux-versions-64-bit"></a>Установка .NET Core для поддерживаемых версий Alpine Linux (64-разрядных)

> [!NOTE]
> Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.

Загрузите и выполните инструкции по установке .NET Core 2.1 для поддерживаемых версий Alpine Linux (64-разрядная версия) по следующим ссылкам:

* Среды выполнения .NET Core 2.1.2: [ссылка для загрузки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.2-linux-x64-alpine-binaries)
* Пакет SDK для .NET Core 2.1.400: [ссылка для загрузки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.400-linux-x64-alpine-binaries)
* Пакет SDK для .NET Core 2.1.302: [ссылка для загрузки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.302-linux-x64-alpine-binaries)
* Среды выполнения .NET Core 2.1.1: [ссылка для загрузки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.1-linux-x64-alpine-binaries)
* Пакет SDK для .NET Core 2.1.301: [ссылка для загрузки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.301-linux-x64-alpine-binaries)
* Среды выполнения .NET core 2.1.0: [ссылка для загрузки](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.0-linux-x64-alpine-binaries)
* Пакет SDK для .NET Core 2.1.300: [ссылка для загрузки](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.300-linux-x64-alpine-binaries)

> [!IMPORTANT]
> Если при установке .NET Core в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к статье для используемого дистрибутива и версии:
> * [Известные проблемы в .NET Core 2.1](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [Известные проблемы в .NET Core 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [Известные проблемы в .NET Core 1.1](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [Известные проблемы в .NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0)
