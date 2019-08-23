---
title: <clear>Элемент для <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 9816ba0f8e4ddd4c38537eb4e014a4240ff20407
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927172"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<Очистка элемента > для \<прослушивателей, \<> для трассировки >
Очищает коллекцию `Listeners` для трассировки.  
  
 \<configuration>  
\<> System. Diagnostics  
\<> трассировки  
\<прослушиватели >  
\<очистить >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
  
## <a name="remarks"></a>Примечания  
 Элемент удаляет все прослушиватели `Listeners` из коллекции для трассировки. `<clear>` `<clear>` Элемент можно использовать перед `<add>` использованием элемента, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.  
  
 Можно очистить `Listeners` коллекцию программным путем, <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> вызвав метод для <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> свойства (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
> [!NOTE]
> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Элемент удаляет из коллекции`Listeners`, изменяя поведение методов ,,и.<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.DefaultTraceListener> `<clear>` Вызов метода `Fail` или обычно приводит к отображению окна сообщения. `Assert` Однако окно сообщения не отображается, если объект <xref:System.Diagnostics.DefaultTraceListener> отсутствует `Listeners` в коллекции.  
  
## <a name="example"></a>Пример  
 В следующем примере показано `<clear>` , как использовать элемент перед `<add>` использованием элемента для `Listeners` добавления прослушивателя `console` в коллекцию для трассировки.  
  
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
