---
title: <filter>Элемент <add> для <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153470"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>\<фильтр> \<элемент для \<добавления> для слушателей> для \<> трассировки
Добавляет фильтр слушателю в `Listeners` коллекцию для отслеживания.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<след>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<фильтр>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`type`|Обязательный атрибут.<br /><br /> Определяет тип фильтра, который должен наследовать <xref:System.Diagnostics.TraceFilter> сяокласс. Вы можете использовать имя, квалифицированное для имени типа, которое соответствует <xref:System.Type.FullName%2A> свойству типа, или вы можете использовать полностью <xref:System.Type.AssemblyQualifiedName%2A> квалифицированное имя типа, включая информацию о сборке, которая соответствует свойству. Для получения информации о полностью квалифицированных именах типов [см.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка перешла к конструктору для указанного класса фильтра.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
|`listeners`|Содержит слушателей, которые собирают, хранят и направляют сообщения. Слушатели направляют результаты отслеживания на соответствующую цель.|  
|`add`|Добавляет прослушиватель в коллекцию `Listeners`.|  
  
## <a name="remarks"></a>Remarks  
 Элемент `<filter>` должен содержаться `<add>` в элементе для слушателя трассировки, который определяет тип слушателя, а не только имя слушателя, определенного в [ \<общей>. ](sharedlisteners-element.md) Если слушатель определен в [ \<общей>Слушателя, ](sharedlisteners-element.md)фильтр для этого слушателя должен быть определен в этом элементе.  
  
 Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как `<filter>` использовать элемент для `console` добавления фильтра для отслеживания фильтра в `Listeners` коллекции, указывая уровень события фильтра как. `Error`  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Схема настроек трассировки и отпараги](index.md)
