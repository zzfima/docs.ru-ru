---
title: Необходимые компоненты для .NET Core в Windows
description: Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows.
author: JRAlexander
ms.author: johalex
ms.date: 04/24/2018
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: ac898ea87c0247581154eb7de65e8cbe6ea6ba15
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
* Windows Server 2016 (полный сервер, основные серверные компоненты или сервер Nano)

Полный список операционных систем, поддерживаемых .NET Core 2.x, см. в статье [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).

Полный список операционных систем, поддерживаемых .NET Core 1.x, см. в статье [Версии ОС, поддерживаемые .NET Core 1.x](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).

## <a name="net-core-dependencies"></a>Зависимости .NET Core

Для работы .NET Core 1.1 и более ранних версий в версиях Windows, более ранних, чем Windows 10 и Windows Server 2016, требуется распространяемый пакет Visual C++. Эту зависимость автоматически устанавливает установщик .NET Core.

[Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685) необходимо установить вручную в следующих случаях:

* при установке .NET Core с помощью [скрипта установщика](./tools/dotnet-install-script.md);
* при развертывании автономного приложения .NET Core.
* сборка продукта из исходного кода;
* установка .NET Core из файла *.zip*, включая серверы сборки/непрерывной интеграции/непрерывного развертывания.

> [!NOTE]
> *Для Windows 8.1 и более ранних версий или Windows Server 2012 R2 и более ранних версий.* Убедитесь, что установка Windows находится в актуальном состоянии и содержит обновление [ KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), которое можно установить из Центра обновления Windows. Если это обновление не установлено, при запуске приложения .NET Core появится следующая ошибка: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.

## <a name="prerequisites-with-visual-studio-2017"></a>Необходимые компоненты для Visual Studio 2017

Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор. [Visual Studio 2017](#visual-studio-2017) предоставляет интегрированную среду разработки для приложений .NET Core в Windows.

Дополнительные сведения об обновлениях Visual Studio 2017 см. в [заметках о выпуске](/visualstudio/releasenotes/vs2017-relnotes).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Для разработки приложений .NET Core 2.x в Visual Studio 2017 выполните указанные ниже действия.

 1. [Скачайте и установите Visual Studio 2017 версии 15.3.0 или более поздней](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-15-3-workloads.jpg)

После установки набора инструментов **Кроссплатформенная разработка .NET Core** среда Visual Studio 2017 по умолчанию использует .NET Core 1.x. Чтобы в среде Visual Studio 2017 поддерживалась платформа .NET Core 2.x, установите пакет SDK для .NET Core 2.x.

 2. Установите [пакет SDK для .NET Core 2.x](https://www.microsoft.com/net/download/core).
 3. Перенацельте существующие или новые проекты .NET Core 1.x на .NET Core 2.x, выполнив приведенные ниже инструкции.
    * В меню **Проект** выберите пункт **Свойства**.
    * В меню **Целевая платформа** выберите значение **.NET Core 2.0**.

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.0" в меню целевой платформы](./media/windows-prerequisites/Targeting-dotnetCore2.png)

После установки пакета SDK для .NET Core 2.x среда Visual Studio 2017 по умолчанию использует пакет SDK для .NET Core 2.x и поддерживает следующие действия:

* открытие, сборка и запуск существующих проектов .NET Core 1.x;
* перенацеливание проектов .NET Core 1.x на .NET Core 2.x, сборка и запуск;
* создание проектов .NET Core 2.x.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Для разработки приложений .NET Core 1.x в Visual Studio [скачайте и установите Visual Studio 2017 RTM (версия 15.0.26228.4) или более позднюю версию](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> Для разработки приложений .NET Core 1.x можно использовать среду Visual Studio 2015, но делать этого не рекомендуется по указанным ниже причинам.
  > * Средства .NET Core доступны в виде предварительной версии, которая не поддерживается.
  > * Проекты основаны на файлах project.json, которые являются нерекомендуемыми.
>
> Дополнительные сведения об изменениях формата проектов см. в этом [обзоре](./tools/cli-msbuild-architecture.md).
---

> [!TIP]
> Чтобы проверить установленную версию Visual Studio 2017, выполните указанные ниже действия.
>
> * В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
> * В диалоговом окне **О программе Microsoft Visual Studio** проверьте номер версии.
>   * Для приложений .NET Core 2.1, предварительная версия 1 — Visual Studio 2017 версии 15.6, предварительная версия 6 или более поздняя.
>   * Для приложений .NET Core 2.0 — Visual Studio 2017 версии 15.3 или более поздняя версия.
>   * Для приложений .NET Core 1.x — Visual Studio 2017 версии 15.0 или более поздняя версия.
