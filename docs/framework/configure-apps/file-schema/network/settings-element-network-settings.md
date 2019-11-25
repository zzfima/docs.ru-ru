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
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089108"
---
# <a name="settings-element-network-settings"></a>Элемент > параметров \<(параметры сети)
Настраивает основные параметры сети для пространства имен <xref:System.Net?displayProperty=nameWithType>.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**Параметры**\<

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
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[httpListener](httplistener-element-network-settings.md)|Настраивает параметры, используемые классом <xref:System.Net.HttpListener>.|  
|[httpWebRequest](httpwebrequest-element-network-settings.md)|Настраивает параметры веб-запроса.|  
|[Протокол](ipv6-element-network-settings.md)|Включает поддержку протокола IP версии 6 (IPv6).|  
|[\<элемента > performanceCounter (параметры сети)](performancecounter-element-network-settings.md)|Включает счетчики производительности сети.|  
|[servicePointManager](servicepointmanager-element-network-settings.md)|Настраивает подключения к сетевым ресурсам.|  
|[фиксатор](socket-element-network-settings.md)|Указывает, используют ли операции сокета порты завершения.|  
|[Элемент \<Вебпроксискрипт > (параметры сети)](webproxyscript-element-network-settings.md)|Настраивает характеристики сценария, используемого для обнаружения веб-прокси.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="remarks"></a>Заметки  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="see-also"></a>См. также

- <xref:System.Net?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
