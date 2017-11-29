---
title: "Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 83e455c2377168c316bf34c25b687cde48b0fa3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a>Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса
При использовании в безопасном сеансе маркера контекста безопасности (SCT) с отслеживанием состояния сеанс может сохраняться и при перезапуске службы. Например, если в безопасном сеансе используется маркер SCT без отслеживания состояния, то при сбросе служб IIS данные сеанса, связанного со службой, будут потеряны. В состав данных сеанса входит кэш маркера SCT. Поэтому в следующий раз, когда клиент отправляет в службу маркер SCT без отслеживания состояния, возвращается ошибка, так как невозможно извлечь ключ, связанный с этим маркером SCT. Однако если используется маркер SCT с отслеживанием состояния, то ключ, связанный с маркером SCT, содержится в этом маркере SCT. Так как ключ содержится в маркере SCT и, следовательно, в сообщении, перезапуск службы не влияет на безопасный сеанс. По умолчанию для безопасных сеансов в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] используются маркеры SCT без отслеживания состояния. В этом разделе описывается, как использовать в безопасном сеансе маркеры SCT с отслеживанием состояния.  
  
> [!NOTE]
>  Маркеры SCT с отслеживанием состояния не могут использоваться в безопасном сеансе, связанном с контрактом, унаследованным от <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
> [!NOTE]
>  Для приложений, использующих в безопасных сеансах маркеры SCT с отслеживанием состояния, идентификатором потока для службы должна быть учетная запись пользователя, имеющая связанный с ней профиль пользователя. Если служба запущена с учетной записью, не имеющей профиля пользователя (например, `Local Service`), возможно возникновение исключения.  
  
> [!NOTE]
>  Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера SCT с отслеживанием состояния. При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a>Использование маркеров SCT с отслеживанием состояния в безопасном сеансе  
  
-   Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом, использующим маркер SCT с отслеживанием состояния.  
  
    1.  Определите пользовательскую привязку, добавив [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) в файл конфигурации для службы.  
  
        ```xml  
        <customBinding>  
        ```  
  
    2.  Добавить [ \<привязки >](../../../../docs/framework/misc/binding.md) дочернего элемента [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Укажите имя привязки, задав для атрибута `name` имя, уникальное в пределах этого файла конфигурации.  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  Укажите режим проверки подлинности для сообщений, отправляемых с этой службой, добавив [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) дочернего элемента [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Укажите, что используется безопасный сеанс, задав для атрибута `authenticationMode` значение `SecureConversation`. Укажите, что используются маркеры SCT с отслеживанием состояния, задав для атрибута `requireSecurityContextCancellation` значение `false`.  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  Укажите способ проверки подлинности клиента при установлен безопасный сеанс, добавив [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) дочернего элемента [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Укажите, как производится проверка подлинности клиента, задав атрибут `authenticationMode`.  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  Задания кодирования сообщений, добавив элемент кодирования, таких как [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6.  Укажите транспорта, добавив элемент транспорта, таких как [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
        ```xml  
        <httpTransport />  
        ```  
  
     В следующем примере кода с помощью конфигурации задается пользовательская привязка, которая может использоваться сообщениями с маркерами SCT с отслеживанием состояния в безопасном сеансе.  
  
    ```xml  
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
  
## <a name="example"></a>Пример  
 В следующем примере кода создается пользовательская привязка, которая использует режим проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> для начальной загрузки безопасного сеанса.  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 При использовании проверки подлинности Windows в сочетании с маркером SCT с отслеживанием состояния [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не заносит в свойство <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> фактический идентификатор вызывающей стороны, но вместо этого задает это свойство как анонимное. Поскольку безопасность [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должна воссоздавать содержимое контекста безопасности службы для каждого запроса из входящего маркера SCT, сервер не ведет учета безопасных сеансов в памяти. Поскольку выполнить сериализацию экземпляра <xref:System.Security.Principal.WindowsIdentity> в маркер SCT невозможно, свойство <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> возвращает анонимный идентификатор.  
  
 Следующая конфигурация демонстрирует это расширение функциональности.  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
