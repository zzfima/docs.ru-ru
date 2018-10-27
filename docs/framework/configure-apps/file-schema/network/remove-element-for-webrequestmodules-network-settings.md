---
title: '&lt;Удалить&gt; элемент для webRequestModules (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: 2f787206c503c047a34383e12c5676296e39c1fe
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190753"
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a>&lt;Удалить&gt; элемент для webRequestModules (параметры сети)
Удаляет пользовательский модуль веб-запросов из приложения.  
  
 \<configuration>  
\<System.NET >  
\<webRequestModules >  
\<Удалить >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`prefix`|Префикс URI для запросов, обрабатываемых этот модуль веб-запросов.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Задает модули, используемые для запроса данных от сетевых узлов.|  
  
## <a name="remarks"></a>Примечания  
 `remove` Элемент удаляет зарегистрированный модуль веб-запросов для заданного префикса URI.  
  
 Значение для `prefix` атрибут должен быть из ведущих символов является допустимым URI — например, "`http`«, или"`http://www.contoso.com`«.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  

В следующем примере удаляется существующий модуль веб-запросов для HTTP и затем регистрирует новый пользовательский модуль веб-запросов для HTTP запрашивает `www.contoso.com`.
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
- <xref:System.Net.WebRequest>  
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
