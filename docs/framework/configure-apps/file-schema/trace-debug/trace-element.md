---
title: Элемент <trace>
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
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153170"
---
# <a name="trace-element"></a>\<след> Элемент
Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.  
  
[**\<конфигурация>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<след>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`autoflush`|Необязательный атрибут.<br /><br /> Определяет, автоматически ли слушатели трассировки промывают буфер вывода после каждой операции записи.|  
|`indentsize`|Необязательный атрибут.<br /><br /> Определяет количество пробелов для отступа.|  
|`useGlobalLock`|Необязательный атрибут.<br /><br /> Указывает, следует ли использовать глобальную блокировку.|  
  
## <a name="autoflush-attribute"></a>autoflush Атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не автоматически сбрасывает буфер вывода. Это значение по умолчанию.|  
|`true`|Автоматически сбрасывает буфер вывода.|  
  
## <a name="usegloballock-attribute"></a>useGlobalLock Атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не использует глобальную блокировку, если слушатель является безопасным потоком; в противном случае использует глобальную блокировку.|  
|`true`|Использует глобальную блокировку независимо от того, является ли слушатель безопасным потоком. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<слушатели>](listeners-element-for-trace.md)|Определяет слушателя, который собирает, хранит и направляет сообщения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<trace>` `MyListener` элемент `Listeners` для добавления слушателя в коллекцию. `MyListener`создает файл, который `MyListener.log` называется, и записывает вывод в файл. Атрибут `useGlobalLock` установлен на, `false`что приводит к глобальной блокировки не будет использоваться, если слушатель трассировки поток безопасно. Атрибут `autoflush` установлен на, `true`который вызывает слушателя следа, чтобы написать в файл, независимо от того, <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> метод называется. Атрибут `indentsize` установлен до 0 (ноль), что приводит к тому, <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> что при вызове метода слушателю будут установлены нулевые пробелы.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Схема настроек трассировки и отпараги](index.md)
