---
title: '&lt;Узел&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 1fb35058d407d0fbae78092bb4ccd45b0aaa40e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702032"
---
# <a name="lthostgt"></a>&lt;Узел&gt;
Задает параметры узла службы.  
  
 \<system.ServiceModel>  
\<Services >  
\<службы >  
\<узел >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<baseAddresses >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.|  
|[\<время ожидания >](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<службы >](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Задает параметры для службы Windows Communication Foundation (WCF).|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)
