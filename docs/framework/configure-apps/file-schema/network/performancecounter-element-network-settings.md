---
title: '&lt;performanceCounter&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5879614fd34fe645899f1b95f41e9b0675418292
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltperformancecountergt-element-network-settings"></a>&lt;performanceCounter&gt; элемент (параметры сети)
Включает или отключает счетчики производительности сети.  
  
 \<configuration>  
\<System.NET >  
\<Параметры >  
\<performanceCounters >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Указывает, включены ли счетчики производительности сети. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
 Счетчики производительности сети необходимо включить для использования в файле конфигурации. Все счетчики производительности сети включаются и отключаются с помощью одного параметра в файле конфигурации. Включить или отключить отдельные счетчики производительности сети невозможно. Дополнительные сведения о конкретных сетевых счетчиках производительности см. в разделе [счетчики производительности сети](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).  
  
 Значение по умолчанию — что производительности сети счетчики отключены.  
  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> Свойство может использоваться для получения текущего значения **включен** атрибут из применимые файлы конфигурации.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как настроить <xref:System.Net> и связанных пространствах имен, чтобы включить счетчики производительности сети.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [Счетчики производительности сети](http://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd)
