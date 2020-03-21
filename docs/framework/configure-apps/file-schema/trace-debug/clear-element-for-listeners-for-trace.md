---
title: <clear>Элемент <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153546"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<ясно> \<Элемент для \<слушателей> для следа>
Очищает коллекцию `Listeners` для трассировки.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<след>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ясно>**

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
|`listeners`|Содержит слушателей, которые собирают, хранят и направляют сообщения. Слушатели направляют результаты отслеживания на соответствующую цель.|  
  
## <a name="remarks"></a>Remarks  
 Элемент `<clear>` удаляет всех слушателей `Listeners` из коллекции для отслеживания. Вы можете `<clear>` использовать элемент, `<add>` прежде чем использовать элемент, чтобы быть уверенным, что в коллекции нет других активных слушателей.  
  
 Вы можете `Listeners` очистить коллекцию программно, <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> позвонив метод на <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> имущество (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.  
  
> [!NOTE]
> Элемент `<clear>` <xref:System.Diagnostics.DefaultTraceListener> удаляет `Listeners` из коллекции, изменяя поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> методы. Вызов `Assert` или `Fail` метод обычно приводит к отображению ящика сообщений. Однако окно сообщений не отображается, <xref:System.Diagnostics.DefaultTraceListener> если `Listeners` его нет в коллекции.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, `<clear>` как `<add>` использовать элемент перед `console` использованием `Listeners` элемента для добавления слушателя в коллекцию для отслеживания.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Схема настроек трассировки и отпараги](index.md)
- [\<удалить>](remove-element-for-listeners-for-trace.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
