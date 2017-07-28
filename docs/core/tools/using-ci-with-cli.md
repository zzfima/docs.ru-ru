---
title: "Использование пакета SDK и инструментов .NET Core при непрерывной интеграции (CI) | Microsoft Docs"
description: "Сведения об использовании пакета SDK для .NET Core и входящих в него средств на сервере сборки."
keywords: ".NET, .NET Core, непрерывная интеграция, ci, сборка, автоматизация, Travis CI, AppVeyor, Visual Studio Team Services, vsts"
author: guardrex
ms.author: mairaw
ms.date: 05/18/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0d6e1e34-277c-4aaf-9880-3ebf81023857
ms.translationtype: Human Translation
ms.sourcegitcommit: 5af11b469f906b7c074f127704eb338a78a62b34
ms.openlocfilehash: a13f6b80248a659bda23baece3638e33a166b5df
ms.contentlocale: ru-ru
ms.lasthandoff: 05/31/2017

---

# Использование пакета SDK и средств .NET Core при непрерывной интеграции (CI)
<a id="using-net-core-sdk-and-tools-in-continuous-integration-ci" class="xliff"></a>

## Обзор
<a id="overview" class="xliff"></a>

В этой статье описывается использование пакета SDK для .NET Core и входящих в него средств на сервере сборки. Набор инструментов .NET Core поддерживает два режима: интерактивный (разработчик вводит команды в командной строке) и автоматический (сервер непрерывной интеграции выполняет скрипт сборки). Команды, параметры, входные и выходные данные совпадают. В этом случае нужно только указать способ получения средств и систему сборки приложения. В этом документе рассматриваются сценарии ввода в эксплуатацию средства обеспечения непрерывной интеграции, а также рекомендации по разработке и структуре скриптов сборки.

## Варианты установки для серверов сборки CI
<a id="installation-options-for-ci-build-servers" class="xliff"></a>

### Использование собственных установщиков
<a id="using-the-native-installers" class="xliff"></a>

В macOS, Linux и Windows доступны собственные установщики. Установщики требуют доступа администратора (sudo) к серверу сборки. Преимущество использования собственного установщика заключается в том, что он устанавливает собственные зависимости, необходимые для выполнения средства. Кроме того, собственные установщики обеспечивают системную установку пакета SDK.

Пользователи macOS должны использовать установщики PKG. В случае с Linux можно выбрать диспетчер пакетов на основе каналов, например apt-get для Ubuntu или yum для CentOS. Кроме того, можно использовать сами пакеты (DEB или RPM). Для платформ Windows можно использовать установщик MSI.

