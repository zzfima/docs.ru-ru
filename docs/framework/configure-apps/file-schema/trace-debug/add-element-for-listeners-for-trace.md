---
title: <add>Элемент для <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: d4ff919991ab1505b2845a225706d32cc1e57d0a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920573"
---
# <a name="add-element-for-listeners-for-trace"></a>\<Добавление элемента > для \<прослушивателей, \<> для трассировки >
Добавляет прослушиватель в коллекцию **Listeners** .  
  
 \<configuration>  
\<> System. Diagnostics  
\<> трассировки  
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
|**type**|Обязательный атрибут.<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса.|  
|**name**|Необязательный атрибут.<br /><br /> Указывает имя прослушивателя.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Добавляет фильтр в прослушиватель в `Listeners` коллекции для трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`listeners`|Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> совместно используют одну и ту же коллекцию Listeners. При добавлении объекта прослушивателя в коллекцию в одном из этих классов другой класс использует тот же прослушиватель. Классы прослушивателей являются производными от <xref:System.Diagnostics.TraceListener>.  
  
 Если `name` атрибут прослушивателя трассировки не указан, то <xref:System.Diagnostics.TraceListener.Name%2A> для прослушивателя трассировки по умолчанию используется пустая строка (""). Если у приложения есть только один прослушиватель, можно добавить его без указания имени и удалить его, указав в качестве имени пустую строку. Однако если приложение имеет более одного прослушивателя, необходимо указать уникальные имена для каждого прослушивателя трассировки, что позволяет определять отдельные прослушиватели трассировки в <xref:System.Diagnostics.Debug.Listeners%2A> коллекциях и <xref:System.Diagnostics.Trace.Listeners%2A> управлять ими.  
  
> [!NOTE]
> Добавление нескольких прослушивателей трассировки одного и того же типа и с одним и тем же именем приводит к тому, что только один прослушиватель трассировки этого типа и `Listeners` имя добавляются в коллекцию. Тем не менее можно программно добавить несколько идентичных прослушивателей в `Listeners` коллекцию.  
  
 Значение атрибута **initializeData** зависит от типа создаваемого прослушивателя. Не все прослушиватели трассировки нуждаются в указании **initializeData**.  
  
> [!NOTE]
> При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен". Это предупреждение возникает из-за того, что параметры конфигурации проверяются <xref:System.Diagnostics.TraceListener>по абстрактному базовому классу, который не `initializeData` распознает атрибут. Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице показаны прослушиватели трассировки, которые включены в .NET Framework и описаны значения их атрибутов **initializeData** .  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream` Значение<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> для конструктора.  Задайте для`true`атрибута значение "", чтобы записывать выходные данные трассировки и <xref:System.Console.Error%2A?displayProperty=nameWithType>отладки в; `initializeData` "`false`" для <xref:System.Console.Out%2A?displayProperty=nameWithType>записи.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.DelimitedListTraceListener> в который производится запись.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.EventSchemaTraceListener> производится запись.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.TextWriterTraceListener> производится запись.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.XmlWriterTraceListener> производится запись.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать  **\<Add >** Elements для добавления прослушивателей `MyEventListener` `MyListener` и в коллекцию **Listeners** . `MyListener`создает файл с именем `MyListener.log` и записывает выходные данные в файл. `MyEventListener`создает запись в журнале событий.  
  
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
- [Схема параметров трассировки и отладки](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
