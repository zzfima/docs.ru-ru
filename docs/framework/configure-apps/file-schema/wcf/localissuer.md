---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 4ec5a99139112ae600c1c2bc44feb6d3f62da1e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931742"
---
# <a name="localissuer"></a>\<Локалиссуер >
Указывает адрес и привязку локального издателя, используемого для получения маркера безопасности.  
  
 \<системой. > ServiceModel  
\<> поведения  
раздел endpointBehaviors  
\<> поведения  
\<> clientCredentials  
\<issuedToken >  
\<Локалиссуер >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|адрес|Обязательная строка. Указывает универсальный код ресурса (URI) локального издателя.|  
|привязка|Необязательная строка. Одна из привязок, предоставляемых системой. Список см. в разделе [привязки, предоставляемые системой](../../../wcf/system-provided-bindings.md).|  
|bindingConfiguration|Необязательная строка. Указывает конфигурацию привязки в файле конфигурации.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> удостоверений](identity.md)|Указывает идентификационные данные для локального издателя.|  
|[\<заголовки >](headers-element.md)|Коллекция заголовков адреса, требуемых для правильного обращения к локальному издателю. Заголовок в эту коллекцию можно добавить с помощью ключевого слова `add`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<issuedToken >](issuedtoken.md)|Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 При получении маркера от службы маркеров безопасности (STS) в клиентском приложении должны быть заданы адрес и привязка для установления соединения с STS. Если компонент не предоставляет URL-адрес для службы маркеров безопасности или если адресом издателя Федеративной привязки является `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` или `null`, канал Windows Communication Foundation клиента (WCF) использует значения, заданные параметром <xref:System.ServiceModel.WSFederationHttpBinding> `address` и`binding` для взаимодействия с STS для получения выданного маркера. Дополнительные сведения о настройке локального издателя см. в разделе [как Настройка локального издателя](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="example"></a>Пример  
 В следующем примере устанавливаются атрибуты `address`, `binding` и `bindingConfiguration` элемента `localIssuer`.  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Практическое руководство. Настройка локального издателя](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Идентификация и проверка подлинности службы](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Федерация и выданные маркеры](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Защита клиентов](../../../wcf/securing-clients.md)
- [Практическое руководство. Создание федеративного клиента](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Федерация и выданные маркеры](../../../wcf/feature-details/federation-and-issued-tokens.md)
