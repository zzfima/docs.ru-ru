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
ms.openlocfilehash: fd90d271591a47849b3f70aea50cbe909b6fd613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920399"
---
# <a name="trace-element"></a>\<Элемент > трассировки
Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.  
  
 \<configuration>  
\<> System. Diagnostics  
\<> трассировки  
  
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
|`autoflush`|Необязательный атрибут.<br /><br /> Указывает, будут ли прослушиватели трассировки автоматически сбрасывать выходной буфер после каждой операции записи.|  
|`indentsize`|Необязательный атрибут.<br /><br /> Задает количество пробелов для отступа.|  
|`useGlobalLock`|Необязательный атрибут.<br /><br /> Указывает, следует ли использовать глобальную блокировку.|  
  
## <a name="autoflush-attribute"></a>Атрибут автозаписи  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не очищает выходной буфер автоматически. Это значение по умолчанию.|  
|`true`|Автоматически очищает выходной буфер.|  
  
## <a name="usegloballock-attribute"></a>Атрибут useGlobalLock  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не использует глобальную блокировку, если прослушиватель является потокобезопасным; в противном случае использует глобальную блокировку.|  
|`true`|Использует глобальную блокировку независимо от того, является ли прослушиватель потокобезопасным. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<trace>` элемент для добавления прослушивателя `MyListener` в `Listeners` коллекцию. `MyListener`создает файл с именем `MyListener.log` и записывает выходные данные в файл. `useGlobalLock` Атрибут имеет`false`значение, что приводит к тому, что глобальная блокировка не будет использоваться, если прослушиватель трассировки является потокобезопасным. Атрибут имеет значение, что приводит к тому, что прослушиватель трассировки выполняет запись в файл <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> независимо от того, вызывается ли метод. `true` `autoflush` Атрибуту присваивается значение 0 (ноль), что приводит к тому, что <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> при вызове метода прослушиватель устанавливает отступы в ноль пробелов. `indentsize`  
  
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

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Схема параметров трассировки и отладки](index.md)
