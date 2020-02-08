---
title: Установка .NET Framework 3.5 в Windows 10, 8.1, 8
description: Сведения об установке платформы .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8.
ms.date: 07/16/2018
ms.openlocfilehash: cfe21c0821b8f3223301dcc802533e1aaf024a79
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965949"
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8

Платформа .NET Framework 3.5 может потребоваться для запуска приложений в Windows 10, Windows 8.1 и Windows 8. Эти инструкции можно использовать и для более ранних версий Windows.

## <a name="download-the-offline-installer"></a>Скачивание автономного установщика

Автономный установщик .NET Framework 3.5 с пакетом обновления 1 (SP1) доступен на [странице загрузки .NET Framework 3.5 SP1](https://dotnet.microsoft.com/download/dotnet-framework/net35-sp1). Его можно скачать для версий Windows, предшествовавших Windows 10.

## <a name="install-the-net-framework-35-on-demand"></a>Установка платформы .NET Framework 3.5 по запросу

Если вы попробуете запустить приложение, которому требуется платформа .NET Framework 3.5, может появиться следующее окно настройки. Выберите вариант **Установить этот компонент**, чтобы включить .NET Framework 3.5. Для использования этого варианта требуется подключение к Интернету.

![Снимок экрана: диалоговое окно установки .NET Framework](./media/dotnet-35-windows-10/dotnet-framework-installation-dialog.png)

### <a name="why-am-i-getting-this-pop-up"></a>Почему появляется это всплывающее окно?

Платформа .NET Framework разрабатывается корпорацией Майкрософт и предоставляет среду для выполнения приложений. Доступны различные ее версии. Многие компании разрабатывают приложения для выполнения на платформе .NET Framework, и они предназначены для определенных версий. Если появилось это всплывающее окно, вы пытаетесь запустить приложение, которое требует версии .NET Framework 3.5, но эта версия не установлена в вашей системе.

## <a name="enable-the-net-framework-35-in-control-panel"></a>Включение платформы .NET Framework 3.5 в панели управления

Вы можете самостоятельно включить .NET Framework 3.5 через панель управления Windows. Для использования этого варианта требуется подключение к Интернету.

1. Нажмите клавишу с логотипом Windows ![Снимок экрана: клавиша с логотипом Windows](./media/dotnet-35-windows-10/windows-keyboard-logo.png) на клавиатуре, введите "Компоненты Windows" и нажмите ВВОД. Откроется диалоговое окно **Включение и отключение компонентов Windows**.

2. Установите флажок **.NET Framework 3.5 (включает .NET 2.0 и 3.0)** , нажмите кнопку **OK** и перезагрузите компьютер при появлении соответствующего запроса.

   ![Снимок экрана: установка .NET с помощью панели управления](./media/dotnet-35-windows-10/dotnet-control-panel.png)

   Дочерние элементы для **активации Windows Communication Foundation (WCF) по HTTP** и **активации Windows Communication Foundation (WCF) по протоколу, отличному от HTTP**, предназначены для разработчиков и администраторов серверов, которые используют эту функцию. В других случаях их выбирать не нужно.

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>Устранение неполадок с установкой .NET Framework 3.5

Во время установки могут возникнуть ошибки 0x800f0906, 0x800f0907, 0x800f081f или 0x800F0922. В этом случае см. раздел [Ошибка установки .NET Framework 3.5: 0x800f0906, 0x800f0907 или 0x800F081F](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09), чтобы узнать решение этой проблемы.

Если вам по-прежнему не удается устранить проблему с установкой или у вас нет подключения к Интернету, вы можете попытаться установить платформу с установочного носителя Windows. Дополнительные сведения см. в разделе [Развертывание .NET Framework 3.5 с помощью системы обслуживания образов развертывания и управления ими (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism). Если у вас нет установочного носителя, см. сведения в разделе [Создание установочного носителя Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).

> [!WARNING]
> Если вы устанавливаете .NET Framework 3.5 не через центр обновления Windows, необходимо использовать источники только из той же соответствующей версии операционной системы Windows. Использование исходного пути, который не соответствует той же версии Windows, не помешает установке несовпадающей версии .NET Framework 3.5. Но система не будет поддерживаться и обслуживаться.
