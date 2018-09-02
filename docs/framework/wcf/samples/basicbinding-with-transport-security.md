---
title: BasicBinding с обеспечением безопасности транспорта
ms.date: 03/30/2017
ms.assetid: f49b1de6-0254-4362-8ef2-fccd8ff9688b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 69257099338ae2d50c5ea184c0800d0057e020f4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43471998"
---
# <a name="basicbinding-with-transport-security"></a>BasicBinding с обеспечением безопасности транспорта
Этот образец демонстрирует использование безопасности транспорта SSL с использованием основной привязки. Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующем службу калькулятора.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\TransportSecurity`  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 По умолчанию основная привязка поддерживает взаимодействие по протоколу HTTP. В образце показано, как включить режим безопасности транспорта для базовой привязки. Перед выполнением образца необходимо с помощью мастера сертификатов веб-сервера создать и назначить сертификат.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Код программы в образце идентична [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) службы. Определения конечной точки и привязки в параметрах файла конфигурации меняются для обеспечения безопасного взаимодействия, как показано в следующем образце конфигурации.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
   </services>  
  <bindings>  
    <basicHttpBinding>  
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"/>  
        </security>  
      </binding>  
    </basicHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Так как сертификат, используемый в этом примере является тестовым сертификатом, созданным с помощью Makecert.exe, оповещение системы безопасности отображается при попытке доступа к HTTPS: адрес в браузере, например https://localhost/servicemodelsamples/service.svc. Чтобы разрешить клиента Windows Communication Foundation (WCF) для работы с тестовым сертификатом, клиенту, чтобы подавлять предупреждения системы безопасности добавлен дополнительный код. При использовании настоящих сертификатов этот код и соответствующие классы не требуются.  

```csharp
// This code is required only for test certificates such as those   
// created by Makecert.exe.  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Убедитесь, что вы выполнили [инструкции по установке сертификата сервера Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>См. также
