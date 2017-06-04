---
title: "Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса
При использовании в безопасном сеансе маркера контекста безопасности \(SCT\) с отслеживанием состояния сеанс может сохраняться и при перезапуске службы.Например, если в безопасном сеансе используется маркер SCT без отслеживания состояния, то при сбросе служб IIS данные сеанса, связанного со службой, будут потеряны.В состав данных сеанса входит кэш маркера SCT.Поэтому в следующий раз, когда клиент отправляет в службу маркер SCT без отслеживания состояния, возвращается ошибка, так как невозможно извлечь ключ, связанный с этим маркером SCT.Однако если используется маркер SCT с отслеживанием состояния, то ключ, связанный с маркером SCT, содержится в этом маркере SCT.Так как ключ содержится в маркере SCT и, следовательно, в сообщении, перезапуск службы не влияет на безопасный сеанс.По умолчанию для безопасных сеансов в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] используются маркеры SCT без отслеживания состояния.В этом разделе описывается, как использовать в безопасном сеансе маркеры SCT с отслеживанием состояния.  
  
> [!NOTE]
>  Маркеры SCT с отслеживанием состояния не могут использоваться в безопасном сеансе, связанном с контрактом, унаследованным от <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
> [!NOTE]
>  Для приложений, использующих в безопасных сеансах маркеры SCT с отслеживанием состояния, идентификатором потока для службы должна быть учетная запись пользователя, имеющая связанный с ней профиль пользователя.Если служба запущена с учетной записью, не имеющей профиля пользователя \(например, `Local Service`\), возможно возникновение исключения.  
  
> [!NOTE]
>  Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера SCT с отслеживанием состояния.При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
### Использование маркеров SCT с отслеживанием состояния в безопасном сеансе  
  
-   Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом, использующим маркер SCT с отслеживанием состояния.  
  
    1.  Определите пользовательскую привязку, добавив [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) в файл конфигурации службы.  
  
        ```  
        <customBinding>  
        ```  
  
    2.  Добавьте дочерний элемент [\<привязка\>](../../../../docs/framework/misc/binding.md) в элемент [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Укажите имя привязки, задав для атрибута `name` имя, уникальное в пределах этого файла конфигурации.  
  
        ```  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  Укажите режим проверки подлинности для сообщений, отправляемых в эту службу и из нее, добавив дочерний элемент [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) в элемент [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Укажите, что используется безопасный сеанс, задав для атрибута `authenticationMode` значение `SecureConversation`.Укажите, что используются маркеры SCT с отслеживанием состояния, задав для атрибута `requireSecurityContextCancellation` значение `false`.  
  
        ```  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  Укажите, как производится проверка подлинности клиента во время установления безопасного сеанса, добавив дочерний элемент [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) в элемент [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Укажите, как производится проверка подлинности клиента, задав атрибут `authenticationMode`.  
  
        ```  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  Укажите кодировку сообщения, добавив элемент кодирования, такой как [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
        ```  
        <textMessageEncoding />  
        ```  
  
    6.  Укажите транспорт, добавив транспортный элемент, такой как [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
        ```  
        <httpTransport />  
        ```  
  
     В следующем примере кода с помощью конфигурации задается пользовательская привязка, которая может использоваться сообщениями с маркерами SCT с отслеживанием состояния в безопасном сеансе.  
  
    ```  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## Пример  
 В следующем примере кода создается пользовательская привязка, которая использует режим проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode> для начальной загрузки безопасного сеанса.  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 При использовании проверки подлинности Windows в сочетании с маркером SCT с отслеживанием состояния [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не заносит в свойство <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> фактический идентификатор вызывающей стороны, но вместо этого задает это свойство как анонимное.Поскольку безопасность [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должна воссоздавать содержимое контекста безопасности службы для каждого запроса из входящего маркера SCT, сервер не ведет учета безопасных сеансов в памяти.Поскольку выполнить сериализацию экземпляра <xref:System.Security.Principal.WindowsIdentity> в маркер SCT невозможно, свойство <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> возвращает анонимный идентификатор.  
  
 Следующая конфигурация демонстрирует это поведение.  
  
```  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
  
```  
  
## См. также  
 [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)