---
title: '&lt;службы&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: a48bd0ac30c1a85602122b2fd9213c2aa5159e91
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148101"
---
# <a name="ltservicesgt"></a>&lt;службы&gt;
Службы задаются в разделе `services` файла конфигурации. Для каждой службы используется собственный раздел конфигурации `service`.  
  
 \<система. ServiceModel >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<службы >](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Определяет контракт службы, поведение и конечные точки конкретной службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServicesSection>
