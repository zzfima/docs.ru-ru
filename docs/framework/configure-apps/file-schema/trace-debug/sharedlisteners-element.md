---
title: Элемент <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153325"
---
# <a name="sharedlisteners-element"></a>\<общиеслушатели> Элемент
Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.  Эти слушатели не получают никаких следов по умолчанию, и невозможно получить эти слушатели во время выполнения. Слушатели, идентифицированные как общие слушатели, могут быть добавлены к источникам или следам по имени.  
  
[**\<конфигурация>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<общиеслушатели>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<добавить>](add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `sharedListeners`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`Configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
  
## <a name="remarks"></a>Remarks  
 Добавление слушателя в общую коллекцию слушателей не делает его активным слушателем. Он должен быть добавлен в источник трассировки или `Listeners` след, добавив его в коллекцию для этого элемента. Классы слушателя в рамках .NET <xref:System.Diagnostics.TraceListener> вытекают из класса.  
  
 Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как `<sharedListeners>` использовать `console` элемент `Listeners` для добавления слушателя в коллекцию как для классов, <xref:System.Diagnostics.TraceSource> так и <xref:System.Diagnostics.Trace> для классов. Консольный след слушатель записывает информацию <xref:System.Diagnostics.TraceSource> о <xref:System.Diagnostics.Trace>следах на консоль через звонки либо или .  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.TraceListener>
- [Схема настроек трассировки и отпараги](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
