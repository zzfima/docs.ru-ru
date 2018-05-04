---
title: '&lt;Очистить&gt; элемент для &lt;прослушиватели&gt; для &lt;трассировки&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1705ed7cc847d60ecf8b42f4615d77f2cc569e21
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;Очистить&gt; элемент для &lt;прослушиватели&gt; для &lt;трассировки&gt;
Очищает коллекцию `Listeners` для трассировки.  
  
 \<configuration>  
\<System.Diagnostics >  
\<трассировки >  
\<прослушиватели >  
\<Очистить >  
  
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
|`listeners`|Содержит прослушиватели для сбора, хранения и маршрутизации сообщений. Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.|  
  
## <a name="remarks"></a>Примечания  
 `<clear>` Элемент удаляет все прослушиватели `Listeners` коллекции для трассировки. Можно использовать `<clear>` элемент перед использованием `<add>` элемент, чтобы быть уверенным, отсутствуют другие активные прослушиватели в коллекции.  
  
 Можно снять `Listeners` коллекции программным образом путем вызова <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> метод <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> свойство (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.  
  
> [!NOTE]
>  `<clear>` Элемент удаляет <xref:System.Diagnostics.DefaultTraceListener> из `Listeners` коллекции, меняет поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> методы. Вызов `Assert` или `Fail` метод обычно приводит к отображению окна сообщения. Однако окно сообщения не отображается при <xref:System.Diagnostics.DefaultTraceListener> не находится в `Listeners` коллекции.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<clear>` элемент перед использованием `<add>` элемент для добавления прослушивателя `console` для `Listeners` коллекции для трассировки.  
  
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
 <xref:System.Diagnostics.Trace.Listeners%2A>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.TraceSource>  
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)  
 [Прослушиватели трассировки](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
