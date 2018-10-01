---
title: Практическое руководство. Установка и удаление служб
ms.date: 03/30/2017
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
author: ghogen
ms.openlocfilehash: eb68809909c0550ea5fa5eab1f9d5ca6a069e314
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47232733"
---
# <a name="how-to-install-and-uninstall-services"></a>Практическое руководство. Установка и удаление служб
Если вы разрабатываете службу Windows с помощью платформы .NET Framework, можно быстро установить приложение службы с помощью командной служебной программы InstallUtil.exe. Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, необходимо использовать InstallShield. См. статью о [развертывании с помощью установщика Windows](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
> [!WARNING]
>  Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье. Вместо этого, определите, какая программа (или программный пакет) установила эту службы, а затем на панели управления в разделе **Установка и удаление программ** удалите эту программу. Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.  
  
 Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows. См. статью [Пошаговое руководство. Создание приложения-службы Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5. Это происходит потому, что перед запуском проекта сначала необходимо установить службу в проекте.  
  
> [!TIP]
>  Запустите **Обозреватель сервера** и убедитесь, что служба установлена или удалена. Дополнительные сведения см. в руководстве по получению доступа и инициализации обозревателя сервера и обозревателя базы данных.  
  
### <a name="to-install-your-service-manually"></a>Установка службы вручную  
  
1.  В ОС Windows в меню **Пуск** или на **начальном экране** последовательно выберите **Visual Studio**, **Инструменты Visual Studio** и **Командная строка разработчика**.  
  
     Появляется командная строка Visual Studio.  
  
2.  Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.  
  
3.  Запустите InstallUtil.exe из командной строки, указав исполняемый файл проекта в качестве параметра:  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     Если вы используете командную строку Visual Studio, путь системы должен указывать на InstallUtil.exe. Если нет, можно добавить его в путь или использовать полный путь для его вызова. Этот инструмент устанавливается с помощью платформы .NET Framework, и его путь — `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`. Например, для 32-разрядной платформы .NET Framework 4 или 4.5. *, если вашим каталогом установки Windows является C:\Windows, то путь — `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`. Для 64-разрядной версии .NET Framework 4 или 4.5.\* по умолчанию используется путь `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.  
  
### <a name="to-uninstall-your-service-manually"></a>Удаление службы вручную  
  
1.  В ОС Windows в меню **Пуск** или на **начальном экране** последовательно выберите **Visual Studio**, **Инструменты Visual Studio** и **Командная строка разработчика**.  
  
     Появляется командная строка Visual Studio.  
  
2.  Запустите InstallUtil.exe из командной строки, указав выходные данные проекта в качестве параметра:  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  Иногда после удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре. В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](https://technet.microsoft.com/library/cc742045.aspx).  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Installutil.exe (инструмент для установки)](../../../docs/framework/tools/installutil-exe-installer-tool.md)
