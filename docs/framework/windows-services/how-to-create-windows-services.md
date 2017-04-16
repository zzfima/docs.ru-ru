---
title: "How to: Create Windows Services | Microsoft Docs"
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
  - "Windows Service applications, creating"
  - "templates, Windows Service"
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
caps.latest.revision: 18
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 18
---
# How to: Create Windows Services
При создании службы можно использовать шаблон проекта Visual Studio, который называется **Служба Windows**.  Этот шаблон автоматически выполняет основную часть работы, ссылаясь на необходимые классы и пространства имен, устанавливая наследование от базового класса для служб и переопределяя некоторые методы, которые вы обычно хотите переопределять.  
  
> [!WARNING]
>  Шаблон проекта "Службы Windows" в экспресс\-выпуске Visual Studio отсутствует.  
  
 Для создания функциональной службы необходимо выполнить, как минимум, следующее:  
  
-   Задайте свойство <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>.  
  
-   Создайте установщики, необходимые для приложения службы.  
  
-   Переопределите и задайте код для методов <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> для настройки режимов поведения службы.  
  
### Создание приложения службы Windows  
  
1.  Создайте проект **Служба Windows**.  
  
    > [!NOTE]
    >  Инструкции по созданию службы без использования шаблона см. в разделе [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
2.  В окне **Свойства** установите свойство <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> для своей службы.  
  
     ![Задайте свойство ServiceName.](../../../docs/framework/windows-services/media/windowsservice-servicename.png "WindowsService\_ServiceName")  
  
    > [!NOTE]
    >  Значение <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства всегда должно соответствовать имени, указанному в классах установщика.  При изменении этого свойства необходимо также обновить свойство <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> классов установщика.  
  
3.  Установите любые из следующих свойств для определения режима работы службы.  
  
    |Свойство|Параметр|  
    |--------------|--------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|`True`, чтобы указать, что служба может принимать запросы на останов работы; `false` для предотвращения останова службы.|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|`True`, чтобы указать, что служба хочет принимать уведомления о выключении компьютера, на котором она работает, позволяя ему вызывать процедуру <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>.|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|`True`, чтобы указать, что служба может принимать запросы на приостановку или возобновление выполнения; `false` для предотвращения приостановки и возобновления работы службы.|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|`True` , чтобы указать, что служба может обрабатывать уведомления об изменениях состояния питания компьютера; `false` для предотвращения уведомления службы об этих изменениях.|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|`True` для внесения информационных записей в журнал событий приложения, когда служба выполняет некоторое действие; `false` для отключения этой функции.  Для получения дополнительной информации см. [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md). **Note:**  По умолчанию свойство <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> имеет значение `true`.|  
  
    > [!NOTE]
    >  Когда <xref:System.ServiceProcess.ServiceBase.CanStop%2A> ``  или <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> ``  имеют значение `false`, **Диспетчер управления службами** будет отключать соответствующие пункты меню для остановки, приостановки или продолжения работы службы.  
  
4.  Откройте редактор кода и введите данные для выполнения операций для процедур <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.  
  
5.  Переопределите все прочие методы, для которых необходимо определить функциональные возможности.  
  
6.  Добавить установщики, необходимые для приложения службы.  Для получения дополнительной информации см. [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
7.  Постройте свой проект, выбрав пункт **Построить решение** в меню **Построить**.  
  
    > [!NOTE]
    >  Не нажимайте клавишу F5 для запуска проекта — таким способом нельзя запустить проект службы.  
  
8.  Установите службу.  Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## См. также  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Log Information About Services](../../../docs/framework/windows-services/how-to-log-information-about-services.md)   
 [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md)   
 [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)   
 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)