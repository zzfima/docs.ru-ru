---
title: Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
ms.openlocfilehash: 02e0403f9ae5bb437145fa3a015edc69b884c4d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185019"
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a>Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса
При использовании в безопасном сеансе маркера контекста безопасности (SCT) с отслеживанием состояния сеанс может сохраняться и при перезапуске службы. Например, если в безопасном сеансе используется маркер SCT без учета состояния, то при сбросе служб IIS данные сеанса, связанного со службой, будут потеряны. В состав данных сеанса входит кэш маркера SCT. Поэтому в следующий раз, когда клиент отправляет в службу маркер SCT без учета состояния, возвращается ошибка, так как невозможно извлечь ключ, связанный с этим маркером SCT. Однако если используется маркер SCT с отслеживанием состояния, то ключ, связанный с маркером SCT, содержится в этом маркере SCT. Так как ключ содержится в маркере SCT и, следовательно, в сообщении, перезапуск службы не влияет на безопасный сеанс. По умолчанию Фонд связи Windows (WCF) использует SCTбеза без состояния в безопасном сеансе. В этом разделе описывается, как использовать в безопасном сеансе маркеры SCT с отслеживанием состояния.  
  
> [!NOTE]
> Маркеры SCT с отслеживанием состояния не могут использоваться в безопасном сеансе, связанном с контрактом, унаследованным от <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
> [!NOTE]
> Для приложений, использующих в безопасных сеансах маркеры SCT с отслеживанием состояния, идентификатором потока для службы должна быть учетная запись пользователя, имеющая связанный с ней профиль пользователя. Если служба запущена с учетной записью, не имеющей профиля пользователя (например, `Local Service`), возможно возникновение исключения.  
  
> [!NOTE]
> Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера SCT с отслеживанием состояния. При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a>Использование маркеров SCT с отслеживанием состояния в безопасном сеансе  
  
- Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом, использующим маркер SCT с отслеживанием состояния.  
  
    1. Определите пользовательский привязку, добавив [ \<пользовательский>в](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) файл конфигурации для службы.  
  
        ```xml  
        <customBinding>  
        ```  
  
    2. Добавьте [ \<связывающий элемент>](../../configure-apps/file-schema/wcf/bindings.md) ребенка в [ \<пользовательский>Binding. ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
  
         Укажите имя привязки, задав для атрибута `name` имя, уникальное в пределах этого файла конфигурации.  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3. Укажите режим проверки подлинности для сообщений, отправленных в эту службу и из нее, добавив элемент [ \<безопасности>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) ребенка в [ \<пользовательскийОбязательный>. ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
  
         Укажите, что используется безопасный сеанс, задав для атрибута `authenticationMode` значение `SecureConversation`. Укажите, что используются маркеры SCT с отслеживанием состояния, задав для атрибута `requireSecurityContextCancellation` значение `false`.  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4. Укажите, как клиент проверяется на подлинность во время создания безопасного сеанса, добавляя в [ \<>безопасности ](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<элемент защищенного разговора>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) ребенка.  
  
         Укажите, как производится проверка подлинности клиента, задав атрибут `authenticationMode`.  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5. Укажите кодирование сообщения, добавив элемент кодирования, например [ \<>textMessageEncoding. ](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6. Укажите транспорт, добавив транспортный элемент, такой как [ \<httpTransport>. ](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)  
  
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
  
 Когда аутентификация Windows используется в сочетании с stateful <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> SCT, WCF не заполняет свойство с идентификацией фактического вызывающего абонента, но вместо этого устанавливает свойство к анонимности. Поскольку безопасность WCF должна повторно создавать содержимое контекста безопасности службы для каждого запроса от входящего SCT, сервер не отслеживает сеанс безопасности в памяти. Поскольку выполнить сериализацию экземпляра <xref:System.Security.Principal.WindowsIdentity> в маркер SCT невозможно, свойство <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> возвращает анонимный идентификатор.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [\<обычайОбязательный>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
