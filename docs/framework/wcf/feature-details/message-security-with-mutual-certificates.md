---
title: Безопасность сообщений с использованием взаимных сертификатов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: e2aaf1a5e6ae1074a81c08fc798f22ea5e9ce139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184610"
---
# <a name="message-security-with-mutual-certificates"></a>Безопасность сообщений с использованием взаимных сертификатов
В следующем сценарии показана служба Windows Communication Foundation (WCF) и клиент, защищенный с помощью режима безопасности сообщений. Проверка подлинности клиента и службы выполняется с помощью сертификатов.  
  
 Данный сценарий поддерживает возможность взаимодействия, поскольку в нем используется WS-Security с профилем маркера сертификата X.509.  
  
> [!NOTE]
> Данный сценарий не выполняет согласование сертификата службы. Сертификат службы должен быть предоставлен клиенту перед началом любой связи. Сертификат сервера может быть распределен приложением или предоставлен во внеполосной связи.  
  
 ![Безопасность сообщений с взаимными сертификатами](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Режим безопасности|Сообщение|  
|Совместимость|Да, с клиентами и службами, совместимыми с профилем маркера WS-Security и сертификата X.509.|  
|Аутентификация|Взаимная проверка подлинности сервера и клиента.|  
|Целостность|Да|  
|Конфиденциальность|Да|  
|Транспортировка|HTTP|  
|Привязка|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>Служба  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.  
  
- Создайте автономную службу, используя код без конфигурации.  
  
- Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.  
  
### <a name="code"></a>Код  
 В следующем коде показано, как создать конечную точку службы, которая использует безопасность сообщений. Служба требует прохождения проверки подлинности сертификата.  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a>Конфигурация  
 Вместо кода для создания той же службы можно использовать следующую конфигурацию.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>клиент  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.  
  
- Создайте автономный клиент, используя код (и код клиента).  
  
- Создайте клиент, который не определяет никаких адресов конечных точек. Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации. Пример:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>Код  
 Следующий код служит для создания клиента. Режим безопасности установлен в Message, и типу учетных данных клиента присвоено значение Certificate.  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a>Конфигурация  
 Следующий код служит для настройки клиента. Сертификат клиента должен быть указан с помощью [ \<>сертификата клиента. ](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md) Кроме того, сертификат обслуживания указан с помощью [ \<>сертификата по умолчанию. ](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Обзор безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
- [Как: Создание и установка временных сертификатов в WCF для транспортной безопасности во время разработки](https://docs.microsoft.com/previous-versions/msp-n-p/ff648498(v=pandp.10))
