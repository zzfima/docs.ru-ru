---
title: "Необходимые компоненты для .NET Core в Windows"
description: "Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows."
keywords: ".NET Core, Windows, необходимые компоненты, зависимости, Visual Studio"
author: mairaw
ms.author: mairaw
ms.date: 06/26/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0e414af0edbafed5b7f540eda6de2e5078eac789
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a>Необходимые компоненты для .NET Core в Windows

В этой статье показано, какие зависимости необходимы для развертывания и запуска приложений .NET Core на компьютерах под управлением ОС Windows, а также разработки с помощью Visual Studio.

## <a name="supported-windows-versions"></a>Поддерживаемые версии Windows

Платформа .NET Core поддерживается на устройствах под управлением следующих версий ОС Windows:

* Windows 7 SP1
* Windows 8.1
* Windows 10
* Windows Server 2008 R2 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)
* Windows Server 2012 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)
* Windows Server 2012 R2 (полный сервер или основные серверные компоненты)
* Windows Server 2016 (полный сервер, основные серверные компоненты или сервер Nano)

Полный список поддерживаемых операционных систем см. в [заметках о выпуске .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md).

## <a name="net-core-dependencies"></a>Зависимости .NET Core

Для запуска платформы .NET Core в версиях до Windows 10 и Windows Server 2016 необходим распространяемый компонент Visual C++. Эта зависимость устанавливается автоматически, если вы используете установщик .NET Core. Если же вы устанавливаете .NET Core с использованием [скрипта установщика](./tools/dotnet-install-script.md) или выполняете автономное развертывание приложения .NET Core, необходимо вручную установить [распространяемый компонент Microsoft Visual C++ 2015 с обновлением 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685).

> [!NOTE]
> <em>Только для компьютеров под управлением Windows 7 и Windows Server 2008.</em><br>
> Убедитесь, что установка Windows актуальна, а исправление [KB2533623](https://support.microsoft.com/help/2533623) установлено через Центр обновления Windows.

## <a name="prerequisites-with-visual-studio-2017"></a>Необходимые компоненты для Visual Studio 2017

Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор. Если же вы хотите разрабатывать приложения .NET Core в интегрированной среде разработки Windows, можно использовать [Visual Studio 2017](#visual-studio-2017).

> [!IMPORTANT]
> Хотя можно использовать Visual Studio 2015 с предварительной версией средств .NET Core, эти проекты будут основаны на формате *project.json*, который сейчас считается нерекомендуемым. Visual Studio 2017 использует файлы проектов, основанные на MSBuild. Дополнительные сведения об изменениях формата см. в этом [обзоре](./tools/cli-msbuild-architecture.md).

Чтобы использовать Visual Studio 2017 для разработки приложений .NET Core, нужно установить последнюю доступную версию Visual Studio с выбранным набором инструментов **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).
![Снимок экрана установки Visual Studio 2017 с выбранной рабочей нагрузкой "Кроссплатформенная разработка .NET Core"](./media/windows-prerequisites/vs_workloads.jpg)

Существуют разные выпуски Visual Studio 2017. Чтобы приступить к работе, можно бесплатно скачать версию [Visual Studio Community 2017](https://www.visualstudio.com/downloads/).  Дополнительные сведения о процедуре установки Visual Studio см. в статье [Install Visual Studio 2017](/visualstudio/install/install-visual-studio) (Установка Visual Studio 2017).

Чтобы убедиться, что вы используете последнюю доступную версию Visual Studio 2017, сделайте следующее:

 * В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
 * В диалоговом окне **О программе Microsoft Visual Studio** должна быть указана версия 15.0.26228.4 или более поздняя версия.

Дополнительные сведения об обновлениях Visual Studio 2017 см. в [заметках о выпуске](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).

