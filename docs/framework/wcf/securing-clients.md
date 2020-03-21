---
title: Обеспечение безопасности клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], security considerations
ms.assetid: 44c8578c-9a5b-4acd-8168-1c30a027c4c5
ms.openlocfilehash: bfb980e629ffb8f8543937a1850430c9bf6e9199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183134"
---
# <a name="securing-clients"></a>Обеспечение безопасности клиентов
В Фонде связи Windows (WCF) служба диктует требования безопасности для клиентов. Это означает, что служба указывает используемый режим безопасности и определяет, должен ли клиент предоставить учетные данные. Таким образом, процесс обеспечения безопасности клиента прост: используйте метаданные, полученные от службы (если она опубликована), и создайте клиент. Метаданные указывают, как настроить клиент. Если служба требует, чтобы клиент предоставлял учетные данные, необходимо получить учетные данные, удовлетворяющие требованиям. В этом разделе подробно описан данный процесс. Для получения дополнительной информации о создании службы [безопасности](securing-services.md)см.  
  
## <a name="the-service-specifies-security"></a>Служба задает безопасность  
 По умолчанию привязки WCF включены функции безопасности. (Исключением <xref:System.ServiceModel.BasicHttpBinding>является .) Поэтому, если служба была создана с помощью WCF, существует большая вероятность того, что она будет осуществлять безопасность для обеспечения аутентификации, конфиденциальности и целостности. В таком случае метаданные, предоставляемые службой, будут указывать, что требуется установить безопасный коммуникационный канал. Если метаданные службы не содержат требований по безопасности, не существует способа применить к службе какую-либо схему безопасности, например, SSL через HTTP. Если, однако, служба требует, чтобы клиент предоставлял учетные данные, разработчик, установщик или администратор клиента должны представить фактические учетные данные, которые клиент будет использовать для проверки своей подлинности в службе.  
  
