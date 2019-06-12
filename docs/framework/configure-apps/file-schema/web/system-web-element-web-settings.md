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
ms.openlocfilehash: 687398e47ad95e3234c29571eeeac0c9d2d83a39
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832786"
---
# <a name="systemweb-element-web-settings"></a>\<System.Web > элемент (веб-параметры)
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
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Задает параметры конфигурации для пулов приложений IIS в файле aspnet.config.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Указывает корневой элемент в любом файле конфигурации, который используется среда CLR и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Примечания  
 `system.web` Элемента и его дочерних `applicationPool` элемента были добавлены в .NET Framework, начиная с .NET Framework 3.5 SP1. При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздних версий в интегрированном режиме это сочетание элементов позволяет настроить, как ASP.NET управляет потоками и как помещает запросы в очередь, когда ASP.NET размещен в пуле приложений IIS. При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздних версий в классическом режиме или режиме ISAPI, эти параметры игнорируются.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как настроить поведение всего процесса ASP.NET в файле aspnet.config, когда ASP.NET размещен в пуле приложений IIS. В примере предполагается, что службы IIS выполняются в интегрированном режиме, и что приложение использует .NET Framework 3.5 SP1 или более поздней версии. Это происходит в версиях .NET Framework более ранней, чем .NET Framework 3.5 SP1. В примере значения являются значениями по умолчанию.  
  
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
