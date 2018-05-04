---
title: '&lt;источники&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 73fe0fb13c191843516a2218c708851abc1851b0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltsourcesgt-element"></a>&lt;источники&gt; элемент
Задает источники трассировки, инициирующие сообщения трассировки.  
  
 \<configuration>  
\<System.Diagnostics >  
\<источники >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|Обязательный элемент.<br /><br /> Содержит источник трассировки, который инициирует сообщения трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<sources>` элемента для добавления источника трассировки `mySource` и задать уровень для переключателя источника с именем `sourceSwitch`. Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"   
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"   
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>    
   </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
