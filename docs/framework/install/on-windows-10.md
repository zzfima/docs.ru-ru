---
title: "Установка платформы .NET Framework в Windows 10"
description: "Сведения об установке платформы .NET Framework в Windows 10 или Windows Server 2016."
author: rlander
ms.author: mairaw
keywords: ".NET Framework, установка"
ms.date: 12/20/2017
ms.topic: article
ms.custom: updateeachrelease
ms.prod: .net-framework
ms.workload: dotnet
ms.openlocfilehash: bd588dff62e5d4ac1c1059e697a07598ba272042
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016"></a>Установка платформы .NET Framework в Windows 10 и Windows Server 2016

Для многих приложений, работающих в ОС Windows, требуется платформа .NET Framework. В этой статье приводятся инструкции по установке необходимых версий .NET Framework. [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) является последней доступной версией.

Вы могли попасть на эту страницу после попытки запуска приложения и отображения диалогового окна, аналогичного приведенному ниже:

![Не удалось запустить это приложение.](./media/this-application-could-not-be-started.png)

## <a name="net-framework-471"></a>.NET Framework 4.7.1

Платформа .NET Framework 4.7.1 входит в состав:

* [Windows 10 Fall Creators Update (версия 1709)](https://www.microsoft.com/software-download/windows10)
* [Windows Server, версия 1709](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709)

> [!div class="button"]
[Скачать .NET Framework 4.7.1](https://www.microsoft.com/net/download/thank-you/net471?utm_source=ms-docs&utm_medium=referral)

[.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) можно использовать для запуска приложений, созданных для .NET Framework версии от 4.0 до 4.7.1.

Вы можете установить [.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) в:

* Обновление Windows 10 Creators Update (версия 1703)
* Юбилейное обновление Windows 10 Anniversary Update (версия 1607)
* Windows Server 2016

Платформа .NET Framework 4.7.1 не поддерживается в следующих выпусках:

* Windows 10 1507
* Windows 10 1511

Если вы используете Windows 10 1507 или 1511 и хотите установить платформу .NET Framework 4.7.1, сначала необходимо выполнить обновление до более поздней версии Windows 10.

## <a name="net-framework-462"></a>.NET Framework 4.6.2

[.NET Framework 4.6.2](https://www.microsoft.com/en-us/download/details.aspx?id=53345) является последней поддерживаемой версией платформы .NET Framework в Windows 10 1507 и 1511.

Платформа .NET Framework 4.6.2 поддерживает приложения, созданные для платформы .NET Framework версий с 4.0 по 4.6.2.

## <a name="net-framework-35"></a>.NET Framework 3,5

Следуйте инструкциям по установке [.NET Framework 3.5 в Windows 10](dotnet-35-windows-10.md).

Платформа .NET Framework 3.5 поддерживает приложения, созданные для платформы .NET Framework версий с 1.0 по 3.5.

## <a name="additional-information"></a>Дополнительные сведения

В версиях платформы .NET Framework 4.x существуют локальные обновления на более ранние версии. Это означает следующее.

- На компьютере может быть установлена только одна версия платформы .NET Framework 4.x.

- Нельзя установить более раннюю версию .NET Framework, если уже установлена более поздняя версия.

- .NET Framework версий 4.x можно использовать для запуска приложений, созданных для .NET Framework версий с 4.0 до этой версии. Например, .NET Framework 4.7 можно использовать для запуска приложений, созданных для .NET Framework версии с 4.0 до 4.7. Последнюю версию (.NET Framework 4.7.1) можно использовать для запуска приложений, созданных для всех версий платформы .NET Framework, начиная с версии 4.0.

Список всех версий платформы .NET Framework, доступных для скачивания, см. на странице [скачиваемых файлов .NET](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral).

## <a name="help"></a>Справка

Вы можете [обратиться за помощью в корпорацию Майкрософт](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help), если не можете определить правильную версию установленной платформы .NET Framework.

## <a name="see-also"></a>См. также

[Скачиваемые файлы .NET](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral)   
[Устранение неполадок заблокированных установок и удалений .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)   
[Установка .NET Framework для разработчиков](guide-for-developers.md)
