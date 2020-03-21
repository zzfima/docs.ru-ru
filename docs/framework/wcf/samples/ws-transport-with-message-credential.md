---
title: Транспорт WS с учетными данными сообщения
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 076d4490f6edc6efa8eeb50ae8baa23d5c4e369a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183147"
---
# <a name="ws-transport-with-message-credential"></a>Транспорт WS с учетными данными сообщения
В этом примере показано использовании безопасности транспорта SSL в сочетании с передаваемыми в сообщении учетными данными клиента. В этом примере используется привязка `wsHttpBinding`.  
  
 По умолчанию привязка `wsHttpBinding` обеспечивает взаимодействие по протоколу HTTP. При настройке для безопасности транспорта привязка поддерживает взаимодействие по протоколу HTTPS. Протокол HTTPS обеспечивает конфиденциальность и защиту целостности передаваемых по каналам связи сообщений. Тем не менее набор механизмов аутентификации, который можно использовать для проверки подлинности клиента при соединении со службой, ограничен механизмами, поддерживаемыми транспортом HTTPS. Windows Communication Foundation (WCF) предлагает режим безопасности, предназначенный `TransportWithMessageCredential` для преодоления этого ограничения. Если включен этот режим безопасности, для обеспечения конфиденциальности и целостности передаваемых сообщений, а также для проверки подлинности службы, используется безопасность транспорта. Тем не менее, проверка подлинности клиента выполняется путем ввода учетных данных клиента непосредственно в сообщение. Это позволяет использовать любой тип учетных данных, который поддерживается режимом безопасности сообщений для проверки подлинности клиента, сохраняя при этом преимущества производительности режима безопасности транспорта.  
  
 В этом примере для проверки подлинности клиента на стороне службы используется тип учетных данных `UserName`.  
  
 Этот пример основан на [getting Started,](../../../../docs/framework/wcf/samples/getting-started-sample.md) который реализует услугу калькулятора. В файлах конфигурации клиента и службы задана и настроена привязка `wsHttpBinding`.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Программный код в образце почти идентичен коду службы [Getting Started.](../../../../docs/framework/wcf/samples/getting-started-sample.md) Имеется одна дополнительная операция, предоставляемая контрактом службы - `GetCallerIdentity`. Операция возвращает вызывающей стороне имя удостоверения вызывающей стороны.  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 Перед построением и запуском примера необходимо с помощью мастера сертификатов веб-сервера создать и назначить сертификат. Определения конечной точки и привязки в файле конфигурации устанавливают режим безопасности `TransportWithMessageCredential`, как показано в следующем примере файла конфигурации клиента.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Заданный адрес использует схему https://. Конфигурация привязки задает режим безопасности `TransportWithMessageCredential`. Тот же режим безопасности необходимо задать в файле Web.config службы.  
  
 Поскольку сертификат, используемый в этом примере, является тестовым сертификатом, созданным с помощью Makecert.exe, при попытке получить доступ к https: адрес, `https://localhost/servicemodelsamples/service.svc`например, из браузера, появляется оповещение о безопасности. Чтобы позволить клиенту WCF работать с сертификатом теста на месте, некоторый дополнительный код был добавлен к клиенту для подавления предупреждения безопасности. При использовании рабочих сертификатов этот код и соответствующие классы не требуются.  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```console  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:
YourDomainName\YourAccountName  
   Enter password:
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Убедитесь, что вы выполнили [инструкции по установке сертификатов сервера Internet Information Services (IIS).](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)  
  
3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
