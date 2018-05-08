---
title: Практическое руководство. Добавление установщиков в приложение служб
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
author: ghogen
manager: douge
ms.openlocfilehash: faece1d7ee752e4c17f39027ff8a97fc95ed451b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-installers-to-your-service-application"></a>Практическое руководство. Добавление установщиков в приложение служб
В состав Visual Studio входят компоненты установки, которые можно установить ресурсы, связанные с приложениями служб. Компоненты установки регистрируются в качестве отдельных службы в системе, к которой он устанавливается и. При работе с приложением службы, можно выбрать ссылку в окне «Свойства» для автоматического добавления соответствующих установщиков в проекте.  
  
> [!NOTE]
>  Значения свойств службы копируются из класса службы в класс установщика. При обновлении значения свойств в классе службы, они не обновляются автоматически в программу установки.  
  
 При добавлении установщика в проект новый класс (которая, по умолчанию называется `ProjectInstaller`) создается в проекте, а экземпляры установку компонентов создаются внутри него. Этот класс служит центральной точки для всех компонентов установки проекту требуется. Например если добавить второй службы в приложение и нажмите кнопку Добавить установщик, второй класс установщика не создается; Вместо этого в существующий класс добавляется дополнительный компонент установки для второй службы.  
  
 Необходимо сделать любое специальное кодирование установщиков для правильной установки служб. Однако иногда может потребоваться изменить содержимое установщики, если вам нужно добавить специальные функции в процессе установки.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-installers-to-your-service-application"></a>Добавление установщиков в приложение службы  
  
1.  В **обозревателе решений**, доступ **разработки** представление для службы, для которого требуется добавить компонент установки.  
  
2.  Щелкните фон конструктора, чтобы выбрать службу себе, а не его элементов.  
  
3.  С помощью конструктора в фокус, щелкните правой кнопкой мыши и выберите команду **Добавить установщик**.  
  
     Новый класс `ProjectInstaller`и два компонента установки <xref:System.ServiceProcess.ServiceProcessInstaller> и <xref:System.ServiceProcess.ServiceInstaller>, добавляются к проекту и значения свойств для службы будут скопированы в компоненты.  
  
4.  Нажмите кнопку <xref:System.ServiceProcess.ServiceInstaller> компонента и убедитесь, что значение <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> задано значение совпадает со значением <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> свойство самой службы.  
  
5.  Чтобы определить, как будет запущена служба, щелкните <xref:System.ServiceProcess.ServiceInstaller> компонента и задать <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> свойства соответствующее значение.  
  
    |Значение|Результат|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|Служба должна быть запущена вручную после установки. Дополнительные сведения см. в разделе [как: запуск служб](../../../docs/framework/windows-services/how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|Служба будет запускаться сама при перезагрузке компьютера.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|Не удается запустить службу.|  
  
6.  Чтобы определить контекст безопасности, в котором будет выполняться служба, щелкните <xref:System.ServiceProcess.ServiceProcessInstaller> компонента и задайте соответствующие значения свойств. Дополнительные сведения см. в разделе [как: укажите контекст безопасности для службы](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).  
  
7.  Переопределите все методы, для которых необходимо выполнить дополнительные действия.  
  
8.  Повторите шаги 1 – 7 для каждой дополнительной службы в проекте.  
  
    > [!NOTE]
    >  Для каждой дополнительной службы в проекте, необходимо добавить дополнительный <xref:System.ServiceProcess.ServiceInstaller> компонента в проект `ProjectInstaller` класса. <xref:System.ServiceProcess.ServiceProcessInstaller> Компонент, добавленный на третьем шаге работает со всеми отдельными установщиками служб в проекте.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Установка и удаление служб](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Практическое руководство. Запуск служб](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Практическое руководство. Назначение службам контекста безопасности](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
