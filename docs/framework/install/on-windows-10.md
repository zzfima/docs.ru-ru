---
title: "Установка платформы .NET Framework в Windows 10"
description: "Дополнительные сведения об установке .NET Framework в Windows 10 или Windows Server 2016."
author: rlander
ms.author: mairaw
keywords: ".NET Framework, установка"
ms.date: 11/17/2017
ms.topic: article
ms.custom: updateeachrelease
ms.prod: .net-framework
ms.openlocfilehash: d7f8dd4c6ee9f7eeda389a955f806a5765876ea7
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2017
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016"></a>Установите .NET Framework в Windows 10 и Windows Server 2016

Для многих приложений работающих под управлением Windows требуется платформа .NET Framework. Инструкции в этой статье помогут вам установить версии .NET Framework, которые необходимы. [.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) является последней доступной версии.

Вы может попали на эту страницу после попытки выполнения приложения и отображается диалоговое окно на компьютере аналогично приведенному ниже:

![Не удалось запустить это приложение](./media/this-application-could-not-be-started.png)

## <a name="net-framework-471"></a>.NET framework 4.7.1

Платформа .NET Framework 4.7.1 входит в состав:

* [Создатели Осень обновления (версия 1709) для Windows 10](https://www.microsoft.com/software-download/windows10)
* [Windows Server 2016 (версия 1709)](https://docs.microsoft.com/windows-server/get-started/get-started-with-1709)

> [!div class="button"]
[Загрузить .NET Framework 4.7.1](https://www.microsoft.com/net/download/thank-you/net471?utm_source=ms-docs&utm_medium=referral)

[.NET Framework 4.7.1](https://www.microsoft.com/download/details.aspx?id=56115&desc=dotnet47) может использоваться для запуска приложений, разработанных для .NET Framework 4.0 через 4.7.1.

Можно установить [.NET Framework 4.7.1](https://www.microsoft.com/en-us/download/details.aspx?id=56115&desc=dotnet47) на:

* Обновления создатели Windows 10 (версия 1703)
* Обновления окончания действия (версии 1607) для Windows 10
* Windows Server 2016

Платформа .NET Framework 4.7.1 не поддерживается:

* Windows 10 1507
* Windows 10 версии 1511

Если вы используете Windows 10 1507 или 1511 и требуется установить платформу .NET Framework 4.7.1, необходимо сначала выполнить обновление до более поздней версии Windows 10.

## <a name="net-framework-461"></a>.NET Framework 4.6.1

[.NET Framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981) является последней поддерживаемой версии платформы .NET Framework в Windows 10 1507 и 1511.

Платформа .NET Framework 4.6.1 поддерживает приложений, созданных для .NET Framework 4.0 через 4.6.1.

## <a name="net-framework-35"></a>.NET Framework 3,5

Следуйте инструкциям по установке [.NET Framework 3.5 в Windows 10](dotnet-35-windows-10.md).

.NET Framework 3.5 поддерживает приложений, созданных для .NET Framework 1.0 до 3.5.

## <a name="additional-information"></a>Дополнительные сведения

Версии платформы .NET framework 4.x — это обновления на месте для более ранних версий. Это означает следующее:

- Можно установить только одной версии платформы .NET Framework 4.x, установлены на компьютере.

- Не удается установить более раннюю версию платформы .NET Framework на компьютере, если уже установлена более новая версия.

- 4.x версии платформы .NET Framework могут использоваться для запуска приложений, разработанных для .NET Framework 4.0 до этой версии. Например .NET Framework 4.7 можно использовать для запуска приложений, разработанных для .NET Framework 4.0 через 4.7. Последнюю версию (.NET Framework 4.7.1) можно использовать для запуска приложения, построенные будет всех версий платформы .NET Framework, начиная с версии 4.0.

Список всех версий платформы .NET Framework, доступного для загрузки см. в разделе [загрузок .NET](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) страницы.

## <a name="help"></a>Справка

Если не удается получить правильную версию платформы .NET Framework установлена, вы можете [обратиться в корпорацию Майкрософт для получения справки](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).

## <a name="see-also"></a>См. также

[Загрузка .NET](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral)   
[Устранение неполадок заблокированных установок и удалений .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)   
[Установите .NET Framework для разработчиков](guide-for-developers.md)