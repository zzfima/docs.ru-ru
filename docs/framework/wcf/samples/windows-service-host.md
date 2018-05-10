---
title: Узел службы Windows
ms.date: 03/30/2017
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
ms.openlocfilehash: 06bb17ca174eef069889381460b77f6b50902f70
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="windows-service-host"></a>Узел службы Windows
В этом примере демонстрируется службы Windows Communication Foundation (WCF), размещенной в управляемой службе Windows. Службы Windows управляются с помощью компонента "службы" в **панели управления** и может быть настроен для автоматического запуска после перезагрузки системы. Этот образец состоит из клиентской программы и программы службы Windows. Служба реализуется как программа EXE и содержит свой собственный код размещения. В других средах размещения, таких как служба активации Windows (WAS) или IIS, писать код размещения необязательно.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 После построения этой службы ее необходимо установить с помощью служебной программы Installutil.exe, как и все остальные службы Windows. Если предполагается вносить изменения в службу, необходимо сначала удалить ее с помощью команды `installutil /u`. Входящие в состав этого образца файлы Setup.bat и Cleanup.bat содержат команды для установки и запуска службы Windows, а также для отключения и удаления службы Windows. Служба WCF только может отвечать клиентам, если служба Windows запущена. Если остановить службу Windows с помощью компонента "службы" из **панели управления** и запустите клиент, <xref:System.ServiceModel.EndpointNotFoundException> исключение возникает, когда клиент пытается получить доступ к службе. Если перезапустить службу Windows и клиент, обращение произойдет успешно.  
  
 Код службы включает класс установщика, класс реализации службы WCF, который реализует контракт ICalculator и класс службы Windows, который выступает в качестве узла во время выполнения. Класс установщика, унаследованный от класса <xref:System.Configuration.Install.Installer>, позволяет устанавливать программу как службу NT с помощью средства Installutil.exe. Класс реализации службы `WcfCalculatorService`, — это служба WCF, которая реализует базовый контракт службы. Эта служба WCF размещается в классе службы Windows с именем `WindowsCalculatorService`. Чтобы считаться службой Windows, этот класс наследует от класса <xref:System.ServiceProcess.ServiceBase> и реализует методы <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> и <xref:System.ServiceProcess.ServiceBase.OnStop>. В методе <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> создается и открывается объект <xref:System.ServiceModel.ServiceHost> для типа `WcfCalculatorService`. В методе <xref:System.ServiceProcess.ServiceBase.OnStop> объект ServiceHost закрывается путем вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> объекта <xref:System.ServiceModel.ServiceHost>. Базовый адрес узла настраивается с помощью [ \<Добавить >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) элемент, который является дочерним для [ \<baseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), который является дочерним по отношению [ \<узла >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) элемент, который является дочерним для [ \<службы >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) элемента.  
  
 Конечная точка, который определен использует базовый адрес и [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). В следующем образце показана конфигурация базового адреса, а также конечной точки, предоставляющей службу CalculatorService.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.WcfCalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <host>  
      <baseAddresses>  
        <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
      </baseAddresses>  
    </host>  
    <!-- This endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service.  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
```  
  
 При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  После построения решения запустите файл Setup.bat из командной строки [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с повышенными привилегиями, чтобы установить службу Windows с помощью программы Installutil.exe. Теперь служба должна отображаться в списке служб.  
  
4.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>См. также  
 [Образцы размещения и сохраняемости образцы](http://go.microsoft.com/fwlink/?LinkId=193961)
