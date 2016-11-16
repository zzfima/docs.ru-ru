---
title: "Предварительные требования для .NET Core"
description: "Предварительные требования для .NET Core"
keywords: .NET, .NET Core
author: billwagner
manager: wpickett
ms.date: 09/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: 130b94a745b0e3222e205d8af26194239130ec9c
ms.openlocfilehash: 04018ec65272745ef98a2a96eb30009bcf44cb2e

---

# <a name="prerequisites-for-windows-development"></a>Предварительные требования для разработки приложений Windows

Для разработки приложений .NET Core в Windows с помощью Visual Studio требуются следующие компоненты:

* поддерживаемая версия клиента или операционной системы Windows;
* Visual Studio 2015 с обновлением 3.3 или более поздней версии;
* расширение диспетчера NuGet для Visual Studio;
* предварительная версия 2 средств .NET Core.

## <a name="supported-windows-versions"></a>Поддерживаемые версии Windows

Платформа .NET Core поддерживается следующими версиями Windows.

* Windows 7 SP1
* Windows 8.1
* Windows 10
* Windows Server 2008 R2 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)
* Windows Server 2012 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)
* Windows Server 2012 R2 с пакетом обновления 1 (SP1) (полный сервер или основные серверные компоненты)
* Windows Server 2016 (полный сервер, основные серверные компоненты или сервер Nano)

Полный список [поддерживаемых операционных систем](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md#rtm-platform-support) см. в [заметках о выпуске .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md).

## <a name="net-core-dependencies"></a>Зависимости .NET Core

При выполнении в Windows платформа .NET Core требует наличия Распространяемого компонента Visual C++. Он устанавливается автоматически установщиком .NET Core. Если платформа .NET Core устанавливается с помощью скрипта установки (`dotnet-install.ps1`), Распространяемый компонент Visual C++ необходимо установить вручную. 

Версия Распространяемого компонента Visual C++ зависит от версии Windows.

* Windows 10
    * [Распространяемый компонент Visual C++ для Visual Studio 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48145)
* Windows 7 или более поздней версии (кроме Windows 10)
    * Проверьте, актуальна ли установка Windows и установлено ли исправление [KB2533623](https://support.microsoft.com/en-us/kb/2533623) через Центр обновления Windows.
    * [Обновление для Universal CRT](https://www.microsoft.com/en-us/download/details.aspx?id=48234) (дополнительные сведения о Universal CRT см. в [этой записи блога](https://blogs.msdn.microsoft.com/vcblog/2015/03/03/introducing-the-universal-crt/))

## <a name="visual-studio"></a>Visual Studio

Для разработки приложений .NET Core требуется среда Visual Studio 2015. Скачать версию [Visual Studio Community 2015](https://www.visualstudio.com/downloads/download-visual-studio-vs) можно бесплатно. 

Убедитесь в том, что у вас версия [Visual Studio 2015 с обновлением 3.3](https://msdn.microsoft.com/library/mt752379.aspx).

* В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
* В диалоговом окне **О программе Microsoft Visual Studio** должна быть указана версия 14.0.25424.00 или более поздняя, а также обновление 3.
* Если у вас нет обновления 3, сначала нужно скачать и установить [Visual Studio 2015 с обновлением 3](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).
* Если у вас есть обновление 3, но номер версии ниже 14.0.25424.00, нужно скачать и установить [Visual Studio 2015 с обновлением 3.3](https://msdn.microsoft.com/library/mt752379.aspx).

Дополнительные сведения об изменениях в обновлении 3 см. в [заметках о выпуске](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).

## <a name="nuget-manager-extension-for-visual-studio"></a>Расширение диспетчера NuGet для Visual Studio

NuGet — это диспетчер пакетов для платформы разработки Майкрософт, включая .NET Core. Для разработки приложений .NET Core требуется [NuGet 3.5.0](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) или более поздней версии.

## <a name="net-core-tools-for-visual-studio-2015"></a>Средства .NET Core для Visual Studio 2015

Скачайте и установите [предварительную версию 2 средств .NET Core 1.0.1 для Visual Studio 2015][sdk]. 

Пакет средств .NET Core устанавливает платформу .NET Core, шаблоны проектов и другие средства для Visual Studio 2015.

> [!NOTE]
В настоящее время нельзя скачать автономный установщик [предварительной версии 2 средств .NET Core 1.0.1 для Visual Studio 2015][sdk]. Вместо этого необходимо скачать [обычный начальный загрузчик ][sdk] и запустить его с параметром командной строки (например, `/layout c:\path`), чтобы получить автономную структуру. После этого ее можно использовать для автономной установки: просто запустите исполняемый файл из локального каталога. Обратите внимание на то, что, так как это полная структура, скачиваются все пакеты для всех поддерживаемых языков, что требует примерно 1 ГБ места на диске.

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546



<!--HONumber=Nov16_HO1-->


