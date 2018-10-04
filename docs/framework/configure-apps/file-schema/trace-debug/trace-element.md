---
title: '&lt;трассировки&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 55a7eb431432b67b3252853d14bf93be304ee883
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780821"
---
# <a name="lttracegt-element"></a>&lt;трассировки&gt; элемент
Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.  
  
 \<configuration>  
\<System.Diagnostics >  
\<трассировки >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`autoflush`|Необязательный атрибут.<br /><br /> Указывает ли прослушиватели трассировки автоматически очистку буфера после каждой операции записи.|  
|`indentsize`|Необязательный атрибут.<br /><br /> Задает количество пробелов для отступа.|  
|`useGlobalLock`|Необязательный атрибут.<br /><br /> Указывает, следует ли использовать глобальную блокировку.|  
  
## <a name="autoflush-attribute"></a>AutoFlush атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не очищает автоматически выходного буфера. Это значение по умолчанию.|  
|`true`|Автоматически очищает выходной буфер.|  
  
## <a name="usegloballock-attribute"></a>useGlobalLock атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не использовать глобальную блокировку, если прослушиватель является потокобезопасным; в противном случае использует глобальную блокировку.|  
|`true`|Использует глобальную блокировку, независимо от того, является ли прослушиватель потокобезопасным. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Указывает прослушиватель, который собирает, хранилищ и направляет сообщения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<trace>` элемент, чтобы добавить прослушиватель `MyListener` для `Listeners` коллекции. `MyListener` Создает файл с именем `MyListener.log` и записывает выходные данные в файл. `useGlobalLock` Атрибут имеет значение `false`, что вызывает глобальной блокировки не должна использоваться, если прослушиватель трассировки потокобезопасен. `autoflush` Атрибуту присваивается `true`, чего прослушиватель трассировки для записи в файл, независимо от того, следует ли <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> вызывается метод. `indentsize` Атрибут имеет значение 0 (ноль), что приводит к прослушивателю в отступ при <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> вызывается метод.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
