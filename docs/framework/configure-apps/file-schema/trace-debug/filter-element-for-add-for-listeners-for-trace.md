---
title: Элемент <filter> для <add> для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: f6b1ec99c5aab8e85df7f1920aca32f49a5be066
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699362"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>Элемент \<filter > для > \<Add для \<listeners > @no__t 3trace
Добавляет фильтр в прослушиватель в коллекции `Listeners` для трассировки.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0add >** ](add-element-for-listeners-for-trace.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1filter >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`type`|Обязательный атрибут.<br /><br /> Указывает тип фильтра, который должен наследовать от класса <xref:System.Diagnostics.TraceFilter>. Можно использовать имя, уточненное пространством имен типа, которое соответствует свойству <xref:System.Type.FullName%2A> типа, или можно использовать полное имя типа, включая сведения о сборке, соответствующие свойству <xref:System.Type.AssemblyQualifiedName%2A>. Дополнительные сведения о полных именах типов см. в разделе Указание полных [имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса фильтра.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
|`add`|Добавляет прослушиватель в коллекцию `Listeners`.|  
  
## <a name="remarks"></a>Примечания  
 Элемент `<filter>` должен содержаться в элементе `<add>` для прослушивателя трассировки, который указывает тип прослушивателя, а не только имя прослушивателя, определенного в [@no__t 3sharedListeners >](sharedlisteners-element.md). Если прослушиватель определен в [@no__t >](sharedlisteners-element.md), то фильтр для этого прослушивателя должен быть определен в этом элементе.  
  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как с помощью элемента `<filter>` Добавить фильтр в прослушиватель `console` в коллекции `Listeners` для трассировки, указав уровень событий фильтра `Error`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Схема параметров трассировки и отладки](index.md)
