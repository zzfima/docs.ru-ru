---
title: "&lt;сообщение&gt; для &lt;netHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af7dcd39dbc7ecca899cda0779c98efa1493c60f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagegt-of-ltnethttpbindinggt"></a>&lt;сообщение&gt; для &lt;netHttpBinding&gt;
Определяет параметры безопасности уровня сообщений [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 \<система. ServiceModel >  
\<привязки >  
\<Привязка netHttpBinding >  
\<Привязка >  
\<Безопасность >  
\<сообщение >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|algorithmSuite|Задает алгоритмы шифрования сообщений и ключей. Этот атрибут имеет тип <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, который задает алгоритмы и размеры ключей. Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).<br /><br /> Значение по умолчанию — `Basic256`.|  
|clientCredentialType|Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности на уровне сообщений. Значение по умолчанию — `UserName`.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|UserName|-Требует подлинности клиента на сервер с использованием имени пользователя. Эти учетные данные должны быть указаны с помощью элемента <`clientCredentials`>.<br />-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]не поддерживает передачу дайджеста пароля или получение ключей с использованием паролей и использование таких ключей для обеспечения безопасности сообщений. Таким образом, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] принудительно обеспечивает безопасность транспорта при использовании имени пользователя. Для `basicHttpBinding` это требует настройки канала SSL.|  
|Сертификат|Требует, чтобы при подключении к серверу проверка подлинности клиента проводилась с помощью сертификата. В этом случае учетные данные клиента должны быть определены с помощью элементов <`clientCredentials`> и <`clientCertificate`>. Кроме того, при использовании режима безопасности сообщений клиенту должен быть предоставлен сертификат службы. В этом случае необходимо указать с помощью учетных данных службы <xref:System.ServiceModel.Description.ClientCredentials> класса или `ClientCredentials` элемент поведения и указав службу сертификатов с помощью \<serviceCertificate > элемента serviceCredentials.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|<`security`> элемента <`netHttpBinding`>|Определяет возможности безопасности для элемента <`netHttpBinding`>.|  
  
## <a name="example"></a>Пример  
 В образце демонстрируется реализация приложения, которое использует basicHttpBinding и безопасность сообщений. В следующем примере конфигурации для службы в определении конечной точки задаются привязка basicHttpBinding и ссылки на конфигурацию привязки с именем `Binding1`. Сертификат, используемый службой для своей проверки подлинности при подключении к клиенту, установлен в разделе `behaviors` файла конфигурации в элементе `serviceCredentials`. Режим проверки, применяемый к сертификату, который клиент использует для своей проверки подлинности при подключении к службе, также установлен в разделе `behaviors` в элементе `clientCertificate`.  
  
 Та же привязка и данные безопасности задаются в файле конфигурации клиента.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
      <basicHttpBinding>  
        <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1" >  
          <security mode = "Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--  
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>См. также  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки служб Windows Communication Foundation и клиентов](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
