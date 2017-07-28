---
title: "Практическое руководство. Задание значений учетных данных клиента | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Практическое руководство. Задание значений учетных данных клиента
Используя [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], служба может указать способ проверки подлинности клиента в службе.  Например, в службе можно указать, что клиент проходит проверку подлинности с помощью сертификата.  
  
### Определение типа учетных данных клиента  
  
1.  Получите метаданные из конечной точки метаданных службы.  Метаданные обычно состоят из двух файлов: код клиента на выбранном языке программирования \(по умолчанию \- Visual C\#\) и XML\-файл конфигурации.  Одним из способов получения метаданных является использование программы Svcutil.exe для возвращения кода клиента и конфигурации клиента.  Дополнительные сведения см. в разделе [Извлечение метаданных](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) и [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
2.  Откройте XML\-файл конфигурации.  Если используется программа Svcutil.exe, то по умолчанию файл имеет имя Output.config.  
  
3.  Найдите элемент **\<security\>** с атрибутом **mode** attribute \(**\<security mode\=** `MessageOrTransport`**\>**, где в `MessageOrTransport` установлен один из режимов безопасности.  
  
4.  Найдите дочерний элемент, соответствующий значению режима.  Например, если установлен режим **Message**, найдите элемент **\<message\>**, содержащийся в элементе **\<security\>**.  
  
5.  Запишите значение, присвоенное атрибуту **clientCredentialType**.  Фактическое значение зависит от используемого режима \- транспорт или сообщение.  
  
 Следующий XML\-код представляет конфигурацию для клиента, использующего безопасность сообщений. Для проверки подлинности клиента требуется сертификат.  
  
```  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## Пример: транспортный режим TCP с сертификатом в качестве учетных данных клиента  
 В этом примере в качестве режима безопасности задается Transport, а в качестве значения учетных данных клиента \- сертификат X.509.  В следующих процедурах показано, как задать значение учетных данных клиента в коде клиента и в конфигурации.  Предполагается, что с помощью программы [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из службы возвращены метаданные \(код и конфигурация\).  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Как создать клиент](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
#### Указание значения учетных данных клиента в коде клиента  
  
1.  Используйте программу [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания кода и конфигурации из службы.  
  
2.  Создайте экземпляр клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] с помощью созданного кода.  
  
3.  В классе клиента задайте соответствующее значение для свойства <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601>.  В этом примере в качестве значения свойства задается сертификат X.509 с помощью метода <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     Можно использовать любое перечисление класса <xref:System.Security.Cryptography.X509Certificates.X509FindType>.  В случае, если сертификат изменен \(в связи с истечением срока действия\) используется имя субъекта.  Использование имени субъекта позволяет инфраструктуре снова найти сертификат.  
  
#### Указание значения учетных данных клиента в конфигурации клиента  
  
1.  Добавьте [\<поведение\>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) в элемент [\<поведения\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
2.  Добавьте элемент [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) в элемент [\<поведения\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  Необходимо присвоить обязательному атрибуту `name` соответствующее значение.  
  
3.  Добавьте [\<clientCertificate\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) в элемент [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).  
  
4.  Присвойте соответствующие значения следующим атрибутам: `storeLocation`, `storeName`, `x509FindType` и `findValue`, как показано в следующем коде.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] сертификатах см. в разделе [Работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
    ```  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  При настройке клиента укажите поведение, задав атрибут `behaviorConfiguration` элемента `<endpoint>`, как показано в следующем коде.  Элемент конечной точки является дочерним объектом элемента [\<клиент\>](../../../docs/framework/configure-apps/file-schema/wcf/client.md).  Также укажите имя конфигурации привязки, установив привязку для клиента в атрибуте `bindingConfiguration`.  Если используется созданный файл конфигурации, имя привязки создается автоматически.  В данном примере это имя `"tcpBindingWithCredential"`.  
  
    ```  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## См. также  
 <xref:System.ServiceModel.NetTcpBinding>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>   
 <xref:System.ServiceModel.ClientBase%601>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>   
 [Программирование безопасности WCF](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)   
 [Выбор типа учетных данных](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Как создать клиент](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [\<netTcpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)   
 [\<безопасность\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)   
 [\<сообщение\>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)   
 [\<поведение\>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)   
 [\<поведения\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)   
 [\<clientCertificate\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)   
 [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)