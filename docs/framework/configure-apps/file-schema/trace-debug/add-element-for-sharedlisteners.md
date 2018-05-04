---
title: '&lt;Добавить&gt; элемент для &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 27d83ba706b4d93b4ac5426bf5bae59b4bfc0d9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a>&lt;Добавить&gt; элемент для &lt;sharedListeners&gt;
Добавляет прослушиватель в коллекцию `sharedListeners`. `sharedListeners` — Это коллекция прослушивателей, чтобы любое [ \<источника >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [ \<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) может ссылаться.  По умолчанию в прослушиватели `sharedListeners` коллекции не помещаются в `Listeners` коллекции. Они должны быть добавлены по имени, чтобы [ \<источника >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) или [ \<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md). Невозможно получить прослушиватели `sharedListeners` коллекции в коде во время выполнения.  
  
 \<configuration>  
\<System.Diagnostics >  
\<sharedListeners > элемент  
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
|`name`|Обязательный атрибут.<br /><br /> Указывает имя прослушивателя, который используется для добавления общего прослушивателя для `Listeners` коллекции.|  
|`type`|Обязательный атрибут.<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, отвечающую требованиям, указанным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sharedListeners`|Коллекция прослушивателей, которые могут ссылаться на любой источник или элемент трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Классы слушателя поставляются с платформой .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса. Значение для `name` атрибут используется для добавления общего прослушивателя для `Listeners` сбор данных для трассировки или источник трассировки. Значение для `initializeData` атрибута зависит от типа создании прослушивателя. Не все прослушиватели трассировки требуют указывать `initializeData`.  
  
> [!NOTE]
>  При использовании `initializeData` атрибут, можно получить компилятор предупреждение «атрибута «initializeData» не объявлен.» Это предупреждение возникает, поскольку параметры конфигурации проверяются абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута. Как правило можно игнорировать это предупреждение для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описываются значения их `initializeData` атрибуты.  
  
|Класс прослушивателей трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|`useErrorStream` Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.  Задать `initializeData` для атрибута "`true`«для записи выходных данных трассировки и отладки в стандартный поток ошибок; присвоить»`false`» на запись в стандартный выходной поток.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<add>` элементы для добавления <xref:System.Diagnostics.TextWriterTraceListener> `textListener` для `sharedListeners` коллекции.   `textListener` добавляется по имени, чтобы `Listeners` коллекции для источника трассировки `TraceSourceApp`. `textListener` Прослушиватель записывает выходные данные трассировки в файл myListener.log.  
  
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
