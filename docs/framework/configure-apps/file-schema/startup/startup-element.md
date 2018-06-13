---
title: '&lt;При запуске&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 60699f0335bb35589341558800cfd64503d0aa0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748432"
---
# <a name="ltstartupgt-element"></a>&lt;При запуске&gt; элемент
Указывает информация запуска среды CLR.  
  
 \<configuration>  
\<При запуске >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|Необязательный атрибут.<br /><br /> Указывает, следует ли включить [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] политике активации среды выполнения или использовать [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] политике активации.|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>Атрибут useLegacyV2RuntimeActivationPolicy  
  
|Значение|Описание|  
|-----------|-----------------|  
|`true`|Включить [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] политике активации среды выполнения для выбранной среды выполнения, является привязка методы активации прежних версий среды выполнения (например, [CorBindToRuntimeEx-функция](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) в среду выполнения из файла конфигурации, а не выбраны ограниченного их в среде CLR версии 2.0. Таким образом Если вы выбрали CLR версии 4 или более поздней версии из файла конфигурации, смешанных сборок, созданных в более ранних версиях платформы .NET Framework, загружаются с выбранной версией среды CLR. Установка этого значения предотвращает CLR версии 1.1 или среда CLR версии 2.0 загрузку в один процесс, эффективно отключив функцию side-by-side-process.|  
|`false`|Используйте политику активации по умолчанию для [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] и более поздних версиях это разрешить методы активации для загрузки среды CLR версии 1.1 или 2.0 в процесс прежних версий среды выполнения. Установка этого значения предотвращает сборки смешанного режима от загрузки в .NET Framework 4 или более поздней версии, если они были созданы с .NET Framework 4 или более поздней версии. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR. Приложения, собранные с помощью версии 1.1 или более поздней, должны использовать  **\<supportedRuntime >** элемента.|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Примечания  
 **\<SupportedRuntime >** элемент должен использоваться всеми приложениями, собранными с помощью версии 1.1 или более поздней версии среды выполнения. Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать  **\<requiredRuntime >** элемента.  
  
 Код запуска для приложения, размещенного в Internet Explorer не учитывает  **\<запуска >** и его дочерних элементов.  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Атрибут useLegacyV2RuntimeActivationPolicy  
 Этот атрибут полезен, если приложение использует устаревшие активации пути, такие как [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), и нужно, чтобы эти пути для активации версии 4 среды CLR вместо более ранней версии, или если ваше приложение созданные с помощью [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] но имеет зависимость от сборки смешанного режима, созданного с помощью более ранней версии платформы .NET Framework. В этих сценариях, присвойте атрибуту значение `true`.  
  
> [!NOTE]
>  Присвоение атрибуту `true` запрещает загрузку в один процесс, эффективно отключив функцию-process side-by-side CLR версии 1.1 или среда CLR версии 2.0 (в разделе [Side-by-Side выполнение COM-взаимодействия](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров запуска](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Указание используемой версии среды выполнения](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [Выполнение Side-by-Side COM-взаимодействия](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [Внутрипроцессное параллельное выполнение](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
