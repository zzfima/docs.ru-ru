---
title: <add> из <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 7e7f0eac41e69e959aa6c4f8f3cfb488d4ea2917
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926799"
---
# <a name="add-of-claimtyperequirements"></a>\<Добавление > \<> claimTypeRequirements
Задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных. Например, службы предъявляют требования к входящим учетным данным, которые должны обладать определенным набором типов утверждений.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<> безопасности  
\<issuedTokenParameters >  
\<claimTypeRequirements >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|claimType|Универсальный код ресурса (URI), определяющий тип утверждения. Например, для приобретения товара с веб-узла пользователь должен представить действительную кредитную карту с достаточным кредитным лимитом. Типом утверждения будет универсальный код ресурса (URI) кредитной карты.|  
|isOptional|Логическое значение, указывающее, является ли утверждение необязательным. Если утверждение является обязательным, установите для этого атрибута значение `false`.<br /><br /> Этот атрибут можно использовать, если служба запрашивает определенные данные, но они не являются необходимыми. Например, если требуется, чтобы пользователь ввел имя, фамилию и адрес, а указание номера телефона является необязательным.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<claimTypeRequirements >](claimtyperequirements-element.md)|Задает коллекцию обязательных типов утверждений.<br /><br /> В федеративном сценарии службы предъявляют требования к входящим учетным данным. Например, входящие учетные данные должны обладать определенным набором типов утверждений. Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.|  
  
## <a name="remarks"></a>Примечания  
 В федеративном сценарии службы предъявляют требования к входящим учетным данным. Например, входящие учетные данные должны обладать определенным набором типов утверждений. Это требование представлено в политике безопасности. Когда клиент запрашивает учетные данные в федеративной службе (например, CardSpace), требования помещаются в запрос маркера (RequestSecurityToken), что позволяет федеративной службе выдать учетные данные, полностью отвечающие требованиям.  
  
## <a name="example"></a>Пример  
 Следующая конфигурация добавляет два требования типа утверждения к привязке безопасности.  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<claimTypeRequirements >](claimtyperequirements-element.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
- [Практическое руководство. Создание пользовательской привязки с помощью SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Безопасность пользовательской привязки](../../../wcf/samples/custom-binding-security.md)
