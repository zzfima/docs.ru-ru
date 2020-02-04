---
title: Расширение трассировки
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: c6d62f6c334261b0dc897a1c1a2cd71d40ee4f51
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734924"
---
# <a name="extending-tracing"></a>Расширение трассировки
В этом примере показано, как расширить функцию трассировки Windows Communication Foundation (WCF) путем написания пользовательских трассировок действий в клиенте и в коде службы. Это позволяет пользователю создавать действия трассировки и группировать трассировки в логические пакеты работ. Кроме того, возможно согласование действий с помощью передач (в рамках одной конечной точки) и распространения (между конечными точками). В этом образце трассировка включается как для клиента, так и для службы. Дополнительные сведения о включении трассировки в файлах конфигурации клиента и службы см. в разделе [Трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a>Трассировка и распространение действий  
 Определяемая пользователем трассировка действий позволяет пользователю создавать собственные действия трассировки для группирования трассировок в логические единицы работы, сопоставлять действия посредством передачи и распространения, а также уменьшить затраты на производительность трассировки WCF (например, стоимость места на диске файла журнала).  
  
### <a name="adding-custom-sources"></a>Добавление пользовательских источников  
 Пользовательские трассировки можно добавлять как в код клиента, так и в код службы. Добавление источников трассировки в файлы конфигурации клиента или службы позволяет записывать и отображать эти пользовательские трассировки в средстве [Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). В следующем примере кода показано, как добавить в файл конфигурации пользовательский источник трассировки с именем `ServerCalculatorTraceSource`.  
  
```xml  
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
  
### <a name="correlating-activities"></a>Согласование действий  
 Для непосредственного согласования действий между конечными точками в источнике трассировки `propagateActivity` атрибут `true` должен иметь значение `System.ServiceModel`. Кроме того, для распространения трассировок без выполнения действий WCF трассировка действий ServiceModel должна быть отключена. Это показано в следующем примере кода.  
  
> [!NOTE]
> Отключение трассировки действия ServiceModel не эквивалентно указанию значения off для уровня трассировки, обозначаемого свойством `switchValue`.  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a>Снижение нагрузки на производительность  
 Установка для свойства `ActivityTracing` значения off в трассировке `System.ServiceModel` создает файл трассировки, который содержит только пользовательские трассировки действий без включения каких-либо трассировок действий ServiceModel. В результате уменьшится размер файла журнала. Однако возможность корреляции трассировок обработки WCF теряется.  
  
##### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>См. также раздел

- [Примеры мониторинга AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
