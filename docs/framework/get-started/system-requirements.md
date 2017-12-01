---
title: "Требования к системе для .NET Framework"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- software requirements
- .NET Framework, system requirements
- system requirements
- operating systems supported
- hardware requirements
ms.assetid: 298275e2-da1d-4618-9f74-6a3567832350
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b08bd7b78a8606f61c266da51f4079f0b5f4aac6
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2017
---
# <a name="net-framework-system-requirements"></a>Требования к системе для .NET Framework

Таблицы в этом разделе содержат оборудования, операционной системы и требования к программному обеспечению для .NET Framework 4.5 и ее доработанных выпусков (4.5.1 и 4.5.2), [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и ее доработанных выпусков (4.6.1 и 4.6.2) и .NET Framework 4.7 и его точки выпуск (4.7.1). Для сред разработки, позволяющих разрабатывать приложения для платформы .NET Framework, существует отдельный набор требований.

Сведения о скачивании и ссылки для скачивания см. в разделе [Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md).

Сведения о жизненном цикле поддержки версий .NET Framework см. в разделе [Политика жизненного цикла поддержки продуктов Майкрософт](https://support.microsoft.com/en-us/lifecycle/search?sort=PN&alpha=Microsoft%20.NET%20Framework&Filter=FilterNO).

## <a name="hardware-requirements"></a>Требования к оборудованию

|                          |        |
| ------------------------ | ------ |
| **Процессор**            | 1 ГГц  |
| **ОЗУ**                  | 512 Мб |
| **Дисковое пространство (минимум)** |        |
| 32-разрядная                   | 4,5 ГБ |
| 64-разрядная версия                   | 4,5 ГБ |

## <a name="installation-requirements"></a>Требования к установке

Для установки платформы .NET Framework требуются разрешения администратора. Если у вас отсутствуют разрешения администратора на компьютере, на котором требуется установить платформу .NET Framework, обратитесь к администратору сети.

## <a name="supported-client-operating-systems"></a>Поддерживаемые клиентские операционные системы

| Операционная система | Поддерживаемые выпуски | Предустановлена с операционной системой | Может устанавливаться отдельно |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Создатели Осень центра обновления Windows 10 | 32- и 64-разрядные версии | .NET framework 4.7.1 | |
| Обновление Windows 10 Creators Update | 32- и 64-разрядные версии | .NET Framework 4.7 | .NET framework 4.7.1 | 
| Юбилейное обновление Windows 10 Anniversary Update | 32- и 64-разрядные версии | [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|.NET Framework 4.7<br/><br/>.NET framework 4.7.1 |
| Ноябрьское обновление Windows 10 | 32- и 64-разрядная | [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] | |
| Windows 10 | 32- и 64-разрядная | [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] | [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] |
| [!INCLUDE[win81](../../../includes/win81-md.md)] | 32-разрядная версия, 64-разрядная версия и ARM | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] | [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET framework 4.7.1 |
| [!INCLUDE[win8](../../../includes/win8-md.md)] | 32-разрядная версия, 64-разрядная версия и ARM | [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] |
| Windows 7 SP1|32- и 64-разрядные версии | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET framework 4.7.1|
| Windows Vista SP2|32- и 64-разрядные версии | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] |
| Windows XP |32- и 64-разрядные версии | -- | .NET Framework 4 |

 **Примечания.**

- В системах Windows 7 платформе .NET Framework требуется пакет обновления 1 (SP1) для Windows 7. Если вы используете Windows 7 и еще не установили пакет обновления 1 (SP1), это необходимо сделать перед установкой платформы .NET Framework.

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] поддерживается в среде предустановки Windows (за исключением некоторых функций).

- .NET Framework 4 также поддерживает платформу IA64.

- Для обеспечения оптимального уровня совместимости и безопасности на всех платформах рекомендуется установить последнюю версию пакета обновления Windows и все критические обновления, доступные на [веб-сайте Центра обновления Windows](http://go.microsoft.com/fwlink/?LinkId=168461).

- В 64-разрядных операционных системах платформа .NET Framework поддерживает как среду WOW64 (32-разрядная обработка на 64-разрядном компьютере), так и собственную 64-разрядную обработку.

## <a name="supported-server-operating-systems"></a>Поддерживаемые серверные операционные системы

| Операционная система | Поддерживаемые выпуски | Предустановлена с операционной системой | Может устанавливаться отдельно |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Windows Server, версии 1709 | 64-разрядная версия | .NET framework 4.7.1 | -- |
| Windows Server 2016 | 64-разрядная версия | [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] | .NET Framework 4.7<br/><br/> .NET framework 4.7.1 |
| Windows Server 2012 R2 | 64-разрядная версия | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] | [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/> .NET framework 4.7.1 |
| Windows Server 2012 (64-разрядная версия) | 64-разрядная версия| [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET framework 4.7.1 |
| Windows Server 2008 R2 с пакетом обновления 1 (SP1)|64-разрядная | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET framework 4.7.1 |
| Windows Server 2008 SP2|32- и 64-разрядные версии | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] |

 **Примечания.**

- [!INCLUDE[winserver8](../../../includes/winserver8-md.md)] включает [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], поэтому ее не требуется устанавливать. Аналогично [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] включает [!INCLUDE[net_v451](../../../includes/net-v451-md.md)].

- .NET Framework обеспечивает ограниченную поддержку для роли Server Core с Windows Server 2008 R2 SP1 или более поздней версии. В разделе [.NET функциональность Server Core](https://msdn.microsoft.com/library/ee391632.aspx) список неподдерживаемые API.

- Платформа .NET Framework не поддерживается в Windows Server 2008 R2 для систем на платформе Itanium.

- В Windows Server 2008 с пакетом обновления 2 (SP2) платформа .NET Framework не поддерживается в роли Server Core.

- Для обеспечения оптимального уровня совместимости и безопасности на всех платформах рекомендуется установить последнюю версию пакета обновления Windows и все критические обновления, доступные на [веб-сайте Центра обновления Windows](http://go.microsoft.com/fwlink/?LinkId=168461). В некоторых операционных системах может потребоваться установить последний пакет обновления Windows.

- В 64-разрядных операционных системах платформа .NET Framework поддерживает как среду WOW64 (32-разрядная обработка на 64-разрядном компьютере), так и собственную 64-разрядную обработку.

## <a name="see-also"></a>См. также

[Руководство по установке](../../../docs/framework/install/index.md)   
[Начало работы](../../../docs/framework/get-started/index.md)   
[Устранение неполадок с заблокированными установками и удалениями .NET Framework](../../../docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)
