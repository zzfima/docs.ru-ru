---
title: Элемент <system.web> (веб-параметры)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152845"
---
# <a name="systemweb-element-web-settings"></a>\<system.web> элемент (веб-настройки)
Содержит информацию о том, как ASP.NET слой хостинга управляет поведением в масштабах всего процесса.  
  
[**\<конфигурация>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Определяет настройки конфигурации для пулов приложений IIS в файле aspnet.config.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<конфигурация>](../configuration-element.md)|Определяет корневой элемент в каждом файле конфигурации, который используется приложениями общего языка и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Remarks  

Элемент `system.web` и его `applicationPool` элемент ребенка были добавлены в рамку .NET по состоянию на .NET Framework 3.5 SP1. При запуске IIS 7.0 или более поздних версий в интегрированном режиме эта комбинация элементов позволяет настроить, как ASP.NET управляет потоками и как он выстраивает в очередь запросы при размещении ASP.NET в пуле приложений IIS. Если вы запустите IIS 7.0 или более поздние версии в режиме Classic или ISAPI, эти параметры игнорируются.  
  
## <a name="example"></a>Пример  

В следующем примере показано, как настроить поведение ASP.NET процесса в файле aspnet.config, когда ASP.NET размещается в пуле приложений IIS. Пример предполагает, что IIS работает в интегрированном режиме и что приложение использует .NET Framework 3.5 SP1 или более позднюю версию. Такое поведение не происходит в версиях рамочного соглашения .NET раньше, чем .NET Framework 3.5 SP1. Значения в примере являются значениями по умолчанию.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Сведения об элементе  
  
|||  
|-|-|  
|Пространство имен||  
|Имя схемы||  
|Файл проверки||  
|Может быть пустым||  
  
## <a name="see-also"></a>См. также раздел

- [\<applicationPool> элемент (веб-настройки)](applicationpool-element-web-settings.md)
