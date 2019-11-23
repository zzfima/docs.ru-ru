---
title: < System. Diagnostics > элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: dc05c46cb1ba74baceaaeadc2959a6889faf19c9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699197"
---
# <a name="systemdiagnostics-element"></a>\<System. Diagnostics > элемент
Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<System. diagnostics >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.|  
|[\<performanceCounters>](performancecounters-element.md)|Задает размер глобальной памяти, совместно используемой счетчиками производительности.|  
|[\<sharedListeners>](sharedlisteners-element.md)|Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки. Прослушиватели, идентифицированные как общие прослушиватели, можно добавлять в источники или трассировки по имени.|  
|[\<sources>](sources-element.md)|Указывает источники трассировки, инициирующие сообщения трассировки.|  
|[\<switches>](switches-element.md)|Содержит переключатели трассировки и уровни, на которых заданы переключатели трассировки.|  
|[\<trace>](trace-element.md)|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как внедрить переключатель трассировки и прослушиватель трассировки в элемент **\<System. diagnostics >** . Для параметра трассировки `General` задан уровень <xref:System.Diagnostics.TraceLevel>. Прослушиватель трассировки `myListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл.  
  
> [!NOTE]
> В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст. Например, можно указать `true` для <xref:System.Diagnostics.BooleanSwitch> или использовать текст, представляющий значение перечисления, например `Error` для <xref:System.Diagnostics.TraceSwitch>. Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [Схема параметров трассировки и отладки](index.md)
