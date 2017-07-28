---
title: "Узел службы Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "служба NT"
  - "образец размещения службы NT [Windows Communication Foundation]"
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# Узел службы Windows
В этом образце показана служба [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], размещенная в управляемой службе Windows.Службы Windows управляются с помощью компонента "Службы" в **Панели управления**, и их можно настраивать таким образом, чтобы они автоматически запускались после перезагрузки системы.Этот образец состоит из клиентской программы и программы службы Windows.Служба реализуется как программа EXE и содержит свой собственный код размещения.В других средах размещения, таких как служба активации Windows \(WAS\) или IIS, писать код размещения необязательно.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 После построения этой службы ее необходимо установить с помощью служебной программы Installutil.exe, как и все остальные службы Windows.Если предполагается вносить изменения в службу, необходимо сначала удалить ее с помощью команды `installutil /u`.Входящие в состав этого образца файлы Setup.bat и Cleanup.bat содержат команды для установки и запуска службы Windows, а также для отключения и удаления службы Windows.Служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может отвечать клиентам, только если запущена служба Windows.Если остановить службу Windows с помощью компонента "Службы" в **Панели управления**, а затем запустить клиент, при попытке клиента обратиться к службе возникнет исключение <xref:System.ServiceModel.EndpointNotFoundException>.Если перезапустить службу Windows и клиент, обращение произойдет успешно.  
  
 Код службы включает класс установщика, класс реализации службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который реализует контракт ICalculator и класс службы Windows, который выступает в роли основного приложения среды выполнения.Класс установщика, унаследованный от класса <xref:System.Configuration.Install.Installer>, позволяет устанавливать программу как службу NT с помощью средства Installutil.exe.Класс реализации службы `WcfCalculatorService` является службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которая реализует базовый контракт службы.Эта служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] размещается в классе службы Windows с именем `WindowsCalculatorService`.Чтобы считаться службой Windows, этот класс наследует от класса <xref:System.ServiceProcess.ServiceBase> и реализует методы [OnStart\(String\<xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> и <xref:System.ServiceProcess.ServiceBase.OnStop>.В методе [OnStart\(String\<xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> создается и открывается объект <xref:System.ServiceModel.ServiceHost> для типа `WcfCalculatorService`.В методе <xref:System.ServiceProcess.ServiceBase.OnStop> объект ServiceHost закрывается путем вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> объекта <xref:System.ServiceModel.ServiceHost>.Базовый адрес основного приложения настраивается с помощью элемента [\<добавление;\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md), который является дочерним элементом для элемента [\<baseAddresses\>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), который является дочерним элементом для элемента [\<хост\>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md), который является дочерним элементом для элемента [\<service\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md).  
  
 Определяемая конечная точка использует базовый адрес и элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).В следующем образце показана конфигурация базового адреса, а также конечной точки, предоставляющей службу CalculatorService.  
  
```  
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
  
 При выполнении образца запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  После построения решения запустите файл Setup.bat из командной строки [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с повышенными привилегиями, чтобы установить службу Windows с помощью программы Installutil.exe.Теперь служба должна отображаться в списке служб.  
  
4.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также  
 [Образцы размещения и сохраняемости AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)