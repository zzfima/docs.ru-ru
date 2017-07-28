---
title: "How to: Add Installers to Your Service Application | Microsoft Docs"
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
  - "installation components, adding to services"
  - "installers, adding to services"
  - "Windows Service applications, adding installers"
  - "services, adding installers"
  - "ServiceInstaller class, adding installers to services"
  - "ServiceProcessInstaller class, adding installers to services"
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 14
---
# How to: Add Installers to Your Service Application
В состав Visual Studio входят компоненты установки, предназначенные для установки ресурсов, связанных с приложениями служб.  Компоненты установки регистрируются в системе, в которой они устанавливаются, в качестве отдельной службы; после этого они дают знать о своем существовании диспетчеру управления службами.  При работе с приложениями служб для автоматического добавления в проект соответствующих установщиков можно воспользоваться ссылкой в окне "Свойства".  
  
> [!NOTE]
>  Значения свойств службы копируются в класс установщика из класса службы.  При изменении значений свойств в классе службы соответствующие значения в классе установщика автоматически обновляться не будут.  
  
 При добавлении установщика в проекте создается новый класс \(по умолчанию он называется `ProjectInstaller`\), а внутри этого класса создаются экземпляры соответствующих компонентов установки.  Этот класс служит для сбора и объединения всех нужных приложению компонентов установки.  Например, если добавить в приложение вторую службу и щелкнуть ссылку "Добавить установщик", то второй класс установщика создаваться не будет; вместо этого в уже существующий класс будет добавлен дополнительный компонент установки для второй службы.  
  
 Для правильной установки служб не требуется писать какой\-то особый код установщиков.  Тем не менее, иногда бывает нужно добавить в процесс установки дополнительную функциональность. Для этого может потребоваться изменить содержимое установщиков.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы добавить установщики в приложение службы, выполните следующие действия:  
  
1.  В **обозревателе решений** откройте представление **Конструктор** для службы, к в которую необходимо добавить компонент установки.  
  
2.  Щелкните фон конструктора для выбора самой службы, а не какого\-либо из ее элементов.  
  
3.  Щелкните правой кнопкой мыши в активном окне конструктора и выберите команду **Добавить установщик**.  
  
     В проект будет добавлен новый класс `ProjectInstaller` и два компонента установки <xref:System.ServiceProcess.ServiceProcessInstaller> и <xref:System.ServiceProcess.ServiceInstaller>, а значения свойств службы будут скопированы в компоненты.  
  
4.  Щелкните компонент <xref:System.ServiceProcess.ServiceInstaller> и убедитесь в том, что значение свойства <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> соответствует значению свойства <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> самой службы.  
  
5.  Чтобы задать способ запуска службы, щелкните компонент <xref:System.ServiceProcess.ServiceInstaller> и укажите соответствующее значение свойства <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>:  
  
    |Значение|Результат|  
    |--------------|---------------|  
    |<xref:System.ServiceProcess.ServiceStartMode>|После установки служба запускается вручную.  Дополнительные сведения см. в разделе [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode>|После любой перезагрузки компьютера служба будет запускаться сама.|  
    |<xref:System.ServiceProcess.ServiceStartMode>|Служба запускаться не будет.|  
  
6.  Для задания контекста безопасности, в котором должна выполняться служба, щелкните компонент <xref:System.ServiceProcess.ServiceProcessInstaller> и задайте соответствующие значения свойств.  Дополнительные сведения см. в разделе [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).  
  
7.  Необходимо перегрузить все методы, в которых должны выполняться дополнительные действия.  
  
8.  Повторите шаги 1–7 для всех остальных служб, имеющихся в проекте.  
  
    > [!NOTE]
    >  Для каждой дополнительной службы в проекте необходимо добавить в класс установщика `ProjectInstaller` дополнительный компонент <xref:System.ServiceProcess.ServiceInstaller>.  Компонент <xref:System.ServiceProcess.ServiceProcessInstaller>, добавленный на третьем шаге, работает со всеми имеющимися в проекте установщиками служб.  
  
## См. также  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md)   
 [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)