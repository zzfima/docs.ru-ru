---
title: Транспорт WS с учетными данными сообщения
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 54bd025db4da8ed1d1484b11666a37c2c14a6023
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949634"
---
# <a name="ws-transport-with-message-credential"></a>Транспорт WS с учетными данными сообщения
В этом примере показано использовании безопасности транспорта SSL в сочетании с передаваемыми в сообщении учетными данными клиента. В этом примере используется привязка `wsHttpBinding`.  
  
 По умолчанию привязка `wsHttpBinding` обеспечивает взаимодействие по протоколу HTTP. При настройке для безопасности транспорта привязка поддерживает взаимодействие по протоколу HTTPS. Протокол HTTPS обеспечивает конфиденциальность и защиту целостности передаваемых по каналам связи сообщений. Тем не менее набор механизмов аутентификации, который можно использовать для проверки подлинности клиента при соединении со службой, ограничен механизмами, поддерживаемыми транспортом HTTPS. Windows Communication Foundation (WCF) предлагает `TransportWithMessageCredential` режим безопасности, который позволяет обойти это ограничение. Если включен этот режим безопасности, для обеспечения конфиденциальности и целостности передаваемых сообщений, а также для проверки подлинности службы, используется безопасность транспорта. Тем не менее проверка подлинности клиента выполняется путем помещения учетные данные клиента непосредственно в сообщении. Это позволяет использовать любой тип учетных данных, поддерживаемый режим безопасности сообщений для проверки подлинности клиента, сохраняя преимущества высокой производительности режима безопасности транспорта.  
  
 В этом примере для проверки подлинности клиента на стороне службы используется тип учетных данных `UserName`.  
  
 Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующем службу калькулятора. В файлах конфигурации клиента и службы задана и настроена привязка `wsHttpBinding`.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Код программы, в примере почти идентична [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) службы. Имеется одна дополнительная операция, предоставляемая контрактом службы - `GetCallerIdentity`. Операция возвращает вызывающей стороне имя удостоверения вызывающей стороны.  

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
  
 Так как сертификат, используемый в этом примере является тестовым сертификатом, созданным с помощью Makecert.exe, оповещение системы безопасности отображается при попытке доступа к https: адрес, такие как `https://localhost/servicemodelsamples/service.svc`, в браузере. Чтобы разрешить клиента WCF для работы с тестовым сертификатом, в месте, клиенту, чтобы подавлять предупреждения системы безопасности был добавлен дополнительный код. При использовании рабочих сертификатов этот код и соответствующие классы не требуются.  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
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
  
1. Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Убедитесь, что вы выполнили [инструкции по установке сертификата сервера Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
