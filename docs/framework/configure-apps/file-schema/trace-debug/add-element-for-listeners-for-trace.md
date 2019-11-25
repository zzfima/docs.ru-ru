---
title: Элемент <add> для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: eb3e9cf4a6d138998cfde865cda8ed4146be26d0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088982"
---
# <a name="add-element-for-listeners-for-trace"></a>\<добавить элемент > для прослушивателей \<> для \<Trace >
Добавляет прослушиватель в коллекцию **Listeners** .  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trace**](trace-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**прослушиватели**](listeners-element-for-trace.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**

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
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Добавляет фильтр к прослушивателю в коллекции `Listeners` для трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`listeners`|Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
## <a name="remarks"></a>Заметки  
 Классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> используют одну и ту же коллекцию **прослушивателей** . При добавлении объекта прослушивателя в коллекцию в одном из этих классов другой класс использует тот же прослушиватель. Классы прослушивателей являются производными от <xref:System.Diagnostics.TraceListener>.  
  
 Если не указать атрибут `name` прослушивателя трассировки, то <xref:System.Diagnostics.TraceListener.Name%2A> прослушивателя трассировки по умолчанию имеет пустую строку (""). Если у приложения есть только один прослушиватель, можно добавить его без указания имени и удалить его, указав в качестве имени пустую строку. Однако если приложение имеет несколько прослушивателей, необходимо указать уникальные имена для каждого прослушивателя трассировки, что позволяет определять отдельные прослушиватели трассировки и управлять ими в коллекциях <xref:System.Diagnostics.Debug.Listeners%2A> и <xref:System.Diagnostics.Trace.Listeners%2A>.  
  
> [!NOTE]
> Добавление нескольких прослушивателей трассировки одного и того же типа и с одним и тем же именем приводит к тому, что только один прослушиватель трассировки этого типа и имя добавляются в коллекцию `Listeners`. Однако можно программно добавить несколько идентичных прослушивателей в коллекцию `Listeners`.  
  
 Значение атрибута **initializeData** зависит от типа создаваемого прослушивателя. Не все прослушиватели трассировки нуждаются в указании **initializeData**.  
  
> [!NOTE]
> При использовании атрибута `initializeData` может появиться предупреждение компилятора "атрибут initializeData не объявлен". Это предупреждение возникает из-за того, что параметры конфигурации проверяются на основе абстрактного базового класса <xref:System.Diagnostics.TraceListener>, который не распознает атрибут `initializeData`. Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице показаны прослушиватели трассировки, которые включены в .NET Framework и описаны значения их атрибутов **initializeData** .  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Значение `useErrorStream` для конструктора <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Присвойте атрибуту `initializeData` значение "`true`", чтобы записывать выходные данные трассировки и отладки в <xref:System.Console.Error%2A?displayProperty=nameWithType>, "`false`" для записи в <xref:System.Console.Out%2A?displayProperty=nameWithType>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.DelimitedListTraceListener> записывается.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, в который записывается <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который записывается <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который записывается <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать **\<добавления >** элементов для добавления прослушивателей `MyListener` и `MyEventListener` в коллекцию **Listeners** . `MyListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл. `MyEventListener` создает запись в журнале событий.  
  
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