Последние надежные двоичные файлы можно найти на странице, посвященной [началу работы с .NET Core](https://aka.ms/dotnetcoregs). Чтобы использовать последние (возможно, ненадежные) предварительные выпуски средств, воспользуйтесь ссылками в [репозитории GitHub](https://github.com/dotnet/cli#installers-and-binaries). Для дистрибутивов Linux также доступны архивы `tar.gz` (`tarballs`). Используйте вложенные в них скрипты, чтобы установить .NET Core.

### Использование скрипта установки
<a id="using-the-installer-script" class="xliff"></a>

Скрипт установки позволяет выполнять установку на сервере сборки без прав администратора. Кроме того, с его помощью очень легко обеспечить автоматизацию. Скрипт самостоятельно скачивает средство и распаковывает его в стандартную или указанную папку. Вы также можете указать версию средства, которую следует установить, а также нужно ли установить пакет SDK целиком или только общую среду выполнения.

Работу скрипта установки можно автоматизировать в начале процесса сборки. Это позволяет получить и установить требуемую версию пакета SDK. *Требуемая версия* — это версия пакета SDK, необходимая в проектах для сборки. Этот скрипт позволяет установить пакет SDK в локальном каталоге на сервере, запустить средства из папки установки, а затем выполнить очистку после завершения сборки (очистку также может выполнить сервер непрерывной интеграции). Это обеспечивает инкапсуляцию и изоляцию процесса сборки. Ссылку на скрипт установки можно найти в справке по [dotnet-install](dotnet-install-script.md).

> [!NOTE]
> При использовании скрипта установки собственные зависимости не устанавливаются автоматически. Их необходимо установить вручную, если их нет в операционной системе. Список предварительных требований см. в [этом репозитории GitHub](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

## Примеры установки решений CI
<a id="ci-setup-examples" class="xliff"></a>

В этом разделе приведены сведения о ручной настройке с помощью скрипта PowerShell или bash, а также описано несколько решений SaaS для непрерывной интеграции, таких как [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) и [Visual Studio Team Services](https://www.visualstudio.com/docs/build/overview).

### Ручная настройка
<a id="manual-setup" class="xliff"></a>

Каждая служба SaaS имеет собственные методы создания и настройки процесса сборки. Если вы используете другое решения SaaS, нежели упомянутые выше, или хотите внести дополнительные изменения, конфигурацию необходимо выполнить вручную.

Как правило, в процессе ручной настройки необходимо получить версию средства (или последнюю сборку) и выполнить скрипт сборки. Вы можете использовать скрипт PowerShell или bash, чтобы настроить команды .NET Core, а также файл проекта, который определяет процесс сборки. Подробные сведения об этих параметрах см. в разделе [Оркестрация сборки](#orchestrating-the-build).

После создания сценария, выполняющего ручную настройку сервера сборки CI, проверьте его на локальном компьютере разработки. Если проблем со скриптом не возникло, разверните его на сервере сборки CI. Ниже приведен относительно простой сценарий PowerShell, позволяющий получить пакет SDK для .NET Core и установить его на сервере сборки Windows.

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the 
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the 
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it 
#   does, it's removed. This is not strictly required, but it's a 
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the 
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://raw.githubusercontent.com/dotnet/cli/rel/1.0.1/scripts/obtain/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the 
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the 
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

Сведения о реализации процесса сборки следует указать в конце скрипта. Скрипт получает средства, а затем выполняет процесс сборки. Ниже приведен скрипт bash, который выполняет те же действия, что и описанный выше сценарий PowerShell, он выполняется на компьютерах UNIX.

```bash
#!/bin/bash
# Do not use an INSTALLDIR path containing spaces:
#   https://github.com/dotnet/cli/issues/5281
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://raw.githubusercontent.com/dotnet/cli/rel/1.0.1/scripts/obtain/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### Travis CI
<a id="travis-ci" class="xliff"></a>

Средство [Travis CI](https://travis-ci.org/) можно настроить, чтобы установить пакет SDK для .NET Core с помощью языка `csharp` и ключа `dotnet`. Дополнительные сведения см. в официальной документации Travis CI по [созданию проектов C#, F# или Visual Basic](https://docs.travis-ci.com/user/languages/csharp/). Обратите внимание, что при доступе к сведениям сообщества Travis CI идентификатор языка `language: csharp` работает для всех языков .NET, в том числе F# и Mono.

Travis CI выполняет в *матрице сборки* как задания macOS (OS X 10.11, OS X 10.12), так и задания Linux (Ubuntu 14.04). Вы можете указать сочетание среды выполнения, окружения, а также исключений и включений, чтобы охватить свои сочетания сборки приложения. Дополнительные сведения см. в [примере .travis.yml](https://github.com/dotnet/docs/blob/master/.travis.yml) и статье о [настройке сборки](https://docs.travis-ci.com/user/customizing-the-build) в документации по Travis CI. Средства на основе MSBuild включают среды выполнения LTS (1.0.x) и текущие среды выполнения (1.1.x). Установив этот пакет SDK, вы получите все необходимые компоненты сборки.

### AppVeyor
<a id="appveyor" class="xliff"></a>

Средство [AppVeyor](https://www.appveyor.com/) устанавливает рабочий образ сборки `Visual Studio 2017` с пакетом SDK для .NET Core 1.0.1. Но также доступны и другие образы сборки с разными версиями пакета SDK для .NET Core. Дополнительные сведения см. в [примере appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) и [разделе о рабочих образах сборки](https://www.appveyor.com/docs/build-environment/#build-worker-images) в документации по AppVeyor.

Двоичные файлы пакета SDK для .NET Core загружаются в подкаталог и распаковываются в нем с помощью скрипта установки. Затем они добавляются в переменную среды `PATH`. Добавьте матрицу сборки, чтобы выполнить тесты интеграции с разными версиями пакета SDK для .NET Core:

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### Visual Studio Team Services (VSTS)
<a id="visual-studio-team-services-vsts" class="xliff"></a>

Настройте Visual Studio Team Services, чтобы создать проекты .NET Core, используя один из следующих подходов:

1. Выполнение скрипта из раздела [Ручная настройка](#manual-setup) с использованием собственных команд.
1. Создание сборки, состоящей из нескольких встроенных задач сборки VSTS, которые используют средства .NET Core.

Оба решения допустимые. С помощью скрипта ручной настройки можно управлять версиями средства, полученными в процессе сборки. Сборка выполняется с помощью скрипта, который необходимо создать. В этом разделе описывается только создание вручную. Дополнительные сведения о создании сборки с помощью задач сборки VSTS см. в статье [Непрерывная интеграция и развертывание](https://www.visualstudio.com/docs/build/overview).

Чтобы использовать скрипт ручной настройки в VSTS, создайте определение сборки и укажите скрипт, выполняющий этап сборки. Это можно сделать с помощью пользовательского интерфейса VSTS:

1. Сначала создайте определение сборки. Когда появится окно определения типа создаваемой сборки, выберите параметр **Пусто**.

   ![Выбор пустого определения сборки](./media/using-ci-with-cli/screen1.png)

1. После настройки репозитория сборки откроется окно "Определения сборок". Выберите **Добавить шаг сборки**:

   ![Добавление шага сборки](./media/using-ci-with-cli/screen2.png)

1. После этого откроется **каталог задач**. В нем содержатся задачи, используемые в сборке. Так как у вас есть скрипт, нажмите кнопку **Добавить** рядом с параметром **PowerShell: Запуск скрипта PowerShell**.

   ![Добавление этапа сценария PowerShell](./media/using-ci-with-cli/screen3.png)

1. Настройте сервер сборки. Добавьте скрипт из репозитория, для которого выполняется сборка:

   ![Указание выполняемого сценария PowerShell](./media/using-ci-with-cli/screen4.png)

## Оркестрация сборки
<a id="orchestrating-the-build" class="xliff"></a>

Большая часть статьи посвящена тому, как получить средства .NET Core и настроить различные службы CI. Оркестрация или *фактическое создание* кода с помощью .NET Core до этого момента не упоминались. Способ структурирования процесса сборки зависит от многих факторов, которые нельзя здесь описать в общем виде. Дополнительные сведения об оркестрации сборок на основе каждой упомянутой в этой статье технологии, а также ресурсы и примеры см. в документации по [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) и [VSTS](https://www.visualstudio.com/docs/build/overview).

Два принципиальных подхода структурирования процесса сборки кода .NET Core с использованием средств .NET Core заключаются в использовании MSBuild напрямую или с помощью программ командной строки .NET Core. Выберите подход, который проще и удобнее для вас. MSBuild предоставляет возможность представить процесс сборки в виде задач и целевых объектов, но сложность этого подхода заключается в необходимости изучения синтаксиса файла проекта MSBuild. Подход с использованием программ командной строки .NET Core, возможно, проще, но в этом случае следует написать логику оркестрации на языке написания скриптов, например `bash` или PowerShell.

## См. также
<a id="see-also" class="xliff"></a>

[Начало работы с .NET Core](https://www.microsoft.com/net/core#linuxubuntu)   

