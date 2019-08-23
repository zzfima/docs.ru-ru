---
title: <add> из <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: a94c5144d907c26e6f5eef09b1a17b17eb6c9e0f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920223"
---
# <a name="add-of-baseaddresses"></a>\<Добавление > \<> baseAddresses
Представляет элемент конфигурации, который задает базовые адреса, используемые узлом службы.  
  
 \<системой. > ServiceModel  
\<> клиента  
\<> конечной точки  
\<> узла  
\<baseAddresses >  
\<> baseAddress  
  
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
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<baseAddresses >](baseaddresses.md)|Коллекция элементов `baseAddress`.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [Размещение](../../../wcf/feature-details/hosting.md)