## <a name="obtaining-metadata"></a>Получение метаданных  
 При создании клиента первым шагом является получение метаданных от службы, с которой будет взаимодействовать клиент. Это можно сделать двумя способами. Во-первых, если служба публикует конечную точку обмена метаданными (MEX) или делает свои метаданные доступными по HTTP или HTTPS, вы можете загрузить метаданные с помощью [utility Tool ServiceModel Metadata Utility Tool (Svcutil.exe),](servicemodel-metadata-utility-tool-svcutil-exe.md)который генерирует как файлы кода для клиента, так и файл конфигурации. (Для получения дополнительной информации об [использовании](accessing-services-using-a-wcf-client.md)инструмента см. Если служба не публикует конечную точку MEX, а также не предоставляет свои метаданные по HTTP или HTTPS, необходимо связаться с создателем службы для получения документации, описывающая требования к безопасности и метаданные.  
  
> [!IMPORTANT]
> Рекомендуется получать метаданные из надежного источника, который не был злонамеренно искажен. Метаданные, полученные по протоколу HTTP, передаются открытым текстом и могут быть подделаны. Если в службе используются свойства <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> и <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>, для загрузки данных по протоколу HTTPS используйте URL-адрес, предоставленный разработчиком службы.  
  
## <a name="validating-security"></a>Проверка безопасности  
 Источники метаданных можно разделить на две большие категории: надежные источники и ненадежные источники. Если вы доверяете источнику и загрузили код клиента и другие метаданные с безопасной конечной точки MEX этого источника, при создании клиента снабдите его правильными учетными данными - никакие дополнительные меры не требуются.  
  
 Однако если клиент и метаданные загружены из источника, о котором мало что известно, обязательно проверьте меры безопасности, используемые в коде. Например, не следует просто создавать клиент, который отправляет ваши личные или финансовые данные в службу, если эта служба не требует как минимум конфиденциальности и целостности. Вы должны доверять владельцу сервиса в той мере, в какой вы готовы раскрыть такую информацию, так как такая информация будет им видна.  
  
 Поэтому, как правило, при использовании кода и метаданных от ненадежного источника проверяйте код и метаданные на предмет соответствия вашим требованиям к безопасности.  
  
## <a name="setting-a-client-credential"></a>Задание учетных данных клиента  
 Задание учетных данных клиента в клиенте состоит из двух этапов.  
  
1. Определите *тип учетных данных клиента,* который требуетслужба службы. Это можно сделать одним из двух способов. Во-первых, если у вас есть документация от разработчика службы, в ней должен быть указан тип учетных данных клиента (при наличии), требуемых службой. Во-вторых, при наличии только файла конфигурации, созданного инструментом Svcutil.exe, можно изучить индивидуальные привязки и определить требуемый тип учетных данных.  
  
2. Задайте фактические учетные данные клиента. Фактический учетный учетный данный клиента называется *значением учетных данных клиента,* чтобы отличить его от типа. Например, если тип учетных данных клиента представляет собой сертификат, то необходимо предоставить сертификат X.509, выданный службой сертификации, которой доверяет требуемая служба.  
  
### <a name="determining-the-client-credential-type"></a>Определение типа учетных данных клиента  
 Если у вас есть файл конфигурации, созданный инструментом Svcutil.exe, изучите [ \<привязки>](../configure-apps/file-schema/wcf/bindings.md) раздел, чтобы определить, какой тип учетных данных клиента не требуется. В этом разделе находятся элементы привязки, задающие требования безопасности. В частности, \<изучить безопасность> элемент каждого связывания. Этот элемент содержит атрибут `mode`, которому можно присвоить одно из трех возможных значений (`Message`, `Transport` или `TransportWithMessageCredential`). Значение этого атрибута определяет режим, задающий, в свою очередь, какой из дочерних элементов является значимым.  
  
 Элемент `<security>` может содержать `<transport>` либо `<message>` элемент, либо и то, и другое. Значимым элементом является тот, который соответствует режиму безопасности. Например, следующий код задает режим безопасности `"Message"`, а типом учетных данных клиента для элемента `<message>` является `"Certificate"`. В этом случае элемент `<transport>` можно игнорировать. Однако элемент `<message>` задает, что должен быть предоставлен сертификат X.509.  

```xml  
<wsHttpBinding>  
    <binding name="WSHttpBinding_ICalculator">  
       <security mode="Message">  
           <transport clientCredentialType="Windows"
                      realm="" />  
           <message clientCredentialType="Certificate"
                    negotiateServiceCredential="true"  
                    algorithmSuite="Default"
                    establishSecurityContext="true" />  
       </security>  
    </binding>  
</wsHttpBinding>  
```  

 Обратите внимание, что если для атрибута `clientCredentialType` задано значение `"Windows"`, как показано с следующем примере, предоставлять фактическое значение учетных данных не требуется. Это связано с тем, что встроенная система безопасности Windows предоставляет фактические учетные данные (маркер Kerberos) пользователя, запустившего клиент.  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows "
        realm="" />  
</security>  
```  
  
### <a name="setting-the-client-credential-value"></a>Задание значения учетных данных клиента  
 Если установлено, что клиент должен предоставлять учетные данные, используйте подходящий способ настройки клиента. Например, чтобы задать сертификат клиента, используйте метод <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>.  
  
 Обычной формой учетных данных является сертификат X.509. Эти учетные данные можно предоставить двумя способами.  
  
- Запрограммировав их в коде клиента (с помощью метода `SetCertificate`).  
  
 Добавляя [ \<поведение>](../configure-apps/file-schema/wcf/behaviors.md) раздел файла конфигурации для `clientCredentials` клиента и используя элемент (см. ниже).  
  
#### <a name="setting-a-clientcredentials-value-in-code"></a>Установка \<clientCredentials> значение в коде  
 Чтобы установить [ \<клиентУ credentials>](../configure-apps/file-schema/wcf/clientcredentials.md) значение <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> в коде, необходимо получить доступ к свойству <xref:System.ServiceModel.ClientBase%601> класса. Это свойство возвращает объект <xref:System.ServiceModel.Description.ClientCredentials>, обеспечивающий доступ к различным типам учетных данных, как показано в приведенной ниже таблице.  
  
|Свойство ClientCredential|Описание|Примечания|  
|-------------------------------|-----------------|-----------|  
|<xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>|Возвращает <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|Представляет сертификат X.509, предоставляемый клиентом для проверки своей подлинности в службе.|  
|<xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>|Возвращает <xref:System.ServiceModel.Security.HttpDigestClientCredential>|Представляет учетные данные дайджест-проверки подлинности HTTP. Эти учетные данные представляют собой хэш имени пользователя и пароля.|  
|<xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>|Возвращает <xref:System.ServiceModel.Security.IssuedTokenClientCredential>|Представляет настраиваемый маркер безопасности, выданный службой маркеров безопасности, обычно используемой в сценариях федерации.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>|Возвращает <xref:System.ServiceModel.Security.PeerCredential>|Представляет одноранговые учетные данные для участия в сетке узлов домена Windows.|  
|<xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>|Возвращает <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>|Представляет сертификат X.509, предоставляемый службой для согласования вне полосы.|  
|<xref:System.ServiceModel.Description.ClientCredentials.UserName%2A>|Возвращает <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>|Возвращает пару, содержащую имя пользователя и пароль.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>|Возвращает <xref:System.ServiceModel.Security.WindowsClientCredential>|Представляет учетные данные Windows клиента (учетные данные Kerberos). Свойства этого класса доступны только для чтения.|  
  
#### <a name="setting-a-clientcredentials-value-in-configuration"></a>Установка \<клиентАлиза> значения в конфигурации  
 Значения учетных данных определяются с помощью [ \<](../configure-apps/file-schema/wcf/clientcredentials.md) поведения конечной точки в качестве элементов детской>элемента. Используемый элемент зависит от типа учетных данных клиента. Например, в следующем примере показана конфигурация для установки сертификата X.509 с помощью [ \<<>сертификата клиента. ](../configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>
        <behavior name="myEndpointBehavior">  
          <clientCredentials>  
            <clientCertificate findvalue="myMachineName"
            storeLocation="Current" X509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>
      </endpointBehaviors>
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
 Чтобы настроить учетные данные клиента в конфигурации, добавьте [ \<элемент endpointBehaviors>](../configure-apps/file-schema/wcf/endpointbehaviors.md) в файл конфигурации. Кроме того, дополнительный элемент поведения должен быть связан с `behaviorConfiguration` конечной точкой службы, используя атрибут [ \<конечной \<точки>](../configure-apps/file-schema/wcf/endpoint-of-client.md) элемента>клиента, как показано в следующем примере. Значение атрибута `behaviorConfiguration` должно соответствовать значению атрибута `name` расширения функциональности.  

```xml
<configuration>
  <system.serviceModel>
    <client>
      <endpoint address="http://localhost/servicemodelsamples/service.svc"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                behaviorConfiguration="myEndpointBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```
  
> [!NOTE]
> Некоторые из значений учетных данных клиента не могут задаваться с помощью файлов конфигурации приложения; это, например, значения имени пользователя и пароля или значения пользователя и пароля Windows. Такие значения учетных данных могут быть заданы только в коде.  
  
 Для получения дополнительной [информации](how-to-specify-client-credential-values.md)об установлении учетных данных клиента см.  
  
> [!NOTE]
> Значение `ClientCredentialType` игнорируется, если для параметра `SecurityMode` задано значение `"TransportWithMessageCredential",` как показано в следующем примере конфигурации.  
  
```xml  
<wsHttpBinding>  
    <binding name="PingBinding">  
        <security mode="TransportWithMessageCredential"  >  
           <message  clientCredentialType="UserName"
               establishSecurityContext="false"
               negotiateServiceCredential="false" />  
           <transport clientCredentialType="Certificate"  />  
         </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [\<привязки>](../configure-apps/file-schema/wcf/bindings.md)
- [Редактор конфигурации (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)
- [Защита служб](securing-services.md)
- [Обращение к службам с помощью клиента WCF](accessing-services-using-a-wcf-client.md)
- [Практическое руководство. Указание значений учетных данных клиента](how-to-specify-client-credential-values.md)
- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Практическое руководство. Указание типа учетных данных клиента](how-to-specify-the-client-credential-type.md)
