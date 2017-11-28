---
title: "Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8"
description: "Сведения об установке платформы .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8."
author: rlander
ms.author: mairaw
keywords: ".NET Framework, установка"
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
