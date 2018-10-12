---
title: Необходимые компоненты для .NET Core в Windows
description: Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows.
author: mairaw
ms.author: mairaw
ms.date: 08/31/2018
ms.openlocfilehash: 63c0de2b413f38458dba89506f4070760b3f53f8
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45747472"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Необходимые компоненты для .NET Core в Windows

В этой статье описываются зависимости, необходимые для разработки приложений .NET Core в Windows. Поддерживаемые версии ОС, а также перечисленные ниже зависимости относятся к трем способам разработки приложений .NET Core в Windows:

* [командная строка;](tutorials/using-with-xplat-cli.md)
* [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [Visual Studio Code.](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a>Версии Windows, поддерживаемые .NET Core

Платформа .NET Core поддерживается в следующих версиях:

* Windows 7 SP1
* Windows 8.1
* Windows 10, юбилейное обновление (версия 1607) или более поздние версии
* Windows Server 2008 R2 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)
* Windows Server 2012 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)
* Windows Server 2012 R2 (полный сервер или основные серверные компоненты)
* Windows Server 2016 или более поздних версий (полный вариант сервера, основные серверные компоненты или сервер Nano)

## <a name="net-core-supported-operating-systems"></a>Поддерживаемые операционные системы для .NET Core

В следующих статьях содержится полный список операционных систем с указанием версий, в которых поддерживается .NET Core:

* [.NET Core 2.1 - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1 — поддерживаемые версии ОС)
* [.NET Core 2.0 - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.0 — поддерживаемые версии ОС)
* [.NET Core 1.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x — поддерживаемые версии ОС)

## <a name="net-core-dependencies"></a>Зависимости .NET Core

Для работы .NET Core 1.1 и более ранних версий в версиях Windows, более ранних, чем Windows 10 и Windows Server 2016, требуется распространяемый пакет Visual C++. Эту зависимость автоматически устанавливает установщик .NET Core.

[Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685) необходимо установить вручную в следующих случаях:

* при установке .NET Core с помощью [скрипта установщика](./tools/dotnet-install-script.md);
* при развертывании автономного приложения .NET Core.
* сборка продукта из исходного кода;
* установка .NET Core из файла *.zip*, включая серверы сборки/непрерывной интеграции/непрерывного развертывания.

> [!NOTE]
> **Для Windows 8.1 и более ранних версий или Windows Server 2012 R2 и более ранних версий:**
>
> Убедитесь, что установленная версия Windows актуальна и содержит обновление [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), которое можно установить через Центр обновления Windows. Если это обновление не установлено, при запуске приложения .NET Core появится следующая ошибка: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`
>
> **Для Windows 7 или Windows Server 2008 R2:**
>
> Убедитесь, что помимо обновления KB2999226 также установлено обновление [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot). Если это обновление не установлено, при запуске приложения .NET Core появится примерно следующая ошибка: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-with-visual-studio-2017"></a>Необходимые компоненты для Visual Studio 2017

Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор. Visual Studio 2017 предоставляет интегрированную среду разработки для приложений .NET Core в Windows.

Дополнительные сведения об обновлениях Visual Studio 2017 см. в [заметках о выпуске](/visualstudio/releasenotes/vs2017-relnotes).

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

Для разработки приложений .NET Core 2.1 в Visual Studio 2017 выполните указанные ниже действия:

 1. [Скачайте и установите Visual Studio 2017 версии 15.7.0 или более поздней версии](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-15-8-workloads.jpg)

После установки набора инструментов **Кроссплатформенная разработка .NET Core** среда Visual Studio 2017 15.7 по умолчанию использует пакет SDK для .NET Core версии 2.0, а среда Visual Studio 2017 15.8 — пакет SDK для .NET Core версии 2.1.

 2. Если вы используете среду Visual Studio 2017 версии 15.7, установите [пакет SDK для .NET Core 2.1](https://www.microsoft.com/net/download/core) или обновите среду до Visual Studio 2017 версии 15.8.

 3. Перенацельте существующие или новые проекты .NET Core на .NET Core 2.1, выполнив приведенные ниже инструкции:
    * В меню **Проект** выберите пункт **Свойства**.
    * В меню **Целевая платформа** выберите значение **.NET Core 2.1**.

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.0" в меню целевой платформы](./media/windows-prerequisites/Targeting-dotnetCore2.png)

Настроив Visual Studio для работы с пакетом SDK для .NET Core 2.1, вы можете выполнять следующие действия:

* открытие, сборка и запуск существующих проектов .NET Core 1.x и 2.x;
* перенацеливание проектов .NET Core 1.x и 2.0 на .NET Core 2.1, сборка и запуск.
* создание проектов .NET Core 2.1.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

Для разработки приложений .NET Core 2.0 в Visual Studio 2017 выполните указанные ниже действия:

 1. [Скачайте и установите Visual Studio 2017 версии 15.3.0 или более поздней](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-15-3-workloads.jpg)

После установки набора инструментов **Кроссплатформенная разработка .NET Core** среда Visual Studio 2017 по умолчанию использует .NET Core 1.x. Чтобы в среде Visual Studio 2017 поддерживалась платформа .NET Core 2.0, установите пакет SDK для .NET Core 2.0.

 2. Установите [пакет SDK для .NET Core 2.0](https://www.microsoft.com/net/download/dotnet-core/2.0).
 3. Перенацельте существующие или новые проекты .NET Core 1.x на .NET Core 2.0, выполнив приведенные ниже инструкции:
    * В меню **Проект** выберите пункт **Свойства**.
    * В меню **Целевая платформа** выберите значение **.NET Core 2.0**.

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.0" в меню целевой платформы](./media/windows-prerequisites/Targeting-dotnetCore2.png)

После установки пакета SDK для .NET Core 2.0 среда Visual Studio 2017 по умолчанию использует пакет SDK для .NET Core 2.0 и поддерживает следующие действия:

* открытие, сборка и запуск существующих проектов .NET Core 1.x;
* перенацеливание проектов .NET Core 1.x на .NET Core 2.0, сборка и запуск;
* создание проектов .NET Core 2.0.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Для разработки приложений .NET Core 1.x в Visual Studio [скачайте и установите Visual Studio 2017](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> Для разработки приложений .NET Core 1.x можно использовать среду Visual Studio 2015, но делать этого не рекомендуется по указанным ниже причинам.
  > * Средства .NET Core доступны в виде предварительной версии, которая не поддерживается.
  > * Проекты основаны на файлах project.json, которые являются нерекомендуемыми.
>
> Дополнительные сведения об изменениях формата проектов см. в этом [обзоре](./tools/cli-msbuild-architecture.md).
---

<a name="vs-mapping"></a>

> [!TIP]
> Чтобы проверить установленную версию Visual Studio 2017, выполните указанные ниже действия.
>
> * В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
> * В диалоговом окне **О программе Microsoft Visual Studio** проверьте номер версии.
>   * Для приложений .NET Core 2.2, предварительная версия 1 — Visual Studio 2017 версии 15.9 (предварительная версия) или более поздней версии.
>   * Для приложений .NET Core 2.1 — Visual Studio 2017 версии 15.7 или более поздней версии.
>   * Для приложений .NET Core 2.0 — Visual Studio 2017 версии 15.3 или более поздняя версия.
>   * Для приложений .NET Core 1.x — Visual Studio 2017 версии 15.0 или более поздняя версия.
