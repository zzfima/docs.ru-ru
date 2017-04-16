---
title: "Трассировка событий Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
caps.latest.revision: 42
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 42
---
# Трассировка событий Windows
В этом образце показано, как реализовать сквозную трассировку \(E2E\) с помощью трассировки событий для Windows \(трассировка событий Windows\) и `ETWTraceListener`, предоставляемого с этим образцом.Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и включает трассировку событий Windows.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце предполагается, что пользователь знаком с [Трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 Каждый источник трассировки в модели трассировки <xref:System.Diagnostics> может иметь несколько прослушивателей трассировки, которые определяют место и способ трассировки данных.Тип прослушивателя определяет формат записи данных трассировки в журнал.В следующем образце кода показано, как добавить прослушиватель в конфигурацию.  
  
```  
  
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
  
 Перед использованием этого прослушивателя необходимо запустить сеанс трассировки событий Windows.Этот сеанс может быть запущен с помощью программ Logman.exe или Tracelog.exe.В этот образец включен файл SetupETW.bat, поэтому можно настроить сеанс трассировки событий Windows вместе с файлом CleanupETW.bat для закрытия сеанса и завершения выполнения файла журнала.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.Дополнительные сведения об этих средствах см. на сайте [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=56580](http://go.microsoft.com/fwlink/?LinkId=56580)  
  
 При использовании ETWTraceListener трассировки заносятся в журнал в двоичных файлах с расширением ETL.Если трассировка ServiceModel включена, все созданные трассировки отображаются в одном и том же файле.Используйте программу [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра файлов журнала с расширением ETL и SVCLOG.Средство просмотра создает сквозное представление системы, позволяющее выполнять трассировку сообщения на пути от источника в место назначения и точку потребления.  
  
 Прослушиватель трассировки событий Windows поддерживает циклическое ведение журнала.Чтобы включить эту функцию, перейдите в меню **Пуск**, выберите **Выполнить** и введите команду `cmd` для запуска командной консоли.В следующей команде замените параметр `<logfilename>` на имя требуемого файла журнала.  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 Коммутаторы `-f` и `-max` необязательны.Они указывают двоичный циклический формат и максимальный размер журнала \(1000 МБ\) соответственно.Параметр `-p` используется для указания поставщика трассировки.В этом примере `"{411a0819-c24b-428c-83e2-26b41091702e}"` является идентификатором GUID для образца поставщика трассировки событий Windows XML.  
  
 Для запуска сеанса введите следующую команду:  
  
```  
Logman start Wcf  
  
```  
  
 По завершении ведения журнала можно остановить сеанс с помощью следующей команды.  
  
```  
Logman stop Wcf  
```  
  
 В этом процессе создаются двоичные циклические журналы, которые можно обрабатывать с помощью любого средства, включая программу [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) или Tracerpt.  
  
 Дополнительные сведения об использовании альтернативного прослушивателя для выполнения циклического ведения журнала см. в образце [Циклическая трассировка](../../../../docs/framework/wcf/samples/circular-tracing.md).  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы построить решение, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
    > [!NOTE]
    >  Для запуска команд RegisterProvider.bat, SetupETW.bat и CleanupETW.bat необходимо использовать учетную запись локального администратора.При использовании [!INCLUDE[wv](../../../../includes/wv-md.md)] или позже необходимо также запустить командную строку с более высоким уровнем привилегий.Для этого щелкните правой кнопкой мыши значок командной строки и выберите команду **Запуск от имени администратора**.  
  
3.  Перед выполнением образца запустите файл RegisterProvider.bat на стороне клиента и сервера.При этом выполняется настройка получаемого файла ETWTracingSampleLog.etl для создания трассировок, которые можно считать с помощью программы Service Trace Viewer.Этот файл можно найти в папке C:\\logs.Если эта папка не существует, ее необходимо создать, в противном случае трассировки создаваться не будут.Затем запустите файл SetupETW.bat на клиентском и серверном компьютерах, чтобы начать сеанс трассировки событий Windows.Файл SetupETW.bat можно найти в папке CS\\Client.  
  
4.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5.  По завершении образца запустите файл CleanupETW.bat, чтобы завершить создание файла ETWTracingSampleLog.etl.  
  
6.  Откройте файл ETWTracingSampleLog.etl с помощью программы Service Trace Viewer.Будет предложено сохранить двоичный файл как файл с расширением SVCLOG.  
  
7.  Откройте только что созданный файл с расширением SVCLOG с помощью программы Service Trace Viewer, чтобы просмотреть трассировки событий Windows и трассировки ServiceModel.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## См. также  
 [Образцы наблюдения за AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)