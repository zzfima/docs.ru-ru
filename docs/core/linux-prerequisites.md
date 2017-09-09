---
title: "Необходимые компоненты для .NET Core в Linux"
description: "Поддерживаемые версии Linux и зависимости .NET Core для разработки, развертывания и запуска приложений .NET Core на компьютерах с Linux."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 7bbb8405f39a52d2798fd1dbc78f3116cb3bedbb
ms.openlocfilehash: 9864ffa31caa007cb649a9e6e8913863d9cb2c35
ms.contentlocale: ru-ru
ms.lasthandoff: 09/05/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a>Необходимые компоненты для .NET Core в Linux

В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Linux. Поддерживаемые дистрибутивы и версии Linux, а также перечисленные ниже зависимости относятся к двум способам разработки приложений .NET Core в Linux:

* [командная строка и любой редактор;](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code.](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>Поддерживаемые версии Linux

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.0 воспринимает Linux как отдельную операционную систему. Существует отдельная сборка для Linux (на основе архитектуры микросхемы) с поддержкой дистрибутивов Linux.

.NET Core 2.x поддерживается в следующих дистрибутивах и версиях 64-разрядной Linux:

 * Red Hat Enterprise Linux 7
 * CentOS 7
 * Oracle Linux 7
 * Fedora 25, Fedora 26
 * Debian 8.7 или более поздней версии 
 * Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04
 * Linux Mint 18, Linux Mint 17
 * openSUSE 42.2 или более поздней версии
 * SUSE Enterprise Linux (SLES) 12 с пакетом обновления 2 (SP2) или более поздней версии

Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x поддерживается в следующих дистрибутивах и версиях 64-разрядной Linux:

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 24
* Debian 8.2 или более поздней версии
* Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*
 * Ubuntu 16.10 поддерживается последним выпуском исправлений для .NET Core 1.1
* Linux Mint 17
* openSUSE 42.1 или более поздней версии (.NET Core 1.1)

Полный список операционных систем, поддерживаемых .NET Core 1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).

---

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

Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Установка зависимостей .NET Core с помощью собственных установщиков

Для поддерживаемых дистрибутивов и версий Linux доступны собственные установщики .NET Core. Собственные установщики требуют доступа администратора (sudo) к серверу. Преимущество использования собственного установщика заключается в том, что он устанавливает все собственные зависимости .NET Core. Собственные установщики также устанавливают пакет SDK для .NET Core в масштабе всей системы.

В Linux есть два варианта выбора пакета установщика:

* диспетчер пакетов на основе веб-канала, например apt-get для Ubuntu или yum для CentOS/RHEL;
* сами пакеты (DEB или RPM).

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Установка с помощью скрипта установщика .NET Core

Скрипты `dotnet-install` служат для установки цепочки инструментов CLI и общей среды выполнения без прав администратора. Скачать скрипты можно в [репозитории CLI GitHub](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).

Скрипт bash установщика используется в сценариях автоматизации и установки без прав администратора. Скрипт также считывает параметры PowerShell, чтобы их можно было использовать с этим скриптом в системах Linux и OS X.

