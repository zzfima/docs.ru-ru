---
title: Узел службы Windows
ms.date: 03/30/2017
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
ms.openlocfilehash: 83b40f467af933b5da69b859d990fbe4ba005928
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143529"
---
# <a name="windows-service-host"></a>Узел службы Windows
Этот пример демонстрирует службу Windows Communication Foundation (WCF), размещенную в управляемой службе Windows. Службы Windows управляются с помощью панели управления Службы **Applet** и могут быть настроены для автоматического запуска после перезагрузки системы. Этот образец состоит из клиентской программы и программы службы Windows. Служба реализуется как программа EXE и содержит свой собственный код размещения. В других средах размещения, таких как служба активации Windows (WAS) или IIS, писать код размещения необязательно.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 После построения этой службы ее необходимо установить с помощью служебной программы Installutil.exe, как и все остальные службы Windows. Если предполагается вносить изменения в службу, необходимо сначала удалить ее с помощью команды `installutil /u`. Входящие в состав этого образца файлы Setup.bat и Cleanup.bat содержат команды для установки и запуска службы Windows, а также для отключения и удаления службы Windows. Служба WCF может отвечать клиентам только в случае запуска службы Windows. Если вы останавливаете службу Windows, используя Applet службы <xref:System.ServiceModel.EndpointNotFoundException> из панели **управления** и запускайте клиент, происходит исключение, когда клиент пытается получить доступ к службе. Если перезапустить службу Windows и клиент, обращение произойдет успешно.  
  
 Код обслуживания включает класс установки, класс реализации службы WCF, который реализует контракт ICalculator, и класс службы Windows, который выступает в качестве хоста времени выполнения. Класс установщика, унаследованный от класса <xref:System.Configuration.Install.Installer>, позволяет устанавливать программу как службу NT с помощью средства Installutil.exe. Класс реализации `WcfCalculatorService`услуг, это служба WCF, которая реализует базовый контракт на обслуживание. Эта услуга WCF размещается в `WindowsCalculatorService`классе службы Windows под названием . Чтобы считаться службой Windows, этот класс наследует от класса <xref:System.ServiceProcess.ServiceBase> и реализует методы <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> и <xref:System.ServiceProcess.ServiceBase.OnStop>. В методе <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> создается и открывается объект <xref:System.ServiceModel.ServiceHost> для типа `WcfCalculatorService`. В методе <xref:System.ServiceProcess.ServiceBase.OnStop> объект ServiceHost закрывается путем вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> объекта <xref:System.ServiceModel.ServiceHost>. Базовый адрес узла настраивается с использованием [ \<элемента добавления>,](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) который является ребенком [ \<baseAddresses>, ](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)который является ребенком [ \<элемента>узла,](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) который является ребенком элемента [ \<службы>.](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
  
 Конечная точка, которая определена использует [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)базовый адрес и wsHttpBinding>. В следующем образце показана конфигурация базового адреса, а также конечной точки, предоставляющей службу CalculatorService.  
  
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
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. После того, как решение было построено, запустите Setup.bat с повышенной команды Visual Studio 2012 для установки службы Windows с помощью инструмента Installutil.exe. Теперь служба должна отображаться в списке служб.  
  
4. Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
## <a name="see-also"></a>См. также раздел

- [Образцы размещения и сохраняемости AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
