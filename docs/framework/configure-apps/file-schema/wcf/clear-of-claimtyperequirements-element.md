---
title: '&lt;clear&gt; элемента &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 1e77e3c978c1e385aec983d5e2d4bea64697c43e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145293"
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a>&lt;clear&gt; элемента &lt;claimTypeRequirements&gt;
Указывает, что все типы утверждений в федеративных учетных данных должны быть удалены. Это обеспечивает запуск пустой коллекции.  
  
 \<система. ServiceModel >  
\<привязки >  
\<wsFederatedBinding >  
\<Привязка >  
\<Безопасность >  
\<сообщение >  
\<claimTypeRequirements >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<claimTypeRequirements >](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|Задает коллекцию обязательных типов утверждений. Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.<br /><br /> В федеративном сценарии службы предъявляют требования к входящим учетным данным. Например, входящие учетные данные должны обладать определенным набором типов утверждений. Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
