---
title: Элемент <webProxyScript> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: e823d6065ea23f3a47dad6853a1b9e1237a616c9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257828"
---
# <a name="webproxyscript-element-network-settings"></a>\<webProxyScript > (сетевые параметры)
Настраивает характеристики сценария, используемого для обнаружения веб-прокси.  
  
 \<configuration>  
\<system.net>  
\<Параметры >  
\<webProxyScript >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`downloadTimeout`|Указывает максимальное время для загрузки скрипта в часы, минуты и секунды. Значение по умолчанию — одна минута.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="see-also"></a>См. также
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
