---
title: "Обеспечение безопасности клиентов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "клиенты [WCF], вопросы безопасности"
ms.assetid: 44c8578c-9a5b-4acd-8168-1c30a027c4c5
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# Обеспечение безопасности клиентов
В [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] требования безопасности для клиентов определяются службой.Это означает, что служба указывает используемый режим безопасности и определяет, должен ли клиент предоставить учетные данные.Таким образом, процесс обеспечения безопасности клиента прост: используйте метаданные, полученные от службы \(если она опубликована\), и создайте клиент.Метаданные указывают, как настроить клиент.Если служба требует, чтобы клиент предоставлял учетные данные, необходимо получить учетные данные, удовлетворяющие требованиям.В этом разделе подробно описан данный процесс.[!INCLUDE[crabout](../../../includes/crabout-md.md)] о создании защищенной службы см. в разделе [Защита служб](../../../docs/framework/wcf/securing-services.md).  
  
## Служба задает безопасность  
 По умолчанию в привязках [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] включены функции безопасности.\(Исключением является класс <xref:System.ServiceModel.BasicHttpBinding>.\) Поэтому если служба была создана с помощью [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], с большой вероятность она будет реализовывать функции безопасности для обеспечения проверки подлинности, конфиденциальности и целостности.В таком случае метаданные, предоставляемые службой, будут указывать, что требуется установить безопасный коммуникационный канал.Если метаданные службы не содержат требований по безопасности, не существует способа применить к службе какую\-либо схему безопасности, например, SSL через HTTP.Если, однако, служба требует, чтобы клиент предоставлял учетные данные, разработчик, установщик или администратор клиента должны представить фактические учетные данные, которые клиент будет использовать для проверки своей подлинности в службе.  
  
## Получение метаданных  
 При создании клиента первым шагом является получение метаданных от службы, с которой будет взаимодействовать клиент.Это можно сделать двумя способами.Во\-первых, если служба публикует конечную точку обмена метаданными \(MEX\) или предоставляет доступ к метаданным по протоколу HTTP или HTTPS, эти метаданные можно загрузить с помощью инструмента [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), который генерирует файлы кода для клиента и файл конфигурации.\([!INCLUDE[crabout](../../../includes/crabout-md.md)] с использованием этого инструмента см. в разделе [Обращение к службам с использованием клиента WCF](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).\) Если служба не публикует конечную точку обмена метаданными \(MEX\) и не предоставляет доступ к метаданным по протоколу HTTP или HTTPS, необходимо обратиться к разработчику службы за документацией, содержащей описание требований к безопасности и метаданные.  
  
> [!IMPORTANT]
>  Рекомендуется получать метаданные из надежного источника, который не был злонамеренно искажен.Метаданные, полученные по протоколу HTTP, передаются открытым текстом и могут быть подделаны.Если в службе используются свойства <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> и <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>, для загрузки данных по протоколу HTTPS используйте URL\-адрес, предоставленный разработчиком службы.  
  
## Проверка безопасности  
 Источники метаданных можно разделить на две большие категории: надежные источники и ненадежные источники.Если вы доверяете источнику и загрузили код клиента и другие метаданные с безопасной конечной точки MEX этого источника, при создании клиента снабдите его правильными учетными данными — никакие дополнительные меры не требуются.  
  
 Однако если клиент и метаданные загружены из источника, о котором мало что известно, обязательно проверьте меры безопасности, используемые в коде.Например, не следует просто создавать клиент, который отправляет ваши личные или финансовые данные в службу, если эта служба не требует как минимум конфиденциальности и целостности.Необходимо доверять владельцу службы в степени, позволяющей раскрывать ему такую информацию, так как она доступна владельцу службы.  
  
 Поэтому, как правило, при использовании кода и метаданных от ненадежного источника проверяйте код и метаданные на предмет соответствия вашим требованиям к безопасности.  
  
## Задание учетных данных клиента  
 Задание учетных данных клиента в клиенте состоит из двух этапов.  
  
1.  Определите *тип учетных данных клиента*, требуемых службой.Это можно сделать одним из двух способов.Во\-первых, если у вас есть документация от разработчика службы, в ней должен быть указан тип учетных данных клиента \(при наличии\), требуемых службой.Во\-вторых, при наличии только файла конфигурации, созданного инструментом Svcutil.exe, можно изучить индивидуальные привязки и определить требуемый тип учетных данных.  
  
2.  Задайте фактические учетные данные клиента.Фактические учетные данные клиента называются *значением учетных данных клиента*, чтобы отличать их от типа учетных данных.Например, если типом учетных данных клиента является сертификат, необходимо предоставить сертификат X.509, выданный службой сертификации, которой доверяет требуемая служба.  
  
### Определение типа учетных данных клиента  
 При наличии файла конфигурации, созданного инструментом Svcutil.exe, изучите раздел [\<привязки\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md), чтобы определить требуемый тип учетных данных клиента.В этом разделе находятся элементы привязки, задающие требования безопасности.Конкретно изучите элемент \<security\> каждой привязки.Этот элемент содержит атрибут `mode`, которому можно присвоить одно из трех возможных значений \(`Message`, `Transport` или `TransportWithMessageCredential`\).Значение этого атрибута определяет режим, задающий, в свою очередь, какой из дочерних элементов является значимым.  
  
 Элемент `<security>` может содержать элемент `<transport>`, элемент `<message>` или оба этих элемента.Значимым элементом является тот, который соответствует режиму безопасности.Например, следующий код задает режим безопасности `"Message"`, а типом учетных данных клиента для элемента `<message>` является `"Certificate"`.В этом случае элемент `<transport>` можно игнорировать.Однако элемент `<message>` задает, что должен быть предоставлен сертификат X.509.  
  
