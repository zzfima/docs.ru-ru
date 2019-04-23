---
title: <add> из <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: fbcb3a07bf40c96a4cd1b2ec87277b6fefdfb89d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164480"
---
# <a name="add-of-baseaddresses"></a>\<Добавить > из \<baseAddresses >
Представляет элемент конфигурации, который задает базовые адреса, используемые узлом службы.  
  
 \<system.ServiceModel>  
\<Клиент >  
\<endpoint>  
\<узел >  
\<baseAddresses >  
\<baseAddress>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`baseAddress`|Строка, которая задает базовый адрес, используемый узлом службы.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<baseAddresses >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Коллекция элементов `baseAddress`.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)
