---
title: '&lt;прослушиватели&gt; элемент для &lt;источника&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 86b85779f4eff72e8ab910a5ccd32fd369270509
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085688"
---
# <a name="ltlistenersgt-element-for-ltsourcegt"></a>&lt;прослушиватели&gt; элемент для &lt;источника&gt;
Добавляет или удаляет прослушиватели в <xref:System.Diagnostics.TraceSource.Listeners%2A> коллекции для <xref:System.Diagnostics.TraceSource>. Прослушиватель направляет данные трассировки соответствующему целевому объекту, например журнал, окно или текстовый файл.  
  
 \<configuration>  
\<System.Diagnostics >  
\<источники >  
\<Источник >  
\<прослушиватели > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|Добавляет прослушиватель в коллекцию `Listeners`.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|Удаляет прослушиватель из `Listeners` коллекции.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|Очищает коллекцию `Listeners` для источника трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<listeners>` элемент, чтобы добавить прослушиватель трассировки консоли `mySource` источника и удалить прослушиватель трассировки по умолчанию.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.TraceListener>  
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Прослушиватели трассировки](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
