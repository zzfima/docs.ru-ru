---
title: "Необходимые компоненты для .NET Core в Linux"
description: "Поддерживаемые версии Linux и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с Linux."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: johalex
ms.author: johalex
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: dd1557d3a43a13c8103c82dfa467aa889fcf3bbb
ms.openlocfilehash: 2ee303424721b7e1ecb8473c5f957ca929a8742f
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a>Необходимые компоненты для .NET Core в Linux

В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Linux. Поддерживаемые дистрибутивы и версии Linux, а также перечисленные ниже зависимости относятся к двум способам разработки приложений .NET Core в Linux:

* [командная строка;](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code.](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>Поддерживаемые версии Linux

.NET Core 2.x поддерживается в следующих дистрибутивах и версиях Linux:

 * Red Hat Enterprise Linux 7 (64-разрядная версия)
 * CentOS 7 (64-разрядная версия)
 * Oracle Linux 7 (64-разрядная версия)
 * Fedora 25, 26 (64-разрядные версии)
 * Debian 9, 8.7+ (64-разрядные версии) 
 * Ubuntu 17.04, 16.04, 14.04 (64-разрядные версии)
 * Linux Mint 18, 17 (64-разрядные версии)
 * openSUSE 42.2 или более поздние версии (64-разрядные)
 * SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздние версии (64-разрядные)

.NET Core 1.x поддерживается в следующих дистрибутивах и версиях Linux:

* Red Hat Enterprise Linux, CentOS, Oracle Linux 7 (64-разрядные версии)
* Fedora 24 (64-разрядная версия)
* Debian 8.2 и более поздние версии (64-разрядные)
* Ubuntu, Linux Mint 14.04, 16.04, 16.10 *, 17 (64-разрядные версии)
* openSUSE 42.1 (1.1) (64-разрядная версия)
> [!NOTE]
> Ubuntu и Linux 16.10 поддерживаются последним выпуском исправлений для .NET Core 1.1

Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).

Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).
## <a name="linux-distribution-dependencies"></a>Зависимости дистрибутивов Linux
### <a name="ubuntu"></a>Ubuntu
Для дистрибутивов Ubuntu должны быть установлены следующие библиотеки:

* libunwind8
* libunwind8-dev
* gettext
* libicu-dev
* liblttng-ust-dev
* libcurl4-openssl-dev
* libssl-dev
* uuid-dev
* unzip

### <a name="centos"></a>CentOS
Для дистрибутивов CentOS должны быть установлены следующие библиотеки:
* deltarpm
* epel-release
* unzip
* libunwind
* gettext
* libcurl-devel
* openssl-devel
* zlib
* libicu-devel

## <a name="installing-net-core-prerequisites-with-the-native-installers"></a>Установка необходимых компонентов для .NET Core с помощью собственных установщиков

Для поддерживаемых дистрибутивов и версий Linux доступны собственные установщики .NET Core. Собственные установщики требуют доступа администратора (sudo) к серверу. Преимущество использования собственного установщика заключается в том, что он устанавливает все собственные зависимости .NET Core. Собственные установщики также устанавливают пакет SDK для .NET Core в масштабе всей системы.

В Linux есть два варианта выбора пакета установщика: 
* диспетчер пакетов на основе веб-канала, например apt-get для Ubuntu или yum для CentOS; 
* сами пакеты (DEB или RPM). 

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Установка с помощью скрипта установщика .NET Core 

Скрипты `dotnet-install` служат для установки цепочки инструментов CLI и общей среды выполнения без прав администратора. Скачать скрипты можно в [репозитории CLI GitHub](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain). 

Скрипт bash установщика используется в сценариях автоматизации и установки без прав администратора. Скрипт также считывает параметры PowerShell, чтобы их можно было использовать с этим скриптом в системах Linux и OS X.

> [!IMPORTANT]
> Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

## <a name="install-net-core-dependencies-for-red-hat-enterprise-linux-rhel-7-server"></a>Установка зависимостей .NET Core для Red Hat Enterprise Linux (RHEL) 7 Server

> [!Warning]
> Перед тем как начать, удалите из системы все предыдущие версии .NET Core.

### <a name="verify-and-enable-the-net-channel-for-rhel-7-server"></a>Проверка и включение канала .NET для RHEL 7 Server
Чтобы установить зависимости .NET Core в RHEL Server, выполните указанные ниже действия.

1. Включите канал Red Hat .NET, доступный в рамках подписки на RHEL 7 Server. 
    * Для Red Hat Enterprise 7 Server используйте следующую команду:
         ```bash
        subscription-manager repos --enable=rhel-7-server-dotnet-rpms
        ```
    * Для Red Hat Enterprise 7 Workstation используйте следующую команду:
         ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
        ```
    * For Red Hat Enterprise 7 HPC Compute Node используйте следующую команду:
         ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. Установите средство scl.
    ```bash
    yum install scl-utils
    ```
3. Установите .NET Core 1.1 (и все зависимости).
    ```bash
    yum install rh-dotnetcore11
    scl enable rh-dotnetcore11 bash
    ```
4. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --help`.

     ```bash
     dotnet --help
     ```
