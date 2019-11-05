---
title: Элемент <appDomainResourceMonitoring>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 991833500cae4d96e9c28f7e94ca366e9b976a9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118258"
---
# <a name="appdomainresourcemonitoring-element"></a>\<Аппдомаинресаурцемониторинг > элемент
Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<аппдомаинресаурцемониторинг >**  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, собирает ли среда выполнения статистические данные для отслеживания ресурсов домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|значения|Описание|  
|-----------|-----------------|  
|`true`|Собираются статистические данные для отслеживания ресурсов домена приложения.|  
|`false`|Статистика по мониторингу ресурсов домена приложений не собирается.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Заметки  
 Мониторинг ресурсов домена приложений доступен через класс домена управляемого приложения, интерфейс размещения [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) и трассировку событий для Windows (ETW). При включении мониторинга статистика собирается для всех доменов приложений в процессе в течение жизненного цикла процесса.  
  
 Чтобы включить мониторинг из управляемого кода, используйте свойство <xref:System.AppDomain.MonitoringIsEnabled%2A>.  
  
 Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.  
  
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
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
