---
title: Трассировка ETW
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: 25a4281cbf5a9ad81a63eee13d768715eebedfb6
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837900"
---
# <a name="etw-tracing"></a>Трассировка ETW
В этом примере показано, как реализовать сквозную трассировку (E2E) с помощью трассировки событий для Windows (трассировка событий Windows) и `ETWTraceListener`, предоставляемого с этим примером. Образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и включает трассировку ETW.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом примере предполагается, что вы знакомы с [трассировкой и ведением журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 Каждый источник трассировки в модели трассировки <xref:System.Diagnostics> может иметь несколько прослушивателей трассировки, которые определяют место и способ трассировки данных. Тип прослушивателя определяет формат записи данных трассировки в журнал. В следующем образце кода показано, как добавить прослушиватель в конфигурацию.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 Перед использованием этого прослушивателя необходимо запустить сеанс трассировки событий Windows. Этот сеанс может быть запущен с помощью программ Logman.exe или Tracelog.exe. В этот образец включен файл SetupETW.bat, поэтому можно настроить сеанс трассировки событий Windows вместе с файлом CleanupETW.bat для закрытия сеанса и завершения выполнения файла журнала.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела. Дополнительные сведения об этих средствах см. в разделе <https://go.microsoft.com/fwlink/?LinkId=56580>  
  
 При использовании ETWTraceListener трассировки заносятся в журнал в двоичных файлах с расширением ETL. Если трассировка ServiceModel включена, все созданные трассировки отображаются в одном и том же файле. Используйте [средство Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра файлов журнала ETL и SVCLOG. Средство просмотра создает сквозное представление системы, позволяющее выполнять трассировку сообщения на пути от источника в место назначения и точку потребления.  
  
 Прослушиватель трассировки событий Windows поддерживает циклическое ведение журнала. Чтобы включить эту функцию, последовательно выберите **Пуск**, **выполнить** и введите `cmd`, чтобы запустить консоль командной строки. В следующей команде замените параметр `<logfilename>` на имя требуемого файла журнала.  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 Коммутаторы `-f` и `-max` необязательны. Они указывают двоичный циклический формат и максимальный размер журнала (1000 МБ) соответственно. Коммутатор `-p` используется для указания поставщика трассировки. В этом примере `"{411a0819-c24b-428c-83e2-26b41091702e}"` является идентификатором GUID для примера поставщика трассировки событий Windows XML.  
  
 Для запуска сеанса введите следующую команду:  
  
```console  
logman start Wcf  
```  
  
 По завершении ведения журнала можно остановить сеанс с помощью следующей команды.  
  
```console  
logman stop Wcf  
```  
  
 Этот процесс создает двоичные циклические журналы, которые можно обработать с помощью выбранного инструмента, включая [средство Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) или Tracerpt.  
  
 Вы также можете ознакомиться с примером [циклической трассировки](../../../../docs/framework/wcf/samples/circular-tracing.md) для получения дополнительных сведений о альтернативном прослушивателе для выполнения циклического ведения журнала.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
    > [!NOTE]
    > Для запуска команд RegisterProvider.bat, SetupETW.bat и CleanupETW.bat необходимо использовать учетную запись локального администратора. При использовании Windows Vista или более поздней версии необходимо также запустить командную строку с повышенными привилегиями. Для этого щелкните правой кнопкой мыши значок командной строки и выберите команду **Запуск от имени администратора**.  
  
3. Перед выполнением примера запустите файл RegisterProvider.bat на стороне клиента и сервера. При этом выполняется настройка получаемого файла ETWTracingSampleLog.etl для создания трассировок, которые можно считать с помощью программы Service Trace Viewer. Этот файл можно найти в папке C:\logs. Если эта папка не существует, ее необходимо создать, в противном случае трассировки создаваться не будут. Затем запустите файл SetupETW.bat на клиентском и серверном компьютерах, чтобы начать сеанс трассировки событий Windows. Файл SetupETW.bat можно найти в папке CS\Client.  
  
4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5. По завершении образца запустите файл CleanupETW.bat, чтобы завершить создание файла ETWTracingSampleLog.etl.  
  
6. Откройте файл ETWTracingSampleLog.etl с помощью программы Service Trace Viewer. Будет предложено сохранить двоичный файл как файл с расширением SVCLOG.  
  
7. Откройте только что созданный файл с расширением SVCLOG с помощью программы Service Trace Viewer, чтобы просмотреть трассировки событий Windows и трассировки ServiceModel.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a>См. также:

- [Примеры мониторинга AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
