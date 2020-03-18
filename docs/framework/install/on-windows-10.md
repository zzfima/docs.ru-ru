---
title: Установка платформы .NET Framework в Windows 10
description: Сведения об установке платформы .NET Framework в Windows 10 или Windows Server 2016.
ms.date: 04/18/2019
ms.custom: updateeachrelease
ms.openlocfilehash: eed15b9088d6ba46d8f5bc6d16ba779dd6115b0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "76965975"
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016-and-later"></a>Установка платформы .NET Framework в Windows 10 и Windows Server 2016 и более поздней версии

Для многих приложений, работающих в ОС Windows, требуется платформа .NET Framework. В этой статье приводятся инструкции по установке необходимых версий .NET Framework. [.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) является последней доступной версией.

Вы могли попасть на эту страницу после попытки запуска приложения и отображения диалогового окна, аналогичного приведенному ниже:

![Не удалось запустить это приложение.](./media/this-application-could-not-be-started.png)

## <a name="net-framework-48"></a>.NET Framework 4.8

.NET Framework 4.8 входит в состав:

- [обновления Windows 10 за май 2019 г.](https://support.microsoft.com/help/4028685/windows-10-get-the-update)

> [!div class="button"]
> [скачать .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48).

[.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48) можно использовать для запуска приложений, созданных для .NET Framework версий от 4.0 до 4.7.2.

Вы можете установить [.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48) в:

- обновлении Windows 10 за октябрь 2018 г. (версия 1809);
- Windows 10, обновление за апрель 2018 г. (версия 1803)
- Windows 10 Fall Creators Update (версия 1709)
- Обновление Windows 10 Creators Update (версия 1703)
- Юбилейное обновление Windows 10 Anniversary Update (версия 1607)
- Windows Server 2019
- Windows Server, версия 1809
- Windows Server, версия 1803
- Windows Server 2016

.NET Framework 4.8 не поддерживается в:

- Windows 10 1507
- Windows 10 1511

Если вы используете Windows 10 с версией сборки 1507 или 1511 и хотите установить .NET Framework 4.8, сначала выполните обновление до более поздней версии Windows 10.

## <a name="net-framework-462"></a>.NET Framework 4.6.2

[.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462) является последней поддерживаемой версией платформы .NET Framework в Windows 10 1507 и 1511.

Платформа .NET Framework 4.6.2 поддерживает приложения, созданные для платформы .NET Framework версий с 4.0 по 4.6.2.

## <a name="net-framework-35"></a>.NET Framework 3,5

Следуйте инструкциям по установке [.NET Framework 3.5 в Windows 10](dotnet-35-windows-10.md).

Платформа .NET Framework 3.5 поддерживает приложения, созданные для платформы .NET Framework версий с 1.0 по 3.5.

## <a name="additional-information"></a>Дополнительные сведения

В версиях платформы .NET Framework 4.x существуют локальные обновления на более ранние версии. Это означает следующее.

- На компьютере может быть установлена только одна версия платформы .NET Framework 4.x.

- Нельзя установить более раннюю версию .NET Framework, если уже установлена более поздняя версия.

- .NET Framework версий 4.x можно использовать для запуска приложений, созданных для .NET Framework версий с 4.0 до этой версии. Например, .NET Framework 4.7 можно использовать для запуска приложений, созданных для .NET Framework версии с 4.0 до 4.7. Последнюю версию (.NET Framework 4.8) можно использовать для запуска приложений, созданных для всех версий .NET Framework начиная с версии 4.0.

Список всех версий платформы .NET Framework, доступных для скачивания, см. на странице [скачиваемых файлов .NET](https://dotnet.microsoft.com/download).

## <a name="help"></a>Справка

Вы можете [обратиться за помощью в корпорацию Майкрософт](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help), если не можете определить правильную версию установленной платформы .NET Framework.

## <a name="see-also"></a>См. также раздел

- [Скачиваемые файлы .NET](https://dotnet.microsoft.com/download)
- [Устранение неполадок с заблокированными установками и удалениями .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
- [Установка .NET Framework для разработчиков](guide-for-developers.md)
