---
title: "Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8"
description: "Сведения об установке платформы .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8."
author: rlander
ms.author: mairaw
ms.date: 11/27/2017
ms.topic: article
ms.prod: .net-framework
ms.workload: dotnet
ms.openlocfilehash: ca56bfb37cee60ab014dada7b5d72b74b375dd7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8

Платформа .NET Framework 3.5 может потребоваться для запуска приложений в Windows 10, Windows 8.1 и Windows 8. Эти инструкции можно использовать и для более ранних версий Windows.

## <a name="install-the-net-framework-35-on-demand"></a>Установка платформы .NET Framework 3.5 по запросу

Если вы попробуете запустить приложение, которому требуется платформа .NET Framework 3.5, может появиться следующее окно настройки. Выберите вариант **Установить этот компонент**, чтобы включить .NET Framework 3.5. Для использования этого варианта требуется подключение к Интернету.

![Диалоговое окно установки .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a>Включение платформы .NET Framework 3.5 в панели управления

Вы можете самостоятельно включить .NET Framework 3.5 через панель управления Windows. Для использования этого варианта требуется подключение к Интернету.

1. Нажмите клавишу Windows ![с логотипом Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) на клавиатуре, введите "Компоненты Windows" и нажмите клавишу ВВОД. Откроется диалоговое окно **Включение и отключение компонентов Windows**.

2. Установите флажок **.NET Framework 3.5 (включает .NET 2.0 и 3.0)**, нажмите кнопку **OK** и перезагрузите компьютер при появлении соответствующего запроса.

   ![Установка .NET с помощью панели управления](./media/dotnet-control-panel.png)

   Дочерние элементы для **активации Windows Communication Foundation (WCF) по HTTP** и **активации Windows Communication Foundation (WCF) по протоколу, отличному от HTTP**, предназначены для разработчиков и администраторов серверов, которые используют эту функцию. В других случаях их выбирать не нужно.

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>Устранение неполадок с установкой .NET Framework 3.5

Во время установки могут возникнуть ошибки 0x800f0906, 0x800f0907, 0x800f081f или 0x800F0922. В этом случае обратитесь к разделу [Ошибка установки .NET Framework 3.5: 0x800f0906, 0x800f0907 или 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09).

Если ни один из способов, приведенных в предыдущей статье, не подходит или у вас нет подключения к Интернету, необходимо использовать установочный носитель Windows. Дополнительные сведения см. в разделе [Развертывание .NET Framework 3.5 с помощью системы обслуживания образов развертывания и управления ими (DISM)](https://technet.microsoft.com/library/Dn482069.aspx). Если у вас нет установочного носителя, см. сведения в разделе [Создание установочного носителя Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).