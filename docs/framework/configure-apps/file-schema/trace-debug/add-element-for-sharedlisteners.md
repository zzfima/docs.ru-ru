---
title: Элемент <add> для <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 116a9633d16b8dd36c82f07a8e727f6f9f98f0ee
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088969"
---
# <a name="add-element-for-sharedlisteners"></a>\<добавить элемент > для \<Шаредлистенерс >
Добавляет прослушиватель в коллекцию `sharedListeners`. `sharedListeners` — это коллекция прослушивателей, на которые могут ссылаться любые [\<источника >](source-element.md) или [\<трассировки >](trace-element.md) .  По умолчанию прослушиватели в коллекции `sharedListeners` не помещаются в коллекцию `Listeners`. Их необходимо добавить по имени в [источник\<](source-element.md) или [\<> трассировки](trace-element.md). Невозможно получить прослушиватели в коллекции `sharedListeners` в коде во время выполнения.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<шаредлистенерс >** ](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Указывает имя прослушивателя, который используется для добавления общего прослушивателя в коллекцию `Listeners`.|  
|`type`|Обязательный атрибут.<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса.|  
|`traceOutputOptions`|Необязательный атрибут.<br/><br/>Строковое представление одного или нескольких элементов перечисления <xref:System.Diagnostics.TraceOptions>, указывающих данные, записываемые в выходные данные трассировки. Несколько элементов разделяются запятыми. Значение по умолчанию — None.|

### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sharedListeners`|Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.|  
  
## <a name="remarks"></a>Заметки  
 Классы прослушивателей, поставляемые с .NET Framework, являются производными от класса <xref:System.Diagnostics.TraceListener>. Значение атрибута `name` используется для добавления общего прослушивателя в коллекцию `Listeners` для трассировки или для источника трассировки. Значение атрибута `initializeData` зависит от типа создаваемого прослушивателя. Не все прослушиватели трассировки должны указывать `initializeData`.  
  
> [!NOTE]
> При использовании атрибута `initializeData` может появиться предупреждение компилятора "атрибут initializeData не объявлен". Это предупреждение возникает из-за того, что параметры конфигурации проверяются на основе абстрактного базового класса <xref:System.Diagnostics.TraceListener>, который не распознает атрибут `initializeData`. Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице показаны прослушиватели трассировки, которые включены в .NET Framework и описаны значения их `initializeData`ных атрибутов.  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Значение `useErrorStream` для конструктора <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Присвойте атрибуту `initializeData` значение "`true`", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок. Задайте для него значение "`false`", чтобы выполнить запись в стандартный выходной поток.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Имя файла, в который <xref:System.Diagnostics.DelimitedListTraceListener> записывается.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, в который записывается <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который записывается <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Имя файла, в который записывается <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать элементы `<add>`, чтобы добавить <xref:System.Diagnostics.TextWriterTraceListener>`textListener` в коллекцию `sharedListeners`.   `textListener` добавляется по имени в коллекцию `Listeners` для источника трассировки `TraceSourceApp`. Прослушиватель `textListener` записывает выходные данные трассировки в файл myListener. log.  
  
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

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Схема параметров трассировки и отладки](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
