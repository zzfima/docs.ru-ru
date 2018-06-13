---
title: Использование счетчиков производительности
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 8784b4a481b8313d370aad1d8f265dcb44ab3ed6
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807323"
---
# <a name="using-performance-counters"></a>Использование счетчиков производительности
Этот образец демонстрирует способы доступа к счетчикам производительности службы Windows Communication Foundation (WCF) и создать пользовательские счетчики. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
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
  
 Если включены счетчики производительности, для службы включен полный набор счетчиков производительности WCF. Платформа .NET Framework автоматически поддерживает данные о производительности на трех уровнях: `ServiceModelService`, `ServiceModelEndpoint` и `ServiceModelOperation`. На каждом из этих уровней имеются счетчики производительности, например "Calls", "Calls per Second" и "Security Calls Not Authorized".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Просмотр данных о производительности  
  
1.  Запустите средство мониторинга производительности, щелкнув **запустить**, **запуска...** , введите `perfmon` и нажмите кнопку **ОК,** или с помощью панели управления выберите **Администрирование** и дважды щелкните **производительности**.  
  
    > [!NOTE]
    >  Пока не начнется выполнение кода образца, добавить счетчики невозможно.  
  
2.  Удалите доступные счетчики производительности, выбирая их и нажимая клавишу DELETE.  
  
3.  Добавить счетчики WCF, щелкнув правой кнопкой мыши панель «Диаграмма» и выбрав **добавить счетчики**. В **добавить счетчики** выберите **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 или ServiceModelService 3.0.0.0** в объекте производительности раскрывающийся список. Выберите в списке нужные счетчики.  
  
    > [!NOTE]
    >  Нет счетчиков производительности нет WCF для службы, службы WCF не запущен на компьютере.  
  
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>См. также  
 [Примеры мониторинга AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
