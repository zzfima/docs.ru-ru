---
title: "Предварительные требования для средств .NET Core (предварительная версия 3)"
description: "Предварительные требования для средств .NET Core (предварительная версия 3)"
keywords: .NET, .NET Core
author: billwagner
ms.author: wiwagn
ms.date: 09/15/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: 07b62bd7163193eff8dc8f61fda7a45a924bba2b
ms.openlocfilehash: ee4ccba7c06f0a7f67e3fe59c885febf895235fd

---

# <a name="prerequisites-for-windows-development-preview-3-tooling"></a>Предварительные требования для средств разработки приложений Windows (предварительная версия 3)

Для разработки приложений .NET Core в Windows с помощью Visual Studio требуются следующие компоненты:

* поддерживаемая версия клиента или операционной системы Windows;
* Версия-кандидат Visual Studio 2017 или более поздней версии
* Средства .NET Core (предварительная версия 3)

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

Вы можете разрабатывать приложения .NET Core с помощью любого редактора и средств командной строки .NET Core. Если же вы хотите использовать Visual Studio и средства .NET Core (предварительная версия 3), вам понадобится версия-кандидат Visual Studio 2017 или более поздней версии. Скачать [версию-кандидат Visual Studio Community 2017](https://www.visualstudio.com/vs/visual-studio-2017-rc/) можно бесплатно. 

У вас должна быть запущена версия-кандидат Visual Studio 2017:

* В меню **Справка** выберите пункт **О программе Microsoft Visual Studio**.
* В диалоговом окне **О программе Microsoft Visual Studio** должна быть указана версия 15.0.25831.1 или выше.

Дополнительные сведения об обновлениях версии-кандидата Visual Studio 2017 см. в [заметках о выпуске](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

Рабочая нагрузка ".NET Core и Docker (предварительная версия)" должна быть установлена в ходе установки. В противном случае можно снова запустить программу установки и выбрать этот компонент.



<!--HONumber=Nov16_HO3-->


