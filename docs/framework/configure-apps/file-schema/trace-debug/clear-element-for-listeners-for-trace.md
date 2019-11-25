---
title: Элемент <clear> для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 049b8e7ed17633c0f34b062915afaf719927dad6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088914"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<очистить элемент > для прослушивателей \<> для \<трассировки >
Очищает коллекцию `Listeners` для трассировки.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trace**](trace-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**прослушиватели**](listeners-element-for-trace.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
  
## <a name="remarks"></a>Заметки  
 Элемент `<clear>` удаляет все прослушиватели из коллекции `Listeners` для трассировки. Элемент `<clear>` можно использовать перед использованием элемента `<add>`, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.  
  
 Можно очистить коллекцию `Listeners` программным способом, вызвав метод <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> в свойстве <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
> [!NOTE]
> Элемент `<clear>` удаляет <xref:System.Diagnostics.DefaultTraceListener> из коллекции `Listeners`, изменяя поведение методов <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>. Вызов метода `Assert` или `Fail` обычно приводит к отображению окна сообщения. Однако окно сообщения не отображается, если <xref:System.Diagnostics.DefaultTraceListener> не находится в коллекции `Listeners`.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать элемент `<clear>` перед использованием элемента `<add>`, чтобы добавить `console` прослушивателя в коллекцию `Listeners` для трассировки.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Схема параметров трассировки и отладки](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
