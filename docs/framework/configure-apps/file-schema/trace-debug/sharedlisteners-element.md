---
title: '&lt;sharedListeners&gt; элемент'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3069022287d469704cc7adac40d02ef3c6997b56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563057"
---
# <a name="ltsharedlistenersgt-element"></a>&lt;sharedListeners&gt; элемент
Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.  Эти прослушиватели не получают все трассировки по умолчанию, и невозможно извлечь эти прослушиватели во время выполнения. Прослушиватели, определенные как общие могут добавляться к источникам и трассировки по имени.  
  
 \<configuration>  
\<system.diagnostics>  
\<sharedListeners >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `sharedListeners`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`Configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
  
## <a name="remarks"></a>Примечания  
 Добавление прослушивателя к общей коллекции прослушивателей не делает его активным. Оно по-прежнему добавлено к источнику трассировки или трассировки путем добавления его в `Listeners` коллекции для этого элемента трассировки. Классы прослушивателя в .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.  
  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<sharedListeners>` элемент, чтобы добавить прослушиватель `console` для `Listeners` коллекции для обоих <xref:System.Diagnostics.TraceSource> и <xref:System.Diagnostics.Trace> классы. Прослушиватель трассировки консоли записывает сведения трассировки на консоль, через вызовы к либо <xref:System.Diagnostics.TraceSource> или <xref:System.Diagnostics.Trace>.  
  
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
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Diagnostics.TraceListener>
- [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Прослушиватели трассировки](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
