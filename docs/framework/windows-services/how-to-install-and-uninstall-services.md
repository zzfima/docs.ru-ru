---
title: "Практическое руководство. Установка и удаление служб"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 1fcbc8e7a84b16d244561e0cd69f8661236e63de
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-install-and-uninstall-services"></a>Практическое руководство. Установка и удаление служб
Если вы разрабатываете службу Windows с помощью платформы .NET Framework, можно быстро установить приложение службы с помощью командной служебной программы InstallUtil.exe. Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, необходимо использовать InstallShield. В разделе [развертывания установщика Windows](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
> [!WARNING]
>  Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье. Вместо этого определить, какая программа или программный пакет установила службы и выберите **Установка и удаление программ** панели управления для удаления этой программы. Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.  
  
 Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows. В разделе [Пошаговое руководство: создание Windows службы приложения в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5. Это происходит потому, что перед запуском проекта сначала необходимо установить службу в проекте.  
  
> [!TIP]
>  Можно запустить **обозревателя серверов** и убедитесь, что служба установлена или удалена. Дополнительные сведения см. в разделе как: подключение и инициализация обозревателя базы данных обозревателя сервера.  
  
### <a name="to-install-your-service-manually"></a>Установка службы вручную  
  
1.  В ОС Windows **запустить** меню или **запустить** выберите **Visual Studio** , **набора средств Visual Studio**, **разработчика Командной строки**.  
  
     Появляется командная строка Visual Studio.  
  
2.  Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.  
  
3.  Запустите InstallUtil.exe из командной строки, указав исполняемый файл проекта в качестве параметра:  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     Если вы используете командную строку Visual Studio, путь системы должен указывать на InstallUtil.exe. Если нет, можно добавить его в путь или использовать полный путь для его вызова. Этот инструмент устанавливается с помощью платформы .NET Framework, и его путь — `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`. Например, для 32-разрядной платформы .NET Framework 4 или 4.5. *, если вашим каталогом установки Windows является C:\Windows, то путь — `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`. Для 64-разрядной версии платформы .NET Framework 4 или 4.5. \*, путь по умолчанию — `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.  
  
### <a name="to-uninstall-your-service-manually"></a>Удаление службы вручную  
  
1.  В ОС Windows **запустить** меню или **запустить** выберите **Visual Studio**, **набора средств Visual Studio**, **разработчика Командной строки**.  
  
     Появляется командная строка Visual Studio.  
  
2.  Запустите InstallUtil.exe из командной строки, указав выходные данные проекта в качестве параметра:  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  Иногда после удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре. В этом случае команда [sc delete](http://technet.microsoft.com/library/cc742045.aspx) удалить запись для службы из реестра.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Installutil.exe (инструмент для установки)](../../../docs/framework/tools/installutil-exe-installer-tool.md)
