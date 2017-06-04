---
title: "Безопасность транспорта WS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# Безопасность транспорта WS
В этом образце показано использование безопасности транспорта SSL с привязкой <xref:System.ServiceModel.WSHttpBinding>.По умолчанию привязка `wsHttpBinding` обеспечивает взаимодействие по протоколу HTTP.При настройке для безопасности транспорта привязка поддерживает взаимодействие по протоколу HTTPS.Данный образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.В файлах конфигурации клиента и службы задана и настроена привязка `wsHttpBinding`.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 Код программы в этом образце полностью идентичен коду службы, описанной в разделе [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).Перед построением и выполнением образца необходимо с помощью мастера сертификатов веб\-сервера создать и назначить сертификат.Определения конечной точки и привязки в файле конфигурации устанавливают режим безопасности `Transport`, как показано в следующем образце файла конфигурации клиента.  
  
```  
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
  
 Заданный адрес использует схему https:\/\/.Конфигурация привязки задает режим безопасности `Transport`.Тот же режим безопасности необходимо задать в файле Web.config службы.  
  
 Поскольку используемый в этом образце сертификат является тестовым сертификатом, созданным с помощью средства Makecert.exe, при попытке доступа по адресу "https:", например https:\/\/localhost\/servicemodelsamples\/service.svc, через браузер, появляется предупреждение системы безопасности.Чтобы клиент [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] мог работать с используемым тестовым сертификатом, в клиент был добавлен дополнительный код, подавляющий появление предупреждения системы безопасности.При использовании рабочих сертификатов этот код и соответствующие классы не требуются.  
  
```  
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### Настройка, построение и выполнение образца  
  
1.  Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Убедитесь, что выполнены действия, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Убедитесь, что выполнены процедуры, описанные в разделе [Инструкции по установке сертификата сервера в службах IIS](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4.  Чтобы выполнить построение версии решения для языка C\# или Visual Basic .NET, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также