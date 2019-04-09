---
title: <add> Элемент для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: ba0ffc4f95b9af7fcd319068501ce0bb9714c2ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089586"
---
# <a name="add-element-for-listeners-for-trace"></a>\<Добавить > элемент для \<прослушиватели > для \<трассировки >
Добавляет прослушиватель **прослушиватели** коллекции.  
  
 \<configuration>  
\<system.diagnostics>  
\<трассировки >  
\<прослушиватели >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**type**|Обязательный атрибут.<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, перечисленным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса.|  
|**имя**|Необязательный атрибут.<br /><br /> Имя прослушивателя.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Фильтр >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Добавляет фильтр к прослушивателю в `Listeners` коллекции трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`listeners`|Указывает прослушиватель, который собирает, хранилищ и направляет сообщения. Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
## <a name="remarks"></a>Примечания  
 <xref:System.Diagnostics.Debug> И <xref:System.Diagnostics.Trace> классы одного и того же **прослушиватели** коллекции. Если добавить объект прослушивателя в коллекцию в одном из этих классов, другой класс использует этот же прослушиватель. Прослушиватель классы являются производными от <xref:System.Diagnostics.TraceListener>.  
  
 Если вы не укажете `name` атрибут прослушивателя трассировки, <xref:System.Diagnostics.TraceListener.Name%2A> трассировки прослушивателя, по умолчанию используется пустая строка (»»). Если у приложения имеется только один прослушиватель, можно добавить его без указания имени и удалите его, указать пустую строку для имени. Тем не менее, если у приложения есть несколько прослушивателей, необходимо указать уникальные имена для каждого прослушивателя трассировки, для идентификации и управления ими отдельные прослушиватели трассировки в <xref:System.Diagnostics.Debug.Listeners%2A> и <xref:System.Diagnostics.Trace.Listeners%2A> коллекций.  
  
> [!NOTE]
>  Добавление более одного прослушивателя трассировки, того же типа и с тем же присвойте приводит только одного прослушивателя этого типа имя, а, добавляемый `Listeners` коллекции. Тем не менее, можно программно добавить несколько идентичных прослушивателей для `Listeners` коллекции.  
  
 Значение для **initializeData** атрибута зависит от типа создании прослушивателя. Не все прослушиватели трассировки необходимо указать **initializeData**.  
  
> [!NOTE]
>  При использовании `initializeData` атрибут, может появиться предупреждение «атрибут «initializeData» не объявлен.» компилятора Это предупреждение возникает, так как параметры конфигурации проверяются на соответствие абстрактный базовый класс <xref:System.Diagnostics.TraceListener>, который не распознает `initializeData` атрибута. Как правило можно игнорировать это предупреждение для реализации прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице перечислены прослушиватели трассировки, которые входят в состав .NET Framework и описаны значения их **initializeData** атрибуты.  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream` Значение <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктор.  Задайте `initializeData` для атрибута "`true`" для записи трассировки и отладки вывода <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" для записи <xref:System.Console.Out%2A?displayProperty=nameWithType>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла <xref:System.Diagnostics.DelimitedListTraceListener> записывает.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> записывает.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> записывает.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> записывает.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать  **\<Добавить >** элементы для добавления прослушивателей `MyListener` и `MyEventListener` для **прослушиватели** коллекции. `MyListener` Создает файл с именем `MyListener.log` и записывает выходные данные в файл. `MyEventListener` создает запись в журнале событий.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Прослушиватели трассировки](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
