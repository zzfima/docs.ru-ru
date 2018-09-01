---
title: Безопасность транспорта WS
ms.date: 03/30/2017
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 59e6c3792571b8b712da1f36e66ff89a98b6bebb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387834"
---
# <a name="ws-transport-security"></a>Безопасность транспорта WS
В этом образце показано использование безопасности транспорта SSL с привязкой <xref:System.ServiceModel.WSHttpBinding>. По умолчанию привязка `wsHttpBinding` обеспечивает взаимодействие по протоколу HTTP. При настройке для безопасности транспорта привязка поддерживает взаимодействие по протоколу HTTPS. Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующем службу калькулятора. В файлах конфигурации клиента и службы задана и настроена привязка `wsHttpBinding`.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 Код программы в образце идентична [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) службы. Перед построением и запуском примера необходимо с помощью мастера сертификатов веб-сервера создать и назначить сертификат. Определения конечной точки и привязки в файле конфигурации устанавливают режим безопасности `Transport`, как показано в следующем примере файла конфигурации клиента.  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 Заданный адрес использует схему https://. Конфигурация привязки задает режим безопасности `Transport`. Тот же режим безопасности необходимо задать в файле Web.config службы.  
  
 Так как сертификат, используемый в этом примере является тестовым сертификатом, созданным с помощью Makecert.exe, оповещение системы безопасности отображается при попытке доступа к https: адрес, такие как https://localhost/servicemodelsamples/service.svc, в браузере. Чтобы позволить клиенту службы Windows Communication Foundation (WCF) для работы с тестовым сертификатом, в месте, клиенту, чтобы подавлять предупреждения системы безопасности был добавлен дополнительный код. При использовании рабочих сертификатов этот код и соответствующие классы не требуются.  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Убедитесь, что вы выполнили [инструкции по установке сертификата сервера Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>См. также
