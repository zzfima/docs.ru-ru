---
title: "Introduction to Windows Service Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceController"
helpviewer_keywords: 
  - "Windows Service applications, deploying"
  - "OnStop method"
  - "OnPause method"
  - "services, about services"
  - "Service class, Windows Service applications"
  - "framework services, creating services"
  - "ServiceController components, about Windows services"
  - "Win32OwnProcess service type"
  - "services, lifetime"
  - "OnContinue method"
  - "Windows Service applications, about Windows Service applications"
  - "services, states"
  - "service states"
  - "WaitForStatus method"
  - "Win32ShareProcess service type"
  - "Windows Service applications, lifetime"
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 17
---
# Introduction to Windows Service Applications
Службы Microsoft Windows, ранее называвшиеся службами NT, позволяют создавать исполняемые приложения, работающие продолжительное время и выполняющиеся в отдельной сессии Windows.  Эти службы не содержат элементов пользовательского интерфейса, могут быть остановлены и запущены повторно и способны автоматически запускаться при загрузке компьютера.  Эти особенности делают службы идеальным средством для использования на сервере, а также в ситуациях, когда необходима долговременно работающая функциональность, не мешающая работе пользователей на том же компьютере.  Кроме того, службы могут запускаться в контексте безопасности конкретной учетной записи Windows, отличающейся от текущего пользователя или учетной записи компьютера по умолчанию.  Дополнительные сведения о службах и сеансах Windows см. в документации Windows SDK в библиотеке MSDN.  
  
 Службы можно легко создавать путем создания приложений, которые устанавливаются в качестве служб.  Предположим, что нужно отслеживать данные счетчика производительности и реагировать на пороговые значения.  Можно написать приложение службы Windows, которое будет считывать эти показания, развернуть приложение и приступить к сбору и анализу данных.  
  
 Служба создается как проект Microsoft Visual Studio; в проект помещается код, определяющий, какие команды могут быть посланы службе, и действия, которые должны быть выполнены в ответ на эти команды.  Службе могут быть посланы команды запуска, остановки, приостановки и возобновления выполнения; также возможно выполнение настраиваемых команд.  
  
 После создания и сборки приложения для его установки необходимо запустить программу командной строки InstallUtil.exe и указать путь к исполняемому файлу службы.  В дальнейшем для настройки, запуска, остановки или приостановки этой службы можно использовать **Диспетчер управления службами**.  Часть этих действий может быть также выполнена через узел **Службы** в **обозревателе серверов** или с помощью класса <xref:System.ServiceProcess.ServiceController>.  
  
## Приложения\-службы и другие приложения Visual Studio  
 Работа приложений служб имеет ряд отличий от других типов проектов.  
  
-   Чтобы проект начал работать, исполняемый файл, созданный после компиляции проекта приложения службы, должен быть предварительно размещен на сервере.  Приложения служб нельзя отлаживать или запускать нажатием клавиш F5 или F11; также нельзя производить непосредственный запуск службы или пошаговую отладку ее кода.  Вместо этого необходимо установить и запустить службу, а затем использовать для отладки процесса данной службы отладчик.  Для получения дополнительной информации см. [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md).  
  
