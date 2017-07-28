---
title: "Расширение трассировки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Расширение трассировки
В этом образце показано, как расширить возможности трассировки [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], написав пользовательские трассировки действий в коде клиента и службы.Это позволяет пользователю создавать действия трассировки и группировать трассировки в логические пакеты работ.Кроме того, возможно согласование действий с помощью передач \(в рамках одной конечной точки\) и распространения \(между конечными точками\).В этом образце трассировка включается как для клиента, так и для службы.Дополнительные сведения о включении трассировки в файлах конфигурации клиента и службы см. в разделе [Трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 Этот образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## Трассировка и распространение действий  
 Пользовательская трассировка действий позволяет пользователям создавать собственные действия трассировки для объединения трассировок в логические пакеты работ, согласовывать действия с помощью передач и распространения, а также снижать расходы производительности, связанные с трассировкой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(например, место на диске, занимаемое файлом журнала\).  
  
### Добавление пользовательских источников  
 Пользовательские трассировки можно добавлять как в код клиента, так и в код службы.Добавление источников трассировки в файл конфигурации клиента или служб позволяет записывать и отображать эти пользовательские трассировки, используя [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).В следующем примере кода показано, как добавить в файл конфигурации пользовательский источник трассировки с именем `ServerCalculatorTraceSource`.  
  
```  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### Согласование действий  
 Для непосредственного согласования действий между конечными точками в источнике трассировки `System.ServiceModel` атрибут `propagateActivity` должен иметь значение `true`.Кроме того, для распространения трассировки без действий [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] необходимо отключить трассировку действия ServiceModel.Это показано в следующем примере кода.  
  
> [!NOTE]
>  Отключение трассировки действия ServiceModel не эквивалентно указанию значения off для уровня трассировки, обозначаемого свойством `switchValue`.  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### Снижение нагрузки на производительность  
 Установка для свойства `ActivityTracing` значения off в трассировке `System.ServiceModel` создает файл трассировки, который содержит только пользовательские трассировки действий без включения каких\-либо трассировок действий ServiceModel.В результате уменьшится размер файла журнала.Однако при этом будет потеряна возможность согласования трассировок обработки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
##### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также  
 [Образцы наблюдения за AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)