---
title: "Использование счетчиков производительности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 84cbbf83c240ae11099e2c9646150c810a437e71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-performance-counters"></a>Использование счетчиков производительности
В этом образце показано, как получать доступ к счетчикам производительности [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и как создавать пользовательские счетчики производительности. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце клиент вызывает четыре метода службы `ICalculator`. Вызов данных методов осуществляется клиентом до тех пор, пока не будет прерван пользователем. Служба остается неизменной.  
  
 Счетчики производительности включаются в разделе diagnostics файла Web.config службы, как показано в следующем образце конфигурации.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 Эту задачу можно также выполнить с помощью [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Если включены счетчики производительности, это значит, что для службы включен полный набор счетчиков производительности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Платформа .NET Framework автоматически поддерживает данные о производительности на трех уровнях: `ServiceModelService`, `ServiceModelEndpoint` и `ServiceModelOperation`. На каждом из этих уровней имеются счетчики производительности, например "Calls", "Calls per Second" и "Security Calls Not Authorized".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Просмотр данных о производительности  
  
1.  Запустите средство мониторинга производительности, щелкнув **запустить**, **запуска...** , введите `perfmon` и нажмите кнопку **ОК,** или с помощью панели управления выберите **Администрирование** и дважды щелкните **производительности**.  
  
    > [!NOTE]
    >  Пока не начнется выполнение кода образца, добавить счетчики невозможно.  
  
2.  Удалите доступные счетчики производительности, выбирая их и нажимая клавишу DELETE.  
  
3.  Добавить [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] счетчики, щелкнув правой кнопкой мыши панель «Диаграмма» и выбрав **добавить счетчики**. В **добавить счетчики** выберите **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 или ServiceModelService 3.0.0.0** в объекте производительности раскрывающийся список. Выберите в списке нужные счетчики.  
  
    > [!NOTE]
    >  В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] нет счетчиков производительности для службы, если на компьютере не запущены службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Включение счетчиков с помощью редактора конфигураций  
  
1.  Откройте экземпляр программы SvcConfigEditor.exe.  
  
2.  В меню «Файл» выберите **откройте** и нажмите кнопку **файла конфигурации...** .  
  
3.  Перейдите в папку службы примера приложения и откройте файл Web.config.  
  
4.  Нажмите кнопку **диагностики** в дереве конфигурации.  
  
5.  Переключить **счетчика производительности** в **диагностики** окно для отображения 'All'.  
  
6.  Сохраните файл конфигурации и закройте редактор.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>См. также  
 [Примеры мониторинга AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