-   В отличие от проектов других типов, для приложений служб обязательно нужно создавать компоненты установки.  Компоненты установки устанавливают и регистрируют службу на сервере, а также используют **Диспетчер управления службами** Windows для создания соответствующей записи об этой службе.  Для получения дополнительной информации см. [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
-   Метод `Main` приложения службы должен послать команду запуска службам, входящим в состав проекта.  Метод `Run` загружает службы в **Диспетчер управления службами** соответствующего сервера.  При использовании шаблона проекта **Служба Windows** данный метод создается автоматически.  Необходимо помнить, что загрузка службы — не то же самое, что ее запуск.  Дополнительные сведения см. далее в разделе "Жизненный цикл службы".  
  
-   Приложения служб Windows выполняются в отдельной оконной станции, отличной от станции вошедшего пользователя.  Оконная станция — это безопасный объект, содержащий буфер обмена, набор глобальных атомов и группу объектов рабочего стола.  Поскольку оконная станция службы Windows не является интерактивной, диалоговые окна, создаваемые службой Windows, не будут отображаться и могут привести к зависанию программы.  Аналогичным образом, сообщения об ошибках должны записываться в журнал событий Windows, а не выводиться на экран.  
  
     Классы служб Windows, поддерживаемые .NET Framework, не поддерживают взаимодействие с интерактивными станциями, то есть станциями текущего пользователя.  В NET Framework также отсутствуют классы, представляющие станции и рабочие столы.  При необходимости организовать взаимодействие службы Windows с другими станциями следует использовать неуправляемый интерфейс API Windows.  Дополнительные сведения см. в документации по Windows SDK.  
  
     Взаимодействие службы Windows с пользователем или другими станциями должно быть тщательно спроектировано с учетом таких ситуаций, как отсутствие текущего пользователя или непредвиденный набор объектов рабочего стола пользователя.  В некоторых случаях более целесообразным будет создание приложения Windows, выполняющегося под управлением пользователя.  
  
-   Приложения служб Windows выполняются в собственном контексте безопасности и запускаются до того, как пользователь войдет в систему на компьютере, на котором они установлены.  Необходимо с осторожностью подходить к вопросу выбора учетной записи, от имени которой будет запускаться служба; службы, запущенные от имени системной учетной записи, имеют больше прав и привилегий, чем службы, запущенные от имени учетной записи пользователя.  
  
## Жизненный цикл службы  
 Жизненный цикл службы включает несколько состояний.  Сначала служба устанавливается на компьютер, на котором она будет работать.  При этом для проекта службы запускаются установщики, а сама служба устанавливается в **Диспетчер управлениями службами** этого компьютера.  **Диспетчер управлениями службами** является основным средством управления службами Windows.  
  
 После загрузки службы ее необходимо запустить.  После запуска служба может выполнять свои задачи.  Служба может быть запущена с помощью **Диспетчера управлениями службами**, с помощью **обозревателя серверов** или же путем вызова метода <xref:System.ServiceProcess.ServiceController.Start%2A>.  Метод <xref:System.ServiceProcess.ServiceController.Start%2A> передает управление методу <xref:System.ServiceProcess.ServiceBase.OnStart%2A> вызываемого приложения и выполняет содержащийся в нем код.  
  
 Служба может находиться в запущенном состоянии неограниченное время, пока она не будет остановлена или приостановлена, или же пока компьютер не будет выключен.  Существуют три основных состояния службы: <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus> или <xref:System.ServiceProcess.ServiceControllerStatus>.  Кроме того, служба может сообщать о состоянии ожидания выполнения команды: <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus>, или <xref:System.ServiceProcess.ServiceControllerStatus>.  Это говорит о том, что выполняется отправленная службе команда \(например, команда приостановки или запуска службы\).  Определить, в каком состоянии находится служба, можно с помощью свойства <xref:System.ServiceProcess.ServiceController.Status%2A>; метод <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> используется для выполнения какого\-либо действия при возникновении какого\-либо из этих состояний.  
  
 Служба может быть приостановлена, остановлена или продолжена с помощью **Диспетчера управления службами**, **обозревателя серверов** или же путем вызова соответствующих программных методов.  При каждом из этих действий может вызываться соответствующая процедура службы \(<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> или <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>\), где можно задать дополнительные действия при изменении состояния службы.  
  
## Типы служб  
 С помощью .NET Framework в Visual Studio можно создавать службы двух типов.  Если служба в процессе одна, то она относится к типу <xref:System.ServiceProcess.ServiceType>.  Службы, находящиеся в процессе совместно с другими службами, относятся к типу <xref:System.ServiceProcess.ServiceType>.  Получить тип службы можно с помощью свойства <xref:System.ServiceProcess.ServiceController.ServiceType%2A>.  
  
 При попытке считать значение этого свойства у служб, которые были созданы вне Visual Studio, могут быть получены и другие значения.  Дополнительные сведения см. в разделе <xref:System.ServiceProcess.ServiceType>.  
  
## Службы и компонент ServiceController  
 Компонент <xref:System.ServiceProcess.ServiceController> используется для подключения к установленной службе и изменения ее состояния. С помощью компонента <xref:System.ServiceProcess.ServiceController> можно запустить или остановить службу, приостановить ее или продолжить выполнение, а также отправить службе настраиваемую команду.  Однако при создании приложения службы нет необходимости в использовании компонента <xref:System.ServiceProcess.ServiceController>.  Фактически в большинстве случаев компонент <xref:System.ServiceProcess.ServiceController> должен находиться не в самом приложении службы Windows, а в отдельном приложении.  
  
 Для получения дополнительной информации см. <xref:System.ServiceProcess.ServiceController>.  
  
## Требования  
  
-   Службы должны создаваться с использованием проекта приложения **Служба Windows** или другого типа проекта .NET Framework, который наследует от класса <xref:System.ServiceProcess.ServiceBase> и при построении которого будет создан EXE\-файл.  
  
-   В состав проектов, содержащих службы Windows, должны входить компоненты установки самого проекта и его служб.  Для этого можно использовать настройки, задаваемые в окне **Свойства**.  Для получения дополнительной информации см. [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
## См. также  
 [Windows Service Applications](../../../docs/framework/windows-services/index.md)   
 [Service Application Programming Architecture](../../../docs/framework/windows-services/service-application-programming-architecture.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md)   
 [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)   
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)