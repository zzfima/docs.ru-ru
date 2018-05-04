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
manager: markl
ms.openlocfilehash: ba8ff652003a9167ec370643797ac9300b83889a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
|`type`|Требуется атрибут, в том случае, если не обращаются прослушивателя в `sharedListeners` коллекции, в котором регистр необходима только для ссылки на него по имени (в разделе [пример](#example)).<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, отвечающую требованиям, указанным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса. Объект <xref:System.Configuration.ConfigurationException> создается, если класс имеет конструктор, принимающий строку.|  
|`name`|Необязательный атрибут.<br /><br /> Указывает имя прослушивателя.|  
|`traceOutputOptions`|Необязательный атрибут.<br /><br /> Указывает <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> значение свойства для прослушивателя трассировки.|  
|[настраиваемые атрибуты]|Необязательные атрибуты.<br /><br /> Указывает значение для прослушивателя атрибуты, определяемые <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> метода для этого прослушивателя. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> Примером дополнительный атрибут является уникальным для <xref:System.Diagnostics.DelimitedListTraceListener> класса.|  
  
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
 Классы слушателя поставляются с платформой .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.  
  
 Если вы не укажете `name` атрибут прослушивателя трассировки <xref:System.Diagnostics.TraceListener.Name%2A> свойства прослушивателя трассировки по умолчанию является пустая строка (»»). Если приложение имеет только один прослушиватель, его можно добавить без указания имени и его можно удалить, указав для имени пустую строку. Тем не менее, если приложение имеет более одного прослушивателя, следует задать уникальное имя для каждого прослушивателя трассировки, который позволяет идентифицировать и управлять отдельные прослушиватели трассировки в <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> коллекции.  
  
> [!NOTE]
>  Добавлении более одного прослушивателя трассировки того же типа и с тем же именем приведет лишь один прослушиватель этого типа и имя, добавляемый `Listeners` коллекции. Однако можно программно добавить несколько идентичных прослушивателей для `Listeners` коллекции.  
  
 Значение для `initializeData` атрибута зависит от типа создании прослушивателя. Не все прослушиватели трассировки требуют указывать `initializeData`.  
  
> [!NOTE]
>  При использовании `initializeData` атрибут, можно получить компилятор предупреждение «атрибута «initializeData» не объявлен.» Это предупреждение возникает, поскольку параметры конфигурации проверяются абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута. Как правило можно игнорировать это предупреждение для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описываются значения их `initializeData` атрибуты.  
  
|Класс прослушивателей трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream` Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.  Задать `initializeData` для атрибута "`true`«для записи выходных данных трассировки и отладки в стандартный поток ошибок; присвоить»`false`» на запись в стандартный выходной поток.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.  
  
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