> [!IMPORTANT]
> Перед запуском скрипта установите все необходимые [зависимости](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a>Установка .NET Core для Red Hat Enterprise Linux (RHEL) 7

Установка .NET Core в RHEL 7

1. Включите канал Red Hat .NET, доступный в рамках подписки на RHEL 7.
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
    
3. Установка .NET Core

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Установка пакета SDK для .NET Core 2.0 и среды выполнения

   ```bash
   yum install rh-dotnet20
   ```

Включите пакет SDK для .NET Core 2.0 или среду выполнения для своего окружения.

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

Установка пакета SDK для .NET Core 1.1 и среды выполнения

   ```bash
   yum install rh-dotnetcore11
   ```

Включите пакет SDK для .NET Core 1.1 или среду выполнения для своего окружения.

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

**.NET Core 1.0**

Установка пакета SDK для .NET Core 1.0 и среды выполнения

   ```bash
   yum install rh-dotnetcore10
   ```

Включите пакет SDK для .NET Core 1.0 или среду выполнения для своего окружения.

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.

     ```bash
     dotnet --version
     ```

Справку по регистрации для доступа к каналу Red Hat .NET см. в [главе 1 руководства по началу работы с .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) на сайте Red Hat.

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a>Установка .NET Core для Ubuntu 14.04, 16.04, 16.10 и Linux Mint 17 и 18 (64-разрядная версия)

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Зарегистрируйте ключ продукта Майкрософт как доверенный.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. Установите веб-канал пакета узла требуемой версии.

   **Ubuntu 17.04**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 16.04 и Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 14.04 и Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. Установите .NET Core.

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Установите веб-канал пакета узла требуемой версии.

   **Ubuntu 16.10**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  **Ubuntu 16.04 и Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   **Ubuntu 14.04 и Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. Установите .NET Core 1.x на Ubuntu или Linux Mint.

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a>Установка .NET Core для Debian 8 или Debian 9 (64-разрядной версии)

Чтобы установить .NET Core на Debian 8 или Debian 9 (64-разрядной версии), сделайте следующее:

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

> [!NOTE]
> Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Установите системные компоненты.

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. Зарегистрируйте доверенный ключ продукта корпорации Майкрософт.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. Зарегистрируйте канал продукта корпорации Майкрософт.

   **Debian 9 (Stretch)**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   **Debian 8 (Jessie)**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. Извлеките двоичные файлы пакета SDK для .NET Core.

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. Добавьте каталог dotnet в PATH.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Получите необходимые компоненты.

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. Скачайте двоичные файлы пакета SDK для .NET Core (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. Извлеките двоичные файлы пакета SDK для .NET Core.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Добавьте каталог dotnet в PATH.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a>Установка .NET Core на Fedora 24, Fedora 25 или Fedora 26 (64-разрядная версия)

Чтобы установить .NET Core на Fedora 26, Fedora 25 (.NET Core 2.x) или Fedora 24 (.NET Core 1.x), сделайте следующее:

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

> [!NOTE]
> Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 или Fedora 25**

2. Зарегистрируйте ключ сигнатуры Майкрософт.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Добавьте канал продукта dotnet.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. Установите пакет SDK для .NET Core.

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. Добавьте каталог dotnet в PATH.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

2. Получите необходимые компоненты.

   ```bash
   sudo dnf install libunwind libicu
   ```

3. Скачайте двоичный файл пакета SDK для .NET Core (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. Извлеките двоичные файлы пакета SDK для .NET Core.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Добавьте каталог dotnet в PATH.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>Установка .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии)

Чтобы установить .NET Core для CentOS 7.1 (64-разрядной версии) и Oracle Linux 7.1 (64-разрядной версии), выполните указанные ниже действия.

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

> [!NOTE]
> Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Зарегистрируйте ключ сигнатуры Майкрософт.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Добавьте канал продукта Майкрософт.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. Установите пакет SDK для .NET Core.

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. Добавьте каталог dotnet в переменную PATH.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Получите необходимые компоненты.

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. Скачайте двоичный файл пакета SDK для .NET Core (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. Извлеките двоичные файлы пакета SDK для .NET Core.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Добавьте каталог dotnet в PATH.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a>Установка .NET Core для SUSE Linux Enterprise Server (64-разрядной версии)

Чтобы установить .NET Core 2.x для SUSE Linux Enterprise Server (SLES) 12 с пакетом обновления 2 (64-разрядной версии), сделайте следующее:

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

2. Добавьте канал продукта dotnet.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. Установите пакет SDK для .NET Core.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. Добавьте каталог dotnet в PATH.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a>Установка .NET Core для openSUSE (64-разрядной версии)

Чтобы установить .NET Core 2.x для openSUSE или .NET Core 1.x для openSUSE (64-разрядная версия), сделайте следующее:

1. Удалите из системы все **предыдущие предварительные** версии .NET Core.

> [!NOTE]
> Чтобы установить систему Linux из архива TAR.GZ, требуется пользовательский каталог.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Зарегистрируйте ключ сигнатуры Майкрософт.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Добавьте канал продукта dotnet.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. Установите пакет SDK для .NET Core.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. Добавьте каталог dotnet в PATH.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Получите необходимые компоненты.

   ```bash
   sudo zypper install libunwind libicu
   ```

3. Скачайте двоичный файл пакета SDK для .NET Core (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. Извлеките двоичные файлы пакета SDK для .NET Core.
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Добавьте каталог dotnet в PATH.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. Чтобы проверить, успешно ли завершилась установка, выполните команду `dotnet --version`.

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> Если при установке .NET Core 2.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделу с описанием [известных проблем в версии 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) для используемого дистрибутива и версии. 
>
> Если при установке .NET Core 1.x в поддерживаемом дистрибутиве и версии Linux возникают проблемы, обратитесь к разделам с описанием [известных проблем в версии 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) и [версии 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) для используемого дистрибутива и версии.

