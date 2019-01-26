---
title: '&lt;Фильтр&gt; элемент для &lt;добавить&gt; для &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: a811d2ae8112bb1ab9386510fc8435d00f454f85
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083799"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a>&lt;Фильтр&gt; элемент для &lt;добавить&gt; для &lt;sharedListeners&gt;
Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.  
  
 \<configuration>  
\<system.diagnostics>  
\<sharedListeners > элемент  
\<add>  
\<Фильтр >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|**type**|Обязательный атрибут.<br /><br /> Указывает тип фильтра. Можно использовать только полное имя типа (в формате <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойство), или можно использовать имя полное имя типа, включая сведения о сборке (в формате <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> свойство). Сведения о создании полное имя типа, см. в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sharedListeners`|Коллекция прослушивателей, которые может ссылаться любой источник или элемент трассировки.|  
|`add`|Добавляет прослушиватель **sharedListeners** коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Если прослушиватель определен в `<add>` элемент `<sharedListeners>` элемент, фильтр для этого прослушивателя, должен быть определен в `<filter>` элемент, который является дочерним объектом `<add>` элемент.  
  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<filter>` элемент, чтобы добавить фильтр к прослушивателю трассировки `console` в `sharedListeners` коллекции.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
