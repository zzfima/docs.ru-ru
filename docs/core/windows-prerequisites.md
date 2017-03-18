---
title: "Необходимые компоненты для .NET Core в Windows | Документация Майкрософт"
description: "Узнайте о том, какие зависимости необходимы для разработки и запуска приложений .NET Core на компьютере Windows."
keywords: ".NET Core, Windows, необходимые компоненты, зависимости, Visual Studio"
author: mairaw
ms.author: mairaw
ms.date: 01/05/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: e374b924bf78d62227cb9607641130dfd9128186
ms.openlocfilehash: 6383a0ce253f6f7000ed8a81b29b9e1d58914acc
ms.lasthandoff: 03/06/2017

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
* Windows Server 2012 R2 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)
* Windows Server 2016 (полный сервер, основные серверные компоненты или сервер Nano)

Полный список [поддерживаемых операционных систем](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md#rtm-platform-support) см. в [заметках о выпуске .NET Core 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md).

## <a name="net-core-dependencies"></a>Зависимости .NET Core

Для запуска платформы .NET Core в версиях до Windows 10 и Windows Server 2016 необходим распространяемый компонент Visual C++. Эта зависимость устанавливается автоматически, если вы используете установщик .NET Core. Если же вы устанавливаете .NET Core с использованием [скрипта установщика](https://docs.microsoft.com/en-us/dotnet/articles/core/tools/dotnet-install-script) или выполняете автономное развертывание приложения .NET Core, необходимо вручную установить [распространяемый компонент Visual C++ для Visual Studio 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48145).

> [!NOTE]
> <em>Только для компьютеров под управлением Windows 7 и Windows Server 2008.</em><br>
> Убедитесь, что установка Windows актуальна, а исправление [KB2533623](https://support.microsoft.com/en-us/kb/2533623) установлено через Центр обновления Windows.

## <a name="prerequisites-with-visual-studio-2017"></a>Необходимые компоненты для Visual Studio 2017

Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор. Если же вы хотите разрабатывать приложения .NET Core в интегрированной среде разработки Windows, можно использовать [Visual Studio 2017](#visual-studio-2017).

Чтобы использовать Visual Studio 2017 для разработки приложений .NET Core, нужно установить последнюю доступную версию Visual Studio с выбранным набором инструментов **Кроссплатформенная разработка .NET Core** (в разделе **Другие наборы инструментов**).

Существуют разные выпуски Visual Studio 2017. Чтобы приступить к работе, можно бесплатно скачать версию [Visual Studio Community 2017](https://www.visualstudio.com/vs/visual-studio-2017/#downloadvs).  Дополнительные сведения о процедуре установки Visual Studio см. в статье [Install Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) (Установка Visual Studio 2017).

Дополнительные сведения об обновлениях Visual Studio 2017 см. в [заметках о выпуске](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546
