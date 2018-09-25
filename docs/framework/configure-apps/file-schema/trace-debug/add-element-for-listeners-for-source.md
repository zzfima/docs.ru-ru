---
title: '&lt;Добавить&gt; элемент для &lt;прослушиватели&gt; для &lt;источника&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: c0ab15f6eca8b20653530583016eb849273c4ce1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47072034"
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-ltsourcegt"></a>&lt;Добавить&gt; элемент для &lt;прослушиватели&gt; для &lt;источника&gt;
Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.  
  
 \<configuration>  
\<System.Diagnostics >  
\<источники >  
\<Источник >  
\<прослушиватели >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`type`|Необходимый атрибут, в том случае, если не обращаются к прослушивателю в `sharedListeners` коллекции, в котором случае необходима только для ссылки на него по имени (см. в разделе [пример](#example)).<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, перечисленным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса. Объект <xref:System.Configuration.ConfigurationException> создается, если класс имеет конструктор, принимающий строку.|  
|`name`|Необязательный атрибут.<br /><br /> Имя прослушивателя.|  
|`traceOutputOptions`|Необязательный атрибут.<br /><br /> Указывает <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> значение свойства для прослушивателя трассировки.|  
|[настраиваемые атрибуты]|Необязательные атрибуты.<br /><br /> Указывает значение для прослушивателя атрибутов, идентифицируемых <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> метод для этого прослушивателя. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> является примером дополнительный атрибут, уникальные для <xref:System.Diagnostics.DelimitedListTraceListener> класса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
|`listeners`|Задает прослушиватели для сбора, хранения и маршрутизации сообщений.|  
  
## <a name="remarks"></a>Примечания  
 Классы прослушивателя, поставлявшихся с .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.  
  
 Если вы не укажете `name` атрибут прослушивателя трассировки, <xref:System.Diagnostics.TraceListener.Name%2A> свойства прослушивателя трассировки по умолчанию используется пустая строка (»»). Если у приложения имеется только один прослушиватель, его можно добавить без указания имени и его можно удалить, указав пустую строку для имени. Тем не менее, если приложение имеет несколько прослушивателей, следует указать уникальное имя для каждого прослушивателя трассировки, для идентификации и управления ими в прослушиватели трассировки в отдельных <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> коллекции.  
  
> [!NOTE]
>  Добавление более одного прослушивателя трассировки, того же типа и с тем же присвойте приводит только одного прослушивателя этого типа имя, а, добавляемый `Listeners` коллекции. Тем не менее, можно программно добавить несколько идентичных прослушивателей для `Listeners` коллекции.  
  
 Значение для `initializeData` атрибута зависит от типа создании прослушивателя. Не все прослушиватели трассировки необходимо указать `initializeData`.  
  
> [!NOTE]
>  При использовании `initializeData` атрибут, может появиться предупреждение «атрибут «initializeData» не объявлен.» компилятора Это предупреждение возникает, так как параметры конфигурации проверяются на соответствие абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута. Как правило можно игнорировать это предупреждение для реализации прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описаны значения их `initializeData` атрибуты.  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream` Значение <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.  Задайте `initializeData` для атрибута "`true`«для записи выходных данных трассировки и отладки в стандартный поток ошибок; ему присвоено»`false`" для записи в стандартный выходной поток.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<add>` элементы для добавления прослушивателей `console` и `textListener` для `Listeners` коллекции для источника трассировки `TraceSourceApp`. `textListener` Прослушиватель записывает выходные данные трассировки в файл myListener.log.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Прослушиватели трассировки](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
