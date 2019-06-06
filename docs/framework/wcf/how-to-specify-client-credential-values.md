---
title: Практическое руководство. Задание значений учетных данных клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 9d49f68dae43ef699be930c7f2eb33243329d405
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690599"
---
# <a name="how-to-specify-client-credential-values"></a>Практическое руководство. Задание значений учетных данных клиента

С помощью Windows Communication Foundation (WCF), служба может указать способ проверки подлинности клиента к службе. Например, в службе можно указать, что клиент проходит проверку подлинности с помощью сертификата.

### <a name="to-determine-the-client-credential-type"></a>Определение типа учетных данных клиента

1. Получите метаданные из конечной точки метаданных службы. Метаданные обычно состоят из двух файлов: код клиента на выбранном языке программирования (по умолчанию - Visual C#) и XML-файл конфигурации. Одним из способов получения метаданных является использование программы Svcutil.exe для возвращения кода клиента и конфигурации клиента. Дополнительные сведения см. в разделе [получение метаданных](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) и [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).

2. Откройте XML-файл конфигурации. Если используется программа Svcutil.exe, то по умолчанию файл имеет имя Output.config.

3. Найти  **\<безопасности >** элемент с **режим** атрибут ( **\<режим безопасности =** `MessageOrTransport` **>** где `MessageOrTransport` задан один из режимов безопасности.

4. Найдите дочерний элемент, соответствующий значению режима. Например, если выбран режим **сообщение**, найти  **\<сообщения >** элемента, содержащегося в  **\<безопасности >** элемент.

5. Обратите внимание на то значение, присваиваемое **clientCredentialType** атрибута. Фактическое значение зависит от используемого режима - транспорт или сообщение.

Следующий XML-код представляет конфигурацию для клиента, использующего безопасность сообщений. Для проверки подлинности клиента требуется сертификат.

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a>Пример Транспортный режим TCP с сертификатом в качестве учетных данных клиента

В этом примере в качестве режима безопасности задается Transport, а в качестве значения учетных данных клиента - сертификат X.509. В следующих процедурах показано, как задать значение учетных данных клиента в коде клиента и в конфигурации. Предполагается, что вы использовали [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для из службы возвращены метаданные (код и конфигурация). Дополнительные сведения см. в разделе [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).

#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a>Указание значения учетных данных клиента в коде клиента

1. Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания кода и конфигурации из службы.

2. Создайте экземпляр клиента WCF с помощью созданного кода.

3. В классе клиента задайте соответствующее значение для свойства <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601>. В этом примере в качестве значения свойства задается сертификат X.509 с помощью метода <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     Можно использовать любое перечисление класса <xref:System.Security.Cryptography.X509Certificates.X509FindType>. В случае, если сертификат изменен (в связи с истечением срока действия) используется имя субъекта. Использование имени субъекта позволяет инфраструктуре снова найти сертификат.

#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a>Указание значения учетных данных клиента в конфигурации клиента

1. Добавить [ \<поведение >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемент [ \<поведения >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент.

2. Добавить [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент [ \<поведения >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент. Необходимо присвоить обязательному атрибуту `name` соответствующее значение.

3. Добавить [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) элемент [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент.

4. Присвойте соответствующие значения следующим атрибутам: `storeLocation`, `storeName`, `x509FindType` и `findValue`, как показано в следующем коде. Дополнительные сведения см. в разделе [Работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md).

    ```xml
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

5. При настройке клиента укажите поведение, задав атрибут `behaviorConfiguration` элемента `<endpoint>`, как показано в следующем коде. Элемент конечной точки является дочерним элементом [ \<клиента >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) элемент. Также укажите имя конфигурации привязки, установив привязку для клиента в атрибуте `bindingConfiguration`. Если используется созданный файл конфигурации, имя привязки создается автоматически. В данном примере это имя `"tcpBindingWithCredential"`.

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Программирование безопасности WCF](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [Выбор типа учетных данных](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)
- [\<Безопасность >](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [\<сообщение >](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [\<поведение >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [\<варианты поведения >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
- [\<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
