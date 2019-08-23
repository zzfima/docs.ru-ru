---
title: <add> из <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920113"
---
# <a name="add-of-issuerchannelbehaviors"></a>\<Добавление > \<> issuerChannelBehaviors

Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.

> [!NOTE]
> Если какое- [ \<](clientcredentials.md) либо поведение конечной точки содержит элемент ClientCredentials >, будет создано исключение.

\<системой. ServiceModel > \
\<поведения > \
поведение раздела \<EndpointBehaviors > \
\<> clientCredentials \
\<issuedToken > \
\<Элемент > issuerChannelBehaviors \
\<add>

## <a name="syntax"></a>Синтаксис

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описываются атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|issuerAddress|Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.|
|behaviorConfiguration|Имя поведения конечной точки, определенное в том же файле конфигурации.|

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<issuerChannelBehaviors >](issuerchannelbehaviors-element.md)|Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) для использования при взаимодействии с указанными службами маркеров службы.|

## <a name="remarks"></a>Примечания

`issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными. `behaviorConfiguration`Указывает на поведение конечной точки, используемое приложением в каналах, созданных Windows Communication Foundation (WCF) для получения выданных маркеров от служб маркеров безопасности.

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Идентификация и проверка подлинности службы](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Федерация и выданные маркеры](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Защита клиентов](../../../wcf/securing-clients.md)
- [Практическое руководство. Создание федеративного клиента](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Практическое руководство. Настройка локального издателя](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Федерация и выданные маркеры](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors >](issuerchannelbehaviors-element.md)
