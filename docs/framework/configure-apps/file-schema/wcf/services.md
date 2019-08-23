---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: c00d5fe3e8b2ba05843e09aca6aaa79386541bad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937192"
---
# <a name="services"></a>\<службы >
Службы задаются в разделе `services` файла конфигурации. Для каждой службы используется собственный раздел конфигурации `service`.  
  
 \<системой. > ServiceModel  
  
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
 Отсутствуют  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> службы](service.md)|Определяет контракт службы, поведение и конечные точки конкретной службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ServicesSection>
