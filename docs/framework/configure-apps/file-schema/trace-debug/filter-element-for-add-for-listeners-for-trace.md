---
title: Элемент <filter> для <add> <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: cc970240ac07ad3ea72be50d1e9af452da638fa9
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088891"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>\<> элемент фильтра для \<Добавить > для \<трассировки >
Добавляет фильтр к прослушивателю в коллекции `Listeners` для трассировки.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trace**](trace-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**прослушиватели**](listeners-element-for-trace.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<добавить >** ](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filter >**

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
|`type`|Обязательный атрибут.<br /><br /> Указывает тип фильтра, который должен наследовать от класса <xref:System.Diagnostics.TraceFilter>. Можно использовать имя типа, уточненное пространством имен, которое соответствует свойству <xref:System.Type.FullName%2A> типа, или можно использовать полное имя типа, включая сведения о сборке, соответствующие свойству <xref:System.Type.AssemblyQualifiedName%2A>. Дополнительные сведения о полных именах типов см. в разделе Указание полных [имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса фильтра.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
|`add`|Добавляет прослушиватель в коллекцию `Listeners`.|  
  
## <a name="remarks"></a>Заметки  
 Элемент `<filter>` должен содержаться в элементе `<add>` для прослушивателя трассировки, который указывает тип прослушивателя, а не только имя прослушивателя, определенного в [\<шаредлистенерс >](sharedlisteners-element.md). Если прослушиватель определен в [\<е > шаредлистенерс](sharedlisteners-element.md), то фильтр для этого прослушивателя должен быть определен в этом элементе.  
  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать элемент `<filter>`, чтобы добавить фильтр в `console` прослушивателя в коллекции `Listeners` для трассировки, указав уровень событий фильтра `Error`.  
  
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
