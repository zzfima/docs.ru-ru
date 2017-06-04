---
title: "WS Dual Http | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# WS Dual Http
В образце двустороннего HTTP\-взаимодействия показано, как настроить привязку `WSDualHttpBinding`.Этот образец содержит консольную программу клиента \(EXE\) и библиотеку службы \(DLL\), размещаемую в службах IIS.Служба реализует дуплексный контракт.Контракт определяется интерфейсом `ICalculatorDuplex`, который предоставляет математические операции \(добавить, вычесть, умножить и разделить\).В этом образце интерфейс `ICalculatorDuplex` позволяет клиенту выполнять математические операции, вычисляя результат выполнения в сеансе.Независимо от этого служба возвращает результаты в интерфейсе `ICalculatorDuplexCallback`.Для дуплексного контракта требуется сеанс, поскольку необходимо установить контекст для корреляции набора сообщений, обмен которыми осуществляется между клиентом и службой.Привязка `WSDualHttpBinding` поддерживает дуплексное взаимодействие.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для этого образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`  
  
 Чтобы настроить конечную точку службы с привязкой `WSDualHttpBinding`, укажите привязку в конфигурации конечной точки, как показано в примере.  
  
```  
<endpoint address=""  
         binding="wsDualHttpBinding"  
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
```  
  
 На стороне клиента необходимо настроить адрес, который будет использоваться сервером для подключения к клиенту, как показано в следующем образце конфигурации.  
  
```  
<system.serviceModel>  
  <client>  
    <endpoint address=  
         "http://localhost/servicemodelsamples/service.svc"   
         binding="wsDualHttpBinding"   
         bindingConfiguration="Binding1"   
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
  </client>  
  
  <bindings>  
    <!-- Configure a WSDualHttpBinding that supports duplex -->  
    <!-- communication. -->  
    <wsDualHttpBinding>  
      <binding name="Binding1"  
               clientBaseAddress="http://localhost:8000/myClient/"  
               useDefaultWebProxy="true"  
               bypassProxyOnLocal="false">  
      </binding>  
    </wsDualHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Press <ENTER> to terminate client once the output is displayed.  
  
Result(100)  
Result(50)  
Result(882.5)  
Result(441.25)  
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)  
  
```  
  
 При выполнении образца видны отправляемые службой сообщения, возвращаемые клиенту в интерфейсе обратного вызова.Отображается каждый промежуточный результат с последующим отображением всей формулы после завершения всех операций.Чтобы закрыть клиент, нажмите клавишу ВВОД.  
  
### Настройка, построение и выполнение образца  
  
1.  Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Убедитесь, что выполнена процедура, описанная в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Чтобы создать версию решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!IMPORTANT]
    >  Если пример выполняется на нескольких компьютерах, обязательно замените "localhost" в атрибуте `address` элемента [endpoint](http://msdn.microsoft.com/ru-ru/13aa23b7-2f08-4add-8dbf-a99f8127c017) и атрибуте `clientBaseAddress` элемента [\<привязка\>](../../../../docs/framework/misc/binding.md), расположенного в элементе [\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md), именем соответствующего компьютера, как показано ниже.  
  
    ```  
    <client>  
        <endpoint name = ""  
          address=  
         "http://service_machine_name/servicemodelsamples/service.svc"  
        />  
    </client>  
    ...  
    <wsDualHttpBinding>  
        <binding name="DuplexBinding" clientBaseAddress=  
            "http://client_machine_name:8000/myClient/">  
        </binding>  
    </wsDualHttpBinding>  
    ```  
  
## См. также