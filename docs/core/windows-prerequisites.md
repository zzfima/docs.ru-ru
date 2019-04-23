---
title: Необходимые компоненты для .NET Core в Windows
description: Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows.
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 2941721dfa4b87d4113e4f4b529845e47f3dc1b9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313714"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Необходимые компоненты для .NET Core в Windows

В этой статье описываются поддерживаемые версии ОС, необходимые для запуска приложений .NET Core в Windows. Поддерживаемые версии ОС, а также перечисленные ниже зависимости относятся к трем способам разработки приложений .NET Core в Windows:

* [Командная строка](tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [Visual Studio Code](https://code.visualstudio.com/)

Кроме того, если вы разрабатываете приложение в Windows с помощью Visual Studio 2017, ознакомьтесь с минимальными поддерживаемыми версиями для разработки .NET Core в разделе [Необходимые компоненты для Visual Studio 2017](#prerequisites-with-visual-studio-2017).

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

* [.NET Core 3.0 (предварительная версия)](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [.NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

Дополнительные сведения и ссылки для скачивания см. на следующих страницах: [на странице скачиваемых файлов .NET](https://dotnet.microsoft.com/download) для загрузки новой версии и [на странице архива загрузок .NET](https://dotnet.microsoft.com/download/archives#dotnet-core) для более старых версий.

## <a name="net-core-dependencies"></a>Зависимости .NET Core

Для работы .NET Core 1.1 и более ранних версий в версиях Windows, более ранних, чем Windows 10 и Windows Server 2016, требуется распространяемый пакет Visual C++. Эту зависимость автоматически устанавливает установщик .NET Core.

[Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685) необходимо установить вручную в следующих случаях:

* при установке .NET Core с помощью [скрипта установщика](./tools/dotnet-install-script.md);
* при развертывании автономного приложения .NET Core.
* сборка продукта из исходного кода;
* установка .NET Core из файла *.zip*, включая серверы сборки/непрерывной интеграции/непрерывного развертывания.

> [!NOTE]
> **Для Windows 8.1 и более ранних версий или Windows Server 2012 R2 и более ранних версий:**
>
> Убедитесь, что установленная версия Windows актуальна и содержит обновление [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), которое можно установить через Центр обновления Windows. Если это обновление не установлено, при запуске приложения .NET Core появится следующая ошибка: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`
>
> **Для Windows 7 или Windows Server 2008 R2:**
>
> Убедитесь, что помимо обновления KB2999226 также установлено обновление [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot). Если это обновление не установлено, при запуске приложения .NET Core появится примерно следующая ошибка: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-for-net-core-30-preview-3"></a>Необходимые компоненты для .NET Core 3.0 (предварительная версия 3)

Необходимые компоненты для .NET Core 3.0 (предварительная версия 3) такие же, как и для других версий .NET Core. Но если вы хотите создавать проекты .NET Core 3.0 с помощью Visual Studio, необходимо использовать [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). Visual Studio 2019 можно установить параллельно с другими версиями Visual Studio без конфликтов.

## <a name="prerequisites-with-visual-studio-2017"></a>Необходимые компоненты для Visual Studio 2017
    
Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор. Visual Studio 2017 предоставляет интегрированную среду разработки для приложений .NET Core в Windows.

Дополнительные сведения об обновлениях Visual Studio 2017 см. в [заметках о выпуске](/visualstudio/releasenotes/vs2017-relnotes).

# [<a name="net-core-2x"></a>.NET Core 2.x](#tab/netcore2x)

Для разработки приложений .NET Core в Visual Studio 2017 с помощью пакета SDK для .NET Core 2.2 выполните указанные ниже действия:

 1. [Скачайте и установите Visual Studio 2017 версии 15.9.0 или более поздней версии](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-2017-workloads.jpg)

После установки набора инструментов **Кроссплатформенная разработка .NET Core** Visual Studio обычно устанавливает предыдущую версию пакета SDK для .NET Core.
Например, после установки рабочей нагрузки Visual Studio 2017 версии 15.9 использует пакет SDK для .NET Core 2.1 по умолчанию.

Чтобы обновить Visual Studio для использования пакета SDK для .NET Core 2.2, сделайте следующее:

 1. Установите [пакет SDK для .NET Core 2.2](https://dotnet.microsoft.com/download).

 1. Если вы хотите использовать в своем проекте среду выполнения .NET Core последней версии, перенацельте имеющиеся или новые проекты .NET Core на .NET Core 2.2, выполнив приведенные ниже инструкции:

    * В меню **Проект** выберите пункт **Свойства**.
    * В меню **Целевая платформа** выберите значение **.NET Core 2.2**.

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.2" в меню целевой платформы](./media/windows-prerequisites/targeting-dotnet-core.jpg)

Настроив Visual Studio для работы с пакетом SDK для .NET Core 2.2, вы можете выполнять следующие действия:

* открытие, сборка и запуск существующих проектов .NET Core 1.x и 2.x;
* перенацеливание проектов .NET Core 1.x и 2.x на .NET Core 2.2, сборка и запуск;
* создание проектов .NET Core 2.2.

# [<a name="net-core-1x"></a>.NET Core 1.x](#tab/netcore1x)

Для разработки приложений .NET Core 1.x в Visual Studio [скачайте и установите Visual Studio 2017](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> Для разработки приложений .NET Core 1.x можно использовать среду Visual Studio 2015, но делать этого не рекомендуется по указанным ниже причинам.
  > * Средства .NET Core доступны в виде предварительной версии, которая не поддерживается.
  > * Проекты основаны на файлах project.json, которые являются нерекомендуемыми.
>
> Дополнительные сведения об изменениях формата проектов см. в этом [обзоре](./tools/cli-msbuild-architecture.md).

---

<a name="vs-mapping"></a>

> [!TIP]
> Чтобы проверить установленную версию Visual Studio, выполните указанные ниже действия:
>
> * В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
> * В диалоговом окне **О программе Microsoft Visual Studio** проверьте номер версии.
>   * Для приложений .NET Core 3.0, (предварительная версия 3) — Visual Studio 2019 версии 16.0 или более поздняя.
>   * Для приложений .NET Core 2.2 — Visual Studio 2017 версии 15.9 или более поздней версии.
>   * Для приложений .NET Core 2.1 — Visual Studio 2017 версии 15.7 или более поздней версии.
>   * Для приложений .NET Core 1.x — Visual Studio 2017 версии 15.0 или более поздняя версия.