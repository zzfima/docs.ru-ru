---
title: Элемент <appDomainResourceMonitoring>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154380"
---
# <a name="appdomainresourcemonitoring-element"></a>\<appDomainResourceMonitoring> Элемент
Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Уточняется, собирает ли время выполнения статистику для мониторинга ресурсов доменов приложений.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`true`|Собрана статистика мониторинга ресурсов доменов приложений.|  
|`false`|Статистика мониторинга ресурсов доменов приложений не собирается.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  
 Мониторинг ресурсов доменов приложений доступен через управляемый класс доменов приложений, интерфейс [хостинга ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) и отслеживание событий для Windows (ETW). При включении мониторинга собираются статистические данные по всем областям приложений в процессе процесса.  
  
 Для обеспечения мониторинга из <xref:System.AppDomain.MonitoringIsEnabled%2A> управляемого кода используйте свойство.  
  
 Этот элемент конфигурации доступен только в системе .NET 4 и позже.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить мониторинг ресурсов домена приложений.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
