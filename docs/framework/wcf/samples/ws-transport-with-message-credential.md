---
title: "Транспорт WS с учетными данными сообщения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Транспорт WS с учетными данными сообщения
В этом примере показано использовании безопасности транспорта SSL в сочетании с передаваемыми в сообщении учетными данными клиента.В этом примере используется привязка `wsHttpBinding`.  
  
 По умолчанию привязка `wsHttpBinding` обеспечивает взаимодействие по протоколу HTTP.При настройке для безопасности транспорта привязка поддерживает взаимодействие по протоколу HTTPS.Протокол HTTPS обеспечивает конфиденциальность и защиту целостности передаваемых по каналам связи сообщений.Тем не менее набор механизмов аутентификации, который можно использовать для проверки подлинности клиента при соединении со службой ограничивается механизмами, которые поддерживаются транспортом HTTPS.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предлагает `TransportWithMessageCredential` режим безопасности, который позволяет обойти это ограничение.Если включен этот режим безопасности, для обеспечения конфиденциальности и целостности передаваемых сообщений, а также для проверки подлинности службы, используется безопасность транспорта.А для проверки подлинности клиента его учетные данные помещаются непосредственно в сообщение. Это позволяет использовать любой тип учетных данных, поддерживаемый режимом безопасности, и при этом сохранить преимущества высокой производительности режима безопасности транспорта.  
  
 В этом примере для проверки подлинности клиента на стороне службы используется тип учетных данных `UserName`.  
  
 Данный пример основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.В файлах конфигурации клиента и службы задана и настроена привязка `wsHttpBinding`.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного примера расположены в конце этого раздела.  
  
 Код программы в этом примере почти полностью идентичен коду службы, описанной в разделе [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).Имеется одна дополнительная операция, предоставляемая контрактом службы — `GetCallerIdentity`.Операция возвращает вызывающей стороне имя удостоверения вызывающей стороны.  
  
```  
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```  
  
 Перед построением и запуском примера необходимо с помощью мастера сертификатов веб\-сервера создать и назначить сертификат.Определения конечной точки и привязки в файле конфигурации устанавливают режим безопасности `TransportWithMessageCredential`, как показано в следующем примере файла конфигурации клиента.  
  
```  
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
  
 Заданный адрес использует схему https:\/\/.Конфигурация привязки задает режим безопасности `TransportWithMessageCredential`.Тот же режим безопасности необходимо задать в файле Web.config службы.  
  
 Поскольку используемый в этом образце сертификат является тестовым сертификатом, созданным с помощью средства Makecert.exe, при попытке доступа по адресу "https:", например https:\/\/localhost\/servicemodelsamples\/service.svc, через браузер, появляется предупреждение системы безопасности.Чтобы клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] мог работать с используемым тестовым сертификатом, в клиент был добавлен дополнительный код, подавляющий появление предупреждения системы безопасности.При использовании рабочих сертификатов этот код и соответствующие классы не требуются.  
  
```  
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
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
  
### Настройка, построение и выполнение примера  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Убедитесь, что выполнены процедуры, описанные в разделе [Инструкции по установке сертификата сервера в службах IIS](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
3.  Чтобы выполнить построение версии решения для языка C\# или Visual Basic .NET, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также