> [!NOTE]
> Справку по регистрации для доступа к каналу Red Hat .NET см. в [главе 1 руководства по началу работы с .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) на сайте Red Hat.


## <a name="install-net-core-for-ubuntu-1404-1604-1610--linux-mint-17-18-64-bit"></a>Установка .NET Core для Ubuntu 14.04, 16.04, 16.10 и Linux Mint 17, 18 (64-разрядные версии)

> [!Warning]
> Перед тем как начать, удалите из системы все предыдущие версии .NET Core.

### <a name="add-the-dotnet-apt-get-feed"></a>Добавление веб-канала dotnet apt-get

1. Установите веб-канал пакета узла требуемой версии.

   **Ubuntu 14.04 и Linux Mint 17**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
    **Ubuntu 16.04 и Linux Mint 18**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
    **Ubuntu 16.10**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
2. Установите .NET Core.
# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

После установки веб-канала пакета узла установите .NET Core 2.0 в Ubuntu или Linux Mint.
```bash
sudo apt-get install dotnet-sdk-2.0.0
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

После установки веб-канала пакета узла установите .NET Core 1.x в Ubuntu или Linux Mint.
```bash
sudo apt-get install dotnet-dev-1.0.4
```
---
3. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --help`.

 ```bash
     dotnet --help
 ```
## <a name="install-net-core-for-debian-8-or-9-64-bit"></a>Установка .NET Core для Debian 8 или 9 (64-разрядной версии)

> [!Warning]
> Перед тем как начать, удалите из системы все предыдущие версии .NET Core.

Чтобы установить .NET Core в Debian 8 или 9 (64-разрядной версии), выполните указанные ниже действия.
1. Получите необходимые компоненты. 
    ```bash
    sudo apt-get install curl libunwind8 gettext
    ```
2. Скачайте двоичные файлы пакета SDK для .NET Core (tarball).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)   

```bash
     curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)   

```bash
     curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
```
---
3. Извлеките двоичные файлы пакета SDK для .NET Core.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Добавьте каталог dotnet в PATH.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --help`.

     ```bash
     dotnet --help
     ```

## <a name="install-net-core-for-fedora-24-25-or-26-64-bit"></a>Установка .NET Core для Fedora 24, 25 или 26 (64-разрядной версии)

> [!Warning]
> Перед тем как начать, удалите из системы все предыдущие версии .NET Core.

Чтобы установить .NET Core для Fedora 26, 25(.NET Core 2.x) или 24 (.NET Core 1.x), выполните указанные ниже действия. 
1. Получите необходимые компоненты. 
    ```bash
    sudo dnf install libunwind libicu
    ```
2. Скачайте двоичный файл пакета SDK для .NET Core (tarball).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 или 25**

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
```

---
3. Извлеките двоичные файлы пакета SDK для .NET Core.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Добавьте каталог dotnet в PATH.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --help`.

     ```bash
     dotnet --help
     ```
## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>Установка .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии)

> [!Warning]
> Перед тем как начать, удалите из системы все предыдущие версии .NET Core.

Чтобы установить .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии), выполните указанные ниже действия.

1. Получите необходимые компоненты.
    ```bash
    sudo dnf install libunwind libicu
    ```
2. Скачайте двоичный файл пакета SDK для .NET Core (tarball).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
```

---
3. Извлеките двоичные файлы пакета SDK для .NET Core.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Добавьте каталог dotnet в PATH.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --help`.

     ```bash
     dotnet --help
     ```
## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit-net-core-2x-and-opensuse-64-bit"></a>Установка .NET Core для SUSE Linux Enterprise Server (64-разрядной версии) (.NET Core 2.x) и openSUSE (64-разрядной версии)

> [!Warning]
> Перед тем как начать, удалите из системы все предыдущие версии .NET Core.

Чтобы установить .NET Core для SUSE Linux Enterprise Server (SLES) 12 с пакетом обновления 2 (SP2) (64-разрядной версии) и openSUSE 42.2 в NET Core 2.x или openSUSE 42.1 (64-разрядной версии) в .NET Core 1.x, выполните указанные ниже действия.

1. Получите необходимые компоненты.
    ```bash
    sudo zypper install libunwind libicu
    ```
2. Скачайте двоичный файл пакета SDK для .NET Core (tarball).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**SLES 12 SP2, openSUSE 42.2**

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**openSUSE 42.1**

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
```

---
3. Извлеките двоичные файлы пакета SDK для .NET Core.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Добавьте каталог dotnet в PATH.
    ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --help`.

     ```bash
     dotnet --help
     ```

> [!IMPORTANT]
> Если при установке .NET Core 2.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделу с описанием [известных проблем в версии 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) для используемого дистрибутива и версии.
> [!IMPORTANT]
> Если при установке .NET Core 1.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделам с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) для используемого дистрибутива и версии.
