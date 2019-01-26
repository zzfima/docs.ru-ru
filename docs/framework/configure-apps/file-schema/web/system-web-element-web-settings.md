---
title: '&lt;System.Web&gt; элемент (веб-параметры)'
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 29aa97808f3595313b68072a910afb1354d45c6d
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084423"
---
# <a name="ltsystemwebgt-element-web-settings"></a>&lt;System.Web&gt; элемент (веб-параметры)
Содержит сведения об управлении поведению процессов, используемые уровнем размещения ASP.NET.  
  
 \<configuration>  
\<System.Web > элемент (веб-параметры)  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Задает параметры конфигурации для пулов приложений IIS в файле aspnet.config.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Указывает корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .|  
  
## <a name="remarks"></a>Примечания  
 `system.web` Элемента и его дочерних `applicationPool` элемента были добавлены в [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] начиная с версии [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздних версий в интегрированном режиме это сочетание элементов позволяет настроить, как ASP.NET управляет потоками и как помещает запросы в очередь, когда ASP.NET размещен в пуле приложений IIS. При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздних версий в классическом режиме или режиме ISAPI, эти параметры игнорируются.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как настроить поведение всего процесса ASP.NET в файле aspnet.config, когда ASP.NET размещен в пуле приложений IIS. В примере предполагается, что службы IIS выполняются в интегрированном режиме, и что приложение использует [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] или более поздней версии. Этого не происходит в версиях [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] более ранней, чем [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. В примере значения являются значениями по умолчанию.  
  
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
  
## <a name="see-also"></a>См. также
- [Элемент \<applicationPool> (веб-параметры)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
