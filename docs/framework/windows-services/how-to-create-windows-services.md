---
title: "Практическое руководство. Создание служб Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 7d93f8543b9e6e370827f5a666315d562e28ee76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-windows-services"></a>Практическое руководство. Создание служб Windows
При создании службы, можно использовать шаблон проекта Visual Studio называется **службы Windows**. Этот шаблон автоматически выполняет основную часть работы, ссылаясь на необходимые классы и пространства имен, устанавливая наследование от базового класса для служб и переопределяя некоторые методы, которые вы обычно хотите переопределять.  
  
> [!WARNING]
>  Шаблон проекта "Службы Windows" в экспресс-выпуске Visual Studio отсутствует.  
  
 Для создания функциональной службы необходимо выполнить, как минимум, следующее:  
  
-   Задайте свойство <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>.  
  
-   Создайте установщики, необходимые для приложения службы.  
  
-   Переопределите и задайте код для методов <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> для настройки режимов поведения службы.  
  
### <a name="to-create-a-windows-service-application"></a>Создание приложения службы Windows  
  
1.  Создание **службы Windows** проекта.  
  
    > [!NOTE]
    >  Инструкции по созданию службы без использования шаблона см. в разделе [как: запись службы программным образом](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
2.  В **свойства** задайте <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства для службы.  
  
     ![Задайте свойство ServiceName. ] (../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")  
  
    > [!NOTE]
    >  Значение <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства всегда должно соответствовать имени, указанному в классах установщика. При изменении этого свойства необходимо также обновить свойство <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> классов установщика.  
  
3.  Установите любые из следующих свойств для определения режима работы службы.  
  
    |Свойство|Параметр|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|`True`, чтобы указать, что служба может принимать запросы на останов работы; `false` для предотвращения останова службы.|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|`True`, чтобы указать, что служба хочет принимать уведомления о выключении компьютера, на котором она работает, позволяя ему вызывать процедуру <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>.|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|`True`, чтобы указать, что служба может принимать запросы на приостановку или возобновление выполнения; `false` для предотвращения приостановки и возобновления работы службы.|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|`True`Чтобы указать, что служба может обрабатывать уведомления об изменениях состояния питания компьютера; `false` для предотвращения службе оповещен этих изменений.|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|`True` для внесения информационных записей в журнал событий приложения, когда служба выполняет некоторое действие; `false` для отключения этой функции. Дополнительные сведения см. в разделе [как: сведения о журналам](../../../docs/framework/windows-services/how-to-log-information-about-services.md). **Примечание:** по умолчанию <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> равно `true`.|  
  
    > [!NOTE]
    >  Когда <xref:System.ServiceProcess.ServiceBase.CanStop%2A> или <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> присваиваются `false`, **диспетчера управления службами** отключит с соответствующими параметрами меню можно остановить, приостановить или продолжить работу службы.  
  
4.  Откройте редактор кода и введите данные для выполнения операций для процедур <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.  
  
5.  Переопределите все прочие методы, для которых необходимо определить функциональные возможности.  
  
6.  Добавить установщики, необходимые для приложения службы. Дополнительные сведения см. в разделе [как: добавление установщиков к приложению службы](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
7.  Постройте проект, выбрав **построить решение** из **построения** меню.  
  
    > [!NOTE]
    >  Не нажимайте клавишу F5 для запуска проекта — таким способом нельзя запустить проект службы.  
  
8.  Установите службу. Для получения дополнительной информации см. [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Создание службы программным способом](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)  
 [Практическое руководство. Добавление установщиков в приложение служб](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Практическое руководство. Запись сведений о службах в журнал](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [Практическое руководство. Запуск служб](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Практическое руководство. Назначение службам контекста безопасности](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)  
 [Практическое руководство. Установка и удаление служб](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
