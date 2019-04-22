---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094181"
---
# <a name="policyimporter"></a>\<policyImporter >
Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.  
  
 \<system.ServiceModel>  
\<Клиент >  
\<метаданные >  
\<policyImporters >  
\<policyImporter >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`type`|Тип этого элемента.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<policyImporters >](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.|  
  
## <a name="remarks"></a>Примечания  
 Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [Конфигурация клиента WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [Клиенты](../../../../../docs/framework/wcf/feature-details/clients.md)
