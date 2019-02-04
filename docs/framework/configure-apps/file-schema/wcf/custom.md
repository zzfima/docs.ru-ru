---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 5ff066c32f7d08ec989d6cd04e16c89f0a36f6fa
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675027"
---
# <a name="custom"></a>\<пользовательские >
Задает параметры службы пользовательского распознавателя одноранговых узлов.  
  
\<system.serviceModel>  
\<привязки >  
\<netPeerBinding >  
\<Привязка >  
\<resolver>  
\<пользовательские >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`address`|URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.|  
|`resolverType`|Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента. Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<заголовки >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<resolver>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки. Дополнительные сведения о создании пользовательского распознавателя см. в разделе [Добавление в приложение PeerChannel пользовательского распознавателя](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [Одноранговые распознаватели](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [Добавление в приложение PeerChannel пользовательского распознавателя](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))
