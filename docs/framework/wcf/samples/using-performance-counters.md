---
title: Использование счетчиков производительности
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143581"
---
# <a name="using-performance-counters"></a>Использование счетчиков производительности
В этом примере показано, как получить доступ к счетчикам производительности Windows Communication Foundation (WCF) и как создавать счетчики производительности, определяемые пользователем. Этот пример основан на [получении начала](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце клиент вызывает четыре метода службы `ICalculator`. Вызов данных методов осуществляется клиентом до тех пор, пока не будет прерван пользователем. Служба остается неизменной.  
  
 Счетчики производительности включаются в разделе diagnostics файла Web.config службы, как показано в следующем образце конфигурации.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 Эта задача также может быть выполнена с помощью [инструмента редактора конфигурации (SvcConfigEditor.exe).](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
  
 При включении счетчиков производительности для службы включен весь набор счетчиков производительности WCF. Платформа .NET Framework автоматически поддерживает данные о производительности на трех уровнях: `ServiceModelService`, `ServiceModelEndpoint` и `ServiceModelOperation`. На каждом из этих уровней имеются счетчики производительности, например "Calls", "Calls per Second" и "Security Calls Not Authorized".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
### <a name="to-view-performance-data"></a>Просмотр данных о производительности  
  
1. Запустите инструмент монитора производительности, нажав **кнопку Start,** **Run...** `perfmon` , введите и нажмите **OK,** или с панели управления, выберите **административные инструменты** и дважды нажмите **производительность.**  
  
    > [!NOTE]
    > Пока не начнется выполнение кода образца, добавить счетчики невозможно.  
  
2. Удалите доступные счетчики производительности, выбирая их и нажимая клавишу DELETE.  
  
3. Добавьте счетчики WCF, нажав на панель графика и выбрав **Счетчики добавления.** В диалоговом окне **Add Counters** выберите **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 или ServiceModelService 3.0.0.0** в поле списка объектов производительности. Выберите в списке нужные счетчики.  
  
    > [!NOTE]
    > Нет счетчиков производительности WCF для службы, если на компьютере нет служб WCF.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Включение счетчиков с помощью редактора конфигураций  
  
1. Откройте экземпляр программы SvcConfigEditor.exe.  
  
2. В меню файла нажмите **Открыть,** а затем нажмите **Config файл ...**.  
  
3. Перейдите в папку службы примера приложения и откройте файл Web.config.  
  
4. Нажмите **Диагностика** на дереве конфигурации.  
  
5. Переключить **счетчик производительности** в окне **диагностики,** чтобы показать "Все".  
  
6. Сохраните файл конфигурации и закройте редактор.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>См. также раздел

- [Образцы наблюдения за AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
