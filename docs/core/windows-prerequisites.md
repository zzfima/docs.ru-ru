---
title: Необходимые компоненты для .NET Core в Windows
description: Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: 6885f6c853efb0dcb2cb64b83f07e12b1dc2e3cf
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771952"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Необходимые компоненты для .NET Core в Windows

В этой статье описываются поддерживаемые версии ОС, необходимые для запуска приложений .NET Core в Windows. Поддерживаемые версии ОС, а также перечисленные ниже зависимости относятся к трем способам разработки приложений .NET Core в Windows:

* [командная строка;](./tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [Visual Studio Code](https://code.visualstudio.com/)

Кроме того, если вы разрабатываете приложение в Windows с помощью Visual Studio, ознакомьтесь с минимальными поддерживаемыми версиями для разработки .NET Core в разделе [Необходимые компоненты для разработки приложений .NET Core с помощью Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio).

## <a name="net-core-supported-operating-systems"></a>Поддерживаемые операционные системы для .NET Core

В следующих статьях содержится полный список операционных систем с указанием версий, в которых поддерживается .NET Core:

* [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

Дополнительные сведения и ссылки для скачивания см. на следующих страницах: [на странице скачиваемых файлов .NET](https://dotnet.microsoft.com/download) для загрузки новой версии и [на странице архива загрузок .NET](https://dotnet.microsoft.com/download/archives#dotnet-core) для более старых версий.

## <a name="net-core-dependencies"></a>Зависимости .NET Core

[Распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/download/details.aspx?id=52685) необходимо установить вручную в следующих случаях:

* при установке .NET Core с помощью [скрипта установщика](./tools/dotnet-install-script.md);
* при развертывании автономного приложения .NET Core.
* сборка продукта из исходного кода;
* установка .NET Core из файла *.zip*, включая серверы сборки/непрерывной интеграции/непрерывного развертывания.

> [!NOTE]
> **Для Windows 8.1 и более ранних версий или Windows Server 2012 R2 и более ранних версий:**
>
> Убедитесь, что установленная версия Windows актуальна и содержит обновление [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), которое можно установить через Центр обновления Windows. Если это обновление не установлено, при запуске приложения .NET Core появится следующая ошибка: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`
>
> **Для Windows 7 или Windows Server 2008 R2:**
>
> Убедитесь, что помимо обновления KB2999226 также установлено обновление [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot). Если это обновление не установлено, при запуске приложения .NET Core появится примерно следующая ошибка: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a>Необходимые компоненты для разработки приложений .NET Core с помощью Visual Studio

Хотя вы можете использовать любой редактор для разработки приложений .NET Core с помощью SDK для .NET Core, Visual Studio 2017 и более поздние версии предоставляют интегрированную среду разработки для приложений .NET Core в Windows.

<a name="vs-mapping"></a>

Для каждой версии .NET Core имеется минимальная необходимая версия Visual Studio. Чтобы проверить установленную версию Visual Studio, выполните указанные ниже действия:

* В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
* В диалоговом окне **О программе Microsoft Visual Studio** проверьте номер версии.

В таблице ниже перечислены минимальные версии для каждого пакета SDK.

| Версия пакета SDK для .NET Core | Версия Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 3.0                   | Visual Studio 2019 версии 16.3 или более поздней. |
| 2.2                   | Visual Studio 2017 версии 15.9 или более поздней. |
| 2.1                   | Visual Studio 2017 версии 15.7 или более поздней. |
| 1.x                   | Visual Studio 2017 версии 15.0 или более поздней. |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

Для разработки приложений .NET Core в Visual Studio 2019 с помощью пакета SDK для .NET Core 3.0 выполните указанные ниже действия.

* [Скачайте и установите Visual Studio 2019 версии 16.3 или более поздней](/visualstudio/install/install-visual-studio) и выберите одну из следующих рабочих нагрузок, включающих в себя пакет SDK для .NET Core, в зависимости от типа создаваемого приложения:

  * рабочая нагрузка **Кроссплатформенная разработка .NET Core** в разделе **Другие наборы инструментов**;
  * рабочая нагрузка **ASP.NET и разработка веб-приложений** в разделе **Веб-разработка и облако**;
  * рабочая нагрузка **ASP.NET и разработка веб-приложений** в разделе **Разработка классических приложений .NET**.

На следующем рисунке показана рабочая нагрузка **Кроссплатформенная разработка .NET Core**, выбранная в пользовательском интерфейсе Visual Studio.

![Снимок экрана установки Visual Studio 2019 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-2019-workloads.jpg)

После установки любой из этих рабочих нагрузок Visual Studio 2019 версии 16.3 использует пакет SDK для .NET Core 3.0 по умолчанию.

Если вы хотите использовать в существующих проектах среду выполнения .NET Core последней версии, перенацельте каждый имеющийся проект .NET Core на .NET Core 3.0, выполнив приведенные ниже инструкции.

* В меню **Проект** выберите пункт **Свойства**.
* В меню **Целевая платформа** выберите значение **.NET Core 3.0**.

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2019 с выбранным пунктом ".NET Core 3.0" в меню целевой платформы](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

Настроив Visual Studio для работы с пакетом SDK для .NET Core 3.0, вы можете выполнять следующие действия:

* открытие, сборка и запуск существующих проектов .NET Core 1.x и 2.x;
* перенацеливание проектов .NET Core 1.x и 2.x на .NET Core 3.0, сборка и запуск;
* создание проектов .NET Core 3.0.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Для разработки приложений .NET Core в Visual Studio 2017 с помощью пакета SDK для .NET Core 2.2 выполните указанные ниже действия:

* [Скачайте и установите Visual Studio 2019 версии 16.3 или более поздней](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).
* [Скачайте и установите Visual Studio 2017 версии 15.9.0 или более поздней версии](/visualstudio/install/install-visual-studio) с выбранной рабочей нагрузкой **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs-2017-workloads.jpg)

После установки набора инструментов **Кроссплатформенная разработка .NET Core** Visual Studio обычно устанавливает предыдущую версию пакета SDK для .NET Core.
Например, после установки рабочей нагрузки Visual Studio 2017 версии 15.9 использует пакет SDK для .NET Core 2.1 по умолчанию.

Чтобы обновить Visual Studio для использования пакета SDK для .NET Core 2.2, сделайте следующее:

 1. Установите [пакет SDK для .NET Core 2.2](https://dotnet.microsoft.com/download).

 1. Если вы хотите использовать в своем проекте среду выполнения .NET Core последней версии, перенацельте каждый имеющийся или новый проект .NET Core на .NET Core 2.2, выполнив приведенные ниже инструкции.

    * В меню **Проект** выберите пункт **Свойства**.
    * В меню **Целевая платформа** выберите значение **.NET Core 2.2**.

![Снимок экрана: окно свойств проекта приложения в Visual Studio 2017 с выбранным пунктом ".NET Core 2.2" в меню целевой платформы](./media/windows-prerequisites/targeting-dotnet-core.jpg)

Настроив Visual Studio для работы с пакетом SDK для .NET Core 2.2, вы можете выполнять следующие действия:

* открытие, сборка и запуск существующих проектов .NET Core 1.x и 2.x;
* перенацеливание проектов .NET Core 1.x и 2.x на .NET Core 2.2, сборка и запуск;
* создание проектов .NET Core 2.2.

---
