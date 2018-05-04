---
title: '&lt;resolver&gt;'
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: f29c34f53a8bdaee4b30c72bb5d764ae3935fe7a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltresolvergt"></a>&lt;resolver&gt;
Указывает распознаватель одноранговых узлов, используемый для распознавания идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, которые представляют несколько узлов, входящих в сетку.  
  
 \<система. ServiceModel >  
\<привязки >  
\<netPeerBinding >  
\<Привязка >  
\<Сопоставитель >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`mode`|Строка, которая указывает, зависит ли экземпляр распознавателя одноранговых узлов, связанный с данной службой, от PNRP, является ли он пользовательским распознавателем или определяется автоматически. Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.|  
|`referralPolicy`|Строка, указывающая, каким образом отсылки распределяются между одноранговыми узлами. Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<заголовки >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Задает параметры службы пользовательского распознавателя одноранговых узлов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../../../docs/framework/misc/binding.md)|Определяет все возможности [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## <a name="remarks"></a>Примечания  
 Распознаватель одноранговых узлов представляет собой службу обнаружения, используемую одноранговыми каналами для поиска одноранговых узлов, участвующих в сетке с IP-адресами. Он также используется для «регистрации» узла в сетке с IP-адресами; с помощью такого механизма одноранговый узел становится известным и доступным из сетки с IP-адресами. Дополнительные сведения о распознавателей одноранговых узлов см. в разделе [распознавателей одноранговых узлов](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [Одноранговые распознаватели](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [Добавление пользовательского арбитра конфликтов в приложении PeerChannel](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
