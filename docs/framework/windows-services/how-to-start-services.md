---
title: "How to: Start Services | Microsoft Docs"
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
  - "Windows Service applications, starting"
  - "services, starting"
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 14
---
# How to: Start Services
После установки службы ее необходимо запустить.  При запуске службы вызывается метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, принадлежащий классу службы.  Как правило, метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> определяет полезную функциональность службы.  После запуска служба остается активной до тех пор, пока она не будет вручную остановлена или приостановлена.  
  
 Службы можно настраивать на автоматический запуск или запуск вручную.  Служба, настроенная на автоматический запуск, запускается после включения или перезагрузки компьютера, на котором она установлена.  Служба, настроенная на запуск вручную, должна запускаться пользователем.  
  
> [!NOTE]
>  По умолчанию службы, созданные с помощью [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], настроены на запуск вручную.  
  
 Существует несколько способов запустить службу вручную — из **обозревателя серверов**, из **диспетчера управления службами** или непосредственно из программы с помощью компонента <xref:System.ServiceProcess.ServiceController>.  
  
 Чтобы задать порядок запуска службы, необходимо установить значение свойства <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> класса <xref:System.ServiceProcess.ServiceInstaller>.  
  
### Чтобы настроить способ запуска службы, выполните следующие действия:  
  
1.  После создания службы добавьте в нее необходимые установщики.  Для получения дополнительной информации см. [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  Выберите в конструкторе установщик службы, над которой ведется работа.  
  
3.  В окне **Свойства** задайте свойству <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> одно из следующих значений:  
  
    |Служба запускается|Задаваемое значение|  
    |------------------------|-------------------------|  
    |При перезагрузке компьютера|**Automatic**|  
    |По явному действию пользователя|**Вручную**|  
  
    > [!TIP]
    >  Чтобы запретить запуск службы, задайте для свойства <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> значение **Disabled**.  Это, к примеру, может понадобиться при многократной перезагрузке сервера: запретив автоматический запуск некоторых служб, можно уменьшить время перезагрузки.  
  
    > [!NOTE]
    >  Значения этих и других свойств можно изменить после установки службы.  
  
     Существует несколько способов запуска службы, свойству <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> которой присвоено значение **Manual**: с помощью **обозревателя серверов**, **диспетчера управления службами Windows** или программного кода.  Важно отметить, что в действительности не все эти способы приводят к запуску службы в контексте **диспетчера управления службами**; в **обозревателе серверов** и программном методе для запуска службы используется компонент\-контроллер.  
  
### Чтобы запустить службу вручную из обозревателя серверов, выполните следующие действия:  
  
1.  В окне **обозревателя серверов** добавьте требуемый сервер, если его нет в списке.  Для получения дополнительной информации см. [How to: Access and Initialize Server Explorer\/Database Explorer](../Topic/How%20to:%20Access%20and%20Initialize%20Server%20Explorer-Database%20Explorer.md).  
  
2.  Разверните узел **Службы** и выберите службу, которую необходимо запустить.  
  
3.  Щелкните правой кнопкой мыши имя службы и выберите команду **Пуск**.  
  
### Чтобы запустить службу вручную из диспетчера управления службами, выполните следующие действия:  
  
1.  Откройте **диспетчер управления службами** одним из следующих способов:  
  
    -   В Windows XP и Windows 2000 Professional щелкните правой кнопкой мыши значок **Мой компьютер** на рабочем столе и выберите пункт меню **Управление**.  В появившемся окне разверните узел **Службы и приложения**.  
  
         \-либо\-  
  
    -   В Windows Server 2003 и Windows 2000 Server нажмите кнопку **Пуск**, наведите указатель на пункт **Программы**, затем выберите **Администрирование** и **Службы**;  
  
        > [!NOTE]
        >  В системе Windows NT 4.0 это диалоговое окно можно открыть с помощью **панели управления**.  
  
     В разделе **Службы** диалогового окна содержится список служб.  
  
2.  Выберите службу из списка, щелкните ее правой кнопкой мыши и нажмите кнопку **Пуск**.  
  
### Чтобы запустить службу вручную из программного кода, выполните следующие действия:  
  
1.  Создайте экземпляр класса <xref:System.ServiceProcess.ServiceController> и настройте его на работу с необходимой службой.  
  
2.  Чтобы запустить службу, вызовите метод <xref:System.ServiceProcess.ServiceController.Start%2A>.  
  
## См. также  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Access and Initialize Server Explorer\/Database Explorer](../Topic/How%20to:%20Access%20and%20Initialize%20Server%20Explorer-Database%20Explorer.md)