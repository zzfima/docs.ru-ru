---
title: Безопасность транспорта с проверкой подлинности с использованием сертификатов
ms.date: 03/30/2017
dev_langs:
- csharp
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
ms.openlocfilehash: ad2f0922afbd94e1699b383cf2fc9762771b637d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184332"
---
# <a name="transport-security-with-certificate-authentication"></a>Безопасность транспорта с проверкой подлинности с использованием сертификатов

В этой статье обсуждается использование сертификатов X.509 для проверки подлинности сервера и клиента при использовании транспортной безопасности. Дополнительные сведения о сертификатах X.509 см. в разделе [Сертификаты открытого ключа X.509](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates). Сертификаты должны выдаваться сертификационным органом, который часто является сторонним эмитентом сертификатов. В домене Windows Server для выдачи сертификатов клиентским компьютерам домена можно использовать службу сертификации Active Directory. В этом сценарии служба размещена в службах IIS, которые используют протокол SSL. В службе задано использование сертификата SSL (X.509), чтобы клиенты могли проверять подлинность сервера. В клиенте также задано использование сертификата X.509, что позволяет службе проверять подлинность клиента. Клиент должен доверять сертификату сервера, а сервер ― сертификату клиента. Фактическая механика проверки личности службы и клиента выходит за рамки данной статьи. Для получения дополнительной информации смотрите [цифровую подпись](https://en.wikipedia.org/wiki/Digital_signature) в Википедии.
  
 В этом сценарии реализуется шаблон обмена сообщениями «запрос-ответ», показанный на следующей схеме.  
  
 ![Безопасный перевод с помощью сертификатов](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")  
  
 Для получения дополнительной информации об использовании сертификата [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)с услугой [см.](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) В следующей таблице описываются различные особенности этого сценария.  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Режим безопасности|Транспортировка|  
|Совместимость|С существующими службами и клиентами веб-служб.|  
|Проверка подлинности (сервера)<br /><br /> Проверка подлинности (клиента)|Да (с использованием SSL-сертификата)<br /><br /> Да (с использованием сертификата X.509)|  
|Целостность данных|Да|  
|Конфиденциальность данных|Да|  
|Транспортировка|HTTPS|  
|Привязка|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a>Настройка службы  
 Поскольку в этом сценарии служба размещается в службах IIS, он настраивается с помощью файла web.config. В следующем примере содержимого файла web.config показано, как настроить в <xref:System.ServiceModel.WSHttpBinding> использование безопасности транспорта и учетных данных клиента X.509.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a>Настройка клиента  
 Настроить клиент можно в коде или в файле app.config. В следующем примере показано, как настроить клиент в коде.  
  
```csharp
// Create the binding.  
var myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.
var ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
var cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 Также можно настроить клиент в файле App.config, как показано в следующем примере:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Обзор безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
