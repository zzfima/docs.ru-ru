---
title: '&lt;System.Diagnostics&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: c4a10f8973a78a80067ab6eb23fafd3540a68abe
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083409"
---
# <a name="ltsystemdiagnosticsgt-element"></a>&lt;System.Diagnostics&gt; элемент
Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.  
  
 \<configuration>  
\<system.diagnostics>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<assert>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.|  
|[\<performanceCounters>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Задает размер глобальной памяти, совместно используемой счетчиками производительности.|  
|[\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки. Прослушиватели, определенные как общие могут добавляться к источникам и трассировки по имени.|  
|[\<sources>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Задает источники трассировки, которые инициируют сообщения трассировки.|  
|[\<switches>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Содержит переключатели трассировки и уровни, где они установлены.|  
|[\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как внедрение переключателя трассировки и прослушивателя трассировки в  **\<system.diagnostics >** элемент. `General` Установлен переключатель трассировки <xref:System.Diagnostics.TraceLevel> уровень. Прослушиватель трассировки `myListener` создается файл с именем `MyListener.log` и записывает выходные данные в файл.  
  
> [!NOTE]
>  В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст. Например, можно указать `true` для <xref:System.Diagnostics.BooleanSwitch> или текст, представляющий значение перечисления, таких как `Error` для <xref:System.Diagnostics.TraceSwitch>. Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
