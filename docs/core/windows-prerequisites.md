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
ms.sourcegitcommit: a8019c9fc25ef458aa555743e61cd83a3beb11ed
ms.openlocfilehash: b5c088da7d1155414a08995ae0d72154af891190
ms.lasthandoff: 02/28/2017

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

## <a name="prerequisites-with-visual-studio"></a>Необходимые компоненты для Visual Studio

Для разработки приложений .NET Core с помощью пакета SDK для .NET Core вы можете использовать любой редактор. Для разработки приложения .NET Core на платформе Windows с помощью Visual Studio можно воспользоваться одной из двух версий программы:

* [Visual Studio 2015](#visual-studio-2015)
* [Версия-кандидат Visual Studio 2017](#visual-studio-2017-rc)

В Visual Studio 2015 проекты по умолчанию создаются в формате project.json, а в версии-кандидате Visual Studio 2017 — в формате MSBuild. Дополнительные сведения об изменениях формата см. в этом [обзоре](./preview3/tools/layering.md).

### <a name="visual-studio-2015"></a>Visual Studio 2015

Если для разработки приложений .NET Core вы хотите использовать Visual Studio 2015, вам понадобится следующее.

* Visual Studio 2015 с обновлением 3.3 или более поздней версии.

   Существуют разные [выпуски](https://www.visualstudio.com/vs/compare) Visual Studio 2015. Чтобы приступить к работе, можно бесплатно скачать версию [Visual Studio Community 2015](https://www.visualstudio.com/downloads/). 

   Убедитесь в том, что вы используете версию [Visual Studio 2015 с обновлением 3.3](https://msdn.microsoft.com/library/mt752379.aspx). Для этого сделайте следующее.

   * В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
   * В диалоговом окне **О программе Microsoft Visual Studio** должна быть указана версия 14.0.25424.00 или более поздняя, а также обновление 3.
   * Если у вас нет обновления 3, сначала нужно скачать и установить [Visual Studio 2015 с обновлением 3](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).
   * Если у вас есть обновление 3, но номер версии ниже 14.0.25424.00, нужно скачать и установить [Visual Studio 2015 с обновлением 3.3](https://msdn.microsoft.com/library/mt752379.aspx).

   Дополнительные сведения об изменениях в обновлении 3 см. в [заметках о выпуске](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).

* Расширение диспетчера NuGet для Visual Studio

   NuGet — это диспетчер пакетов для платформы разработки Майкрософт, включая .NET Core. Для разработки приложений .NET Core требуется [NuGet 3.5.0 бета-версии](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) или более поздней версии.

* предварительная версия 2 средств .NET Core.

   Скачайте и установите [предварительную версию 2 средств .NET Core 1.0.1 для Visual Studio 2015][sdk]. 

   Пакет средств .NET Core устанавливает платформу .NET Core, шаблоны проектов и другие средства для Visual Studio 2015.

   > [!NOTE]
   > Сейчас нельзя скачать автономный установщик для [предварительной версии 2 средств .NET Core 1.0.1 для Visual Studio 2015][sdk]. Вместо этого необходимо скачать [обычный загрузчик ][sdk] и запустить его с параметром командной строки (например, `/layout c:\path`), чтобы получить автономную структуру. После этого ее можно использовать для автономной установки: просто запустите исполняемый файл из локального каталога. Обратите внимание на то, что, так как это полная структура, скачиваются все пакеты для всех поддерживаемых языков, что требует примерно 1 ГБ места на диске.

### <a name="visual-studio-2017-rc"></a>Версия-кандидат Visual Studio 2017

Если вы хотите использовать версию-кандидат Visual Studio 2017 для разработки приложений .NET Core, необходимо установить последнюю доступную версию-кандидат Visual Studio с выбранной рабочей нагрузкой ".NET Core и Docker (предварительная версия)". 

Существуют разные выпуски версии- кандидата Visual Studio 2017. Чтобы приступить к работе, можно бесплатно скачать [версию-кандидат Visual Studio Community 2017](https://www.visualstudio.com/vs/visual-studio-2017-rc/#downloadvs).  Дополнительные сведения о процедуре установки Visual Studio см. в статье [Install Visual Studio 2017 RC](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) (Установка версии-кандидата Visual Studio 2017).

Чтобы убедиться, что вы используете последнюю доступную версию-кандидат Visual Studio 2017, сделайте следующее.

* В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
* В диалоговом окне **О программе Microsoft Visual Studio** должна быть указана версия 15.0.26020.0 или выше.

Дополнительные сведения об обновлениях версии-кандидата Visual Studio 2017 см. в [заметках о выпуске](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546

