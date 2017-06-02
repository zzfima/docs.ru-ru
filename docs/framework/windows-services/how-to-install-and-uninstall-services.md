---
title: "How to: Install and Uninstall Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows Service applications, deploying"
  - "services, uninstalling"
  - "services, installing"
  - "installing Windows Services"
  - "uninstalling applications, Windows Services"
  - "installation, Windows Services"
  - "uninstalling Windows Services"
  - "installutil.exe tool"
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
caps.latest.revision: 19
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 17
---
# How to: Install and Uninstall Services
Если вы разрабатываете службу Windows с помощью платформы .NET Framework, можно быстро установить приложение службы с помощью командной служебной программы InstallUtil.exe.  Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, необходимо использовать InstallShield.  См. раздел [Развертывание с помощью установщика Windows](http://msdn.microsoft.com/ru-ru/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
> [!WARNING]
>  Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье.  Вместо этого, определите, какая программа или программный пакет установила службы, а затем выберите **Установка и удаление программ** на панели управления для удаления этой программы.  Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.  
  
 Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows.  См. раздел [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5.  Это происходит потому, что перед запуском проекта сначала необходимо установить службу в проекте.  
  
> [!TIP]
>  Можно запустить **Обозреватель серверов** и убедиться, что служба установлена или удалена.  Дополнительные сведения см. в разделе [How to: Access and Initialize Server Explorer\/Database Explorer](../Topic/How%20to:%20Access%20and%20Initialize%20Server%20Explorer-Database%20Explorer.md).  
  
### Установка службы вручную  
  
1.  В ОС Windows в меню **Пуск** или на экране **Пуск** выберите **Visual Studio**, **Инструменты Visual Studio**, **Командная строка разработчика**.  
  
     Появляется командная строка Visual Studio.  
  
2.  Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.  
  
3.  Запустите InstallUtil.exe из командной строки, указав исполняемый файл проекта в качестве параметра:  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     Если вы используете командную строку Visual Studio, путь системы должен указывать на InstallUtil.exe.  Если нет, можно добавить его в путь или использовать полный путь для его вызова.  Этот инструмент устанавливается с помощью платформы .NET Framework, и его путь — `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.  Например, для 32\-разрядной платформы .NET Framework 4 или 4.5. \*, если вашим каталогом установки Windows является C:\\Windows, то путь — `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.  Для 64\-разрядной версии платформы .NET Framework 4 или 4.5. \* по умолчанию используется путь `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.  
  
### Удаление службы вручную  
  
1.  В ОС Windows в меню **Пуск** или на экране **Пуск** выберите **Visual Studio**, **Инструменты Visual Studio**, **Командная строка разработчика**.  
  
     Появляется командная строка Visual Studio.  
  
2.  Запустите InstallUtil.exe из командной строки, указав выходные данные проекта в качестве параметра:  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  Иногда после удаления исполняемого файла для службы сама служба может по\-прежнему присутствовать в реестре.  В этом случае для удаления записи для службы из реестра используйте команду [sc delete](http://technet.microsoft.com/library/cc742045.aspx).  
  
## См. также  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [Installutil.exe \(Installer Tool\)](../../../docs/framework/tools/installutil-exe-installer-tool.md)