---
title: Надежный сеанс по протоколу HTTPS с использованием пользовательской привязки
ms.date: 03/30/2017
ms.assetid: 16aaa80d-3ffe-47c4-8b16-ec65c4d25f8d
ms.openlocfilehash: 051e7f56662a2ca67018ae7dd29189ff50245fc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183875"
---
# <a name="custom-binding-reliable-session-over-https"></a>Надежный сеанс по протоколу HTTPS с использованием пользовательской привязки
В этом образце показано использование безопасности транспорта SSL с надежными сеансами. Надежные сеансы реализуют протокол WS-ReliableMessaging. Чтобы создать безопасный надежный сеанс, можно объединить протокол WS-Security с надежными сеансами. Но в некоторых случаях может потребоваться использовать безопасность транспорта HTTP с протоколом SSL.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSessionOverHttps`  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Протокол SSL гарантирует защищенность пакетов. Важно отметить, что этот подход отличается от защиты надежных сеансов с помощью протокола WS-SecureConversation.  
  
 Чтобы использовать надежные сеансы поверх протокола HTTPS, необходимо создать пользовательскую привязку. Этот пример основан на [getting Started,](../../../../docs/framework/wcf/samples/getting-started-sample.md) который реализует услугу калькулятора. С помощью надежного элемента связывания сеанса создается пользовательская привязка, а [ \<>httpsTransport. ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) Ниже представлена конфигурация пользовательской привязки.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- use base address provided by host -->  
        <endpoint address=""  
                  binding="customBinding"  
                  bindingConfiguration="reliableSessionOverHttps"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed as http://localhost/servicemodelsamples/service.svc/mex-->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="reliableSessionOverHttps">  
          <reliableSession />  
          <httpsTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="true" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 Программный код в образце идентичен коду службы [Getting Started.](../../../../docs/framework/wcf/samples/getting-started-sample.md) Перед построением и запуском примера необходимо с помощью мастера сертификатов веб-сервера создать и назначить сертификат. Определения конечной точки и привязки в файле конфигурации включают использование пользовательской привязки, как показано в следующем образце файла конфигурации клиента.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint name=""  
                address="https://localhost/servicemodelsamples/service.svc"
                binding="customBinding"
                bindingConfiguration="reliableSessionOverHttps"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
      <bindings>  
        <customBinding>  
          <binding name="reliableSessionOverHttps">  
            <reliableSession />  
            <httpsTransport />  
          </binding>  
        </customBinding>
    </bindings>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 Заданный адрес использует схему https://.  
  
 Поскольку сертификат, используемый в этом примере, является тестовым сертификатом, созданным с помощью Makecert.exe, при попытке получить доступ к https: адрес, https://localhost/servicemodelsamples/service.svcнапример, из браузера, появляется оповещение о безопасности. Чтобы позволить клиенту Windows Communication Foundation (WCF) работать с сертификатом теста, клиенту был добавлен дополнительный код для подавления оповещения о безопасности. При использовании рабочих сертификатов этот код и соответствующие классы не требуются.  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Установите ASP.NET 4.0 с помощью следующей команды.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
3. Убедитесь, что вы выполнили [инструкции по установке сертификатов сервера Internet Information Services (IIS).](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)  
  
4. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
