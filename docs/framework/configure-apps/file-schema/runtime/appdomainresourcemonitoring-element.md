---
title: '&lt;appDomainResourceMonitoring&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc507d0cf81bf2bc11edfc0b5efb08c462726b88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727876"
---
# <a name="ltappdomainresourcemonitoringgt-element"></a>&lt;appDomainResourceMonitoring&gt; элемент
Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.  
  
 \<configuration>  
\<Среда выполнения >  
\<appDomainResourceMonitoring >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Определяет, будет ли среда выполнения собирать статистические данные для отслеживания ресурсов домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`true`|Сбор статистики для отслеживания ресурсов домена приложения.|  
|`false`|Статистические данные для отслеживания ресурсов домена приложения не собираются.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Отслеживание ресурсов домена приложения доступен через класс домена управляемого приложения, размещение [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) интерфейс и трассировка событий Windows (ETW). При включенном наблюдении за, статистические данные собираются для всех доменов приложений в процессе, в течение жизненного цикла процесса.  
  
 Чтобы включить мониторинг из управляемого кода, используйте <xref:System.AppDomain.MonitoringIsEnabled%2A> свойство.  
  
 Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздних версий.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить отслеживание ресурсов домена приложения.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
