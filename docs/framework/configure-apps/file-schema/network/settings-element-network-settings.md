---
title: Элемент <settings> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: 12797e2f06d03aacd81700eae57d5776c1a6f354
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663999"
---
# <a name="settings-element-network-settings"></a>\<Элемент параметров > (параметры сети)
Настраивает основные параметры сети для пространства имен <xref:System.Net?displayProperty=nameWithType>.  
  
 \<configuration>  
\<> System. NET  
\<> параметров  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[httpListener](httplistener-element-network-settings.md)|Настраивает параметры, используемые <xref:System.Net.HttpListener> классом.|  
|[httpWebRequest](httpwebrequest-element-network-settings.md)|Настраивает параметры веб-запроса.|  
|[Протокол](ipv6-element-network-settings.md)|Включает поддержку протокола IP версии 6 (IPv6).|  
|[\<Элемент performanceCounter > (параметры сети)](performancecounter-element-network-settings.md)|Включает счетчики производительности сети.|  
|[servicePointManager](servicepointmanager-element-network-settings.md)|Настраивает подключения к сетевым ресурсам.|  
|[фиксатор](socket-element-network-settings.md)|Указывает, используют ли операции сокета порты завершения.|  
|[\<Элемент > Вебпроксискрипт (параметры сети)](webproxyscript-element-network-settings.md)|Настраивает характеристики сценария, используемого для обнаружения веб-прокси.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="see-also"></a>См. также

- <xref:System.Net?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