```  
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
  
 Обратите внимание, что если для атрибута `clientCredentialType` задано значение `"Windows"`, как показано с следующем примере, предоставлять фактическое значение учетных данных не требуется.Это связано с тем, что встроенная система безопасности Windows предоставляет фактические учетные данные \(маркер Kerberos\) пользователя, запустившего клиент.  
  
```  
<security mode="Message">  
    <transport clientCredentialType="Windows "   
        realm="" />  
</security>  
```  
  
### Задание значения учетных данных клиента  
 Если установлено, что клиент должен предоставлять учетные данные, используйте подходящий способ настройки клиента.Например, чтобы задать сертификат клиента, используйте метод <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>.  
  
 Обычной формой учетных данных является сертификат X.509.Эти учетные данные можно предоставить двумя способами.  
  
-   Запрограммировав их в коде клиента \(с помощью метода `SetCertificate`\).  
  
 Добавив раздел [\<поведения\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) в файл конфигурации клиента и использовав элемент `clientCredentials` \(показан ниже\).  
  
#### Задание значения \<clientCredentials\> в коде  
 Чтобы задать значение [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) в коде, необходимо обратиться к свойству <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601>.Это свойство возвращает объект <xref:System.ServiceModel.Description.ClientCredentials>, обеспечивающий доступ к различным типам учетных данных, как показано в приведенной ниже таблице.  
  
|Свойство ClientCredential|Описание|Примечания|  
|-------------------------------|--------------|----------------|  
|<xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>|Возвращает <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|Представляет сертификат X.509, предоставляемый клиентом для проверки своей подлинности в службе.|  
|<xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>|Возвращает <xref:System.ServiceModel.Security.HttpDigestClientCredential>|Представляет учетные данные дайджест\-проверки подлинности HTTP.Эти учетные данные представляют собой хэш имени пользователя и пароля.|  
|<xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>|Возвращает <xref:System.ServiceModel.Security.IssuedTokenClientCredential>|Представляет настраиваемый маркер безопасности, выданный службой маркеров безопасности, обычно используемой в сценариях федерации.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>|Возвращает <xref:System.ServiceModel.Security.PeerCredential>|Представляет одноранговые учетные данные для участия в сетке узлов домена Windows.|  
|<xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>|Возвращает <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>|Представляет сертификат X.509, предоставляемый службой для согласования вне полосы.|  
|<xref:System.ServiceModel.Description.ClientCredentials.UserName%2A>|Возвращает <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>|Возвращает пару, содержащую имя пользователя и пароль.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>|Возвращает <xref:System.ServiceModel.Security.WindowsClientCredential>|Представляет учетные данные Windows клиента \(учетные данные Kerberos\).Свойства этого класса доступны только для чтения.|  
  
#### Задание значения \<clientCredentials\> в конфигурации  
 Значения учетных данных задаются с помощью расширения функциональности конечной точки в виде дочерних элементов элемента [\<clientCredentials\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).Используемый элемент зависит от типа учетных данных клиента.Например, в следующем примере кода показана конфигурация для задания сертификата X.509 с помощью \<[\<clientCertificate\>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
```  
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
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Для задания учетных данных клиента в конфигурации добавьте элемент [\<endpointBehaviors\>](../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) в файл конфигурации.Кроме того, добавленный элемент расширения функциональности должен быть связан с конечной точкой службы с помощью атрибута `behaviorConfiguration` элемента [\<endpoint\>](http://msdn.microsoft.com/ru-ru/13aa23b7-2f08-4add-8dbf-a99f8127c017), как показано в приведенном ниже примере.Значение атрибута `behaviorConfiguration` должно соответствовать значению атрибута `name` расширения функциональности.  
  
 `<configuration>`  
  
 `<system.serviceModel>`  
  
 `<client>`  
  
 `<endpoint address="http://localhost/servicemodelsamples/service.svc"`  
  
 `binding="wsHttpBinding"`  
  
 `bindingConfiguration="Binding1"`  
  
 `behaviorConfiguration="myEndpointBehavior"`  
  
 `contract="Microsoft.ServiceModel.Samples.ICalculator" />`  
  
 `</client>`  
  
 `</system.serviceModel>`  
  
 `</configuration>`  
  
> [!NOTE]
>  Некоторые из значений учетных данных клиента не могут задаваться с помощью файлов конфигурации приложения; это, например, значения имени пользователя и пароля или значения пользователя и пароля Windows.Такие значения учетных данных могут быть заданы только в коде.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] задании учетных данных клиента см. в разделе [Практическое руководство. Задание значений учетных данных клиента](../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
> [!NOTE]
>  Значение `ClientCredentialType` игнорируется, если для параметра `SecurityMode` задано значение `"TransportWithMessageCredential",` как показано в следующем примере конфигурации.  
  
```  
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
  
## См. также  
 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>   
 <xref:System.ServiceModel.ClientBase%601>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>   
 [\<привязки\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)   
 [Средство редактирования конфигурации \(SvcConfigEditor.exe\)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)   
 [Защита служб](../../../docs/framework/wcf/securing-services.md)   
 [Обращение к службам с использованием клиента WCF](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)   
 [Практическое руководство. Задание значений учетных данных клиента](../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Как указывать тип учетных данных клиента](../../../docs/framework/wcf/how-to-specify-the-client-credential-type.md)