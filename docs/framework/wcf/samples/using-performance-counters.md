---
title: Использование счетчиков производительности
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 3e0a0199e93abe1218f7d9c052807cb94e911140
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716703"
---
# <a name="using-performance-counters"></a>Использование счетчиков производительности
В этом образце показано, как получить доступ к счетчикам производительности Windows Communication Foundation (WCF) и как создавать определяемые пользователем счетчики производительности. Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
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
  
 Эту задачу можно также выполнить с помощью [средства редактора конфигурации (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Если счетчики производительности включены, для службы включается весь набор счетчиков производительности WCF. Платформа .NET Framework автоматически поддерживает данные о производительности на трех уровнях: `ServiceModelService`, `ServiceModelEndpoint` и `ServiceModelOperation`. На каждом из этих уровней имеются счетчики производительности, например "Calls", "Calls per Second" и "Security Calls Not Authorized".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>Просмотр данных о производительности  
  
1. Запустите средство "монитор производительности", нажав кнопку **Пуск**, **выполните...** , введите `perfmon` и нажмите кнопку **ОК,** а затем на панели управления выберите пункт **Администрирование** и дважды щелкните элемент **производительность**.  
  
    > [!NOTE]
    > Пока не начнется выполнение кода образца, добавить счетчики невозможно.  
  
2. Удалите доступные счетчики производительности, выбирая их и нажимая клавишу DELETE.  
  
3. Добавьте счетчики WCF, щелкнув правой кнопкой мыши панель графа и выбрав пункт **Добавить счетчики**. В диалоговом окне **Добавление счетчиков** выберите **Сервицемоделоператион 3.0.0.0, Сервицемоделендпоинт 3.0.0.0 или сервицемоделсервице 3.0.0.0** в раскрывающемся списке Объект производительности. Выберите в списке нужные счетчики.  
  
    > [!NOTE]
    > Нет счетчиков производительности WCF для службы, если на компьютере не выполняются службы WCF.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Включение счетчиков с помощью редактора конфигураций  
  
1. Откройте экземпляр программы SvcConfigEditor.exe.  
  
2. В меню Файл выберите команду **Открыть** , а затем щелкните **файл конфигурации.** ...  
  
3. Перейдите в папку службы примера приложения и откройте файл Web.config.  
  
4. Щелкните **Диагностика** в дереве конфигурации.  
  
5. Чтобы отобразить "все", переключите **Счетчик производительности** в окне " **Диагностика** ".  
  
6. Сохраните файл конфигурации и закройте редактор.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>См. также:

- [Примеры мониторинга AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
