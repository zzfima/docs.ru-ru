---
title: <add>Элемент <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153676"
---
# <a name="add-element-for-listeners-for-trace"></a>\<добавить элемент \<> \<для слушателей> для> трассировки
Добавляет слушателя в коллекцию **Слушателей.**  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<след>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|**тип**|Обязательный атрибут.<br /><br /> Определяет тип слушателя. Необходимо использовать строку, соответствующую требованиям, указанным в [определении полностью квалифицированных имен типов.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)|  
|**инициализацияДанны**|Необязательный атрибут.<br /><br /> Строка перешла к конструктору для указанного класса.|  
|**name**|Необязательный атрибут.<br /><br /> Определяет имя слушателя.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<фильтр>](filter-element-for-add-for-listeners-for-trace.md)|Добавляет фильтр слушателю в `Listeners` коллекцию для отслеживания.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`listeners`|Определяет слушателя, который собирает, хранит и направляет сообщения. Слушатели направляют результаты отслеживания на соответствующую цель.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
## <a name="remarks"></a>Remarks  
 <xref:System.Diagnostics.Debug> Классы <xref:System.Diagnostics.Trace> и классы имеют одну и ту же коллекцию **Слушателей.** Если вы добавляете объект слушателя в коллекцию в одном из этих классов, другой класс использует тот же самый слушатель. Классы слушателя вытекают из <xref:System.Diagnostics.TraceListener>.  
  
 Если вы не `name` указываете атрибут слушателя <xref:System.Diagnostics.TraceListener.Name%2A> трассировки, то слушатель трассировки по умолчанию по умолчанию к пустой строке ("). Если в приложении есть только один слушатель, вы можете добавить его, не указывая имя, и удалить его, указав пустую строку для имени. Однако, если в вашем приложении более одного слушателя, следует указать уникальные имена для каждого <xref:System.Diagnostics.Debug.Listeners%2A> слушателя трассы, что позволяет идентифицировать и управлять отдельными слушателями трассировки в коллекциях и <xref:System.Diagnostics.Trace.Listeners%2A> коллекциях.  
  
> [!NOTE]
> Добавление более одного слушателя трассы одного и того же типа и с тем же именем `Listeners` приводит к добавлению в коллекцию только одного слушателя этого типа и имени. Тем не менее, вы можете программно `Listeners` добавить несколько идентичных слушателей в коллекцию.  
  
 Значение атрибута **инициализироватьData** зависит от типа создаваемого слушателя. Не все слушатели трасс требуют, чтобы вы **указали инициализироватьData.**  
  
> [!NOTE]
> При использовании `initializeData` атрибута можно получить предупреждение компилятора "Атрибут "initializeData" не объявлен". Это предупреждение возникает из-за того, что <xref:System.Diagnostics.TraceListener>настройки конфигурации `initializeData` проверяются на основе абстрактного базового класса, который не распознает атрибут. Как правило, можно проигнорировать это предупреждение для реализации микрослушателя, у которых есть конструктор, который принимает параметр.  
  
 В следующей таблице показаны слушатели трасс, включенные в рамку .NET, и описывается значение их **инициализировать** атрибуты Data.  
  
|Класс слушателя трассировки|инициализация значения атрибутаData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Значение `useErrorStream` для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.  Установите `initializeData` атрибут`true`на " для записи <xref:System.Console.Error%2A?displayProperty=nameWithType>трассировки и отладки вывода; ",`false`чтобы <xref:System.Console.Out%2A?displayProperty=nameWithType>написать .|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя имени существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, который <xref:System.Diagnostics.EventSchemaTraceListener> пишет.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, который <xref:System.Diagnostics.TextWriterTraceListener> пишет.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, который <xref:System.Diagnostics.XmlWriterTraceListener> пишет.|  
  
## <a name="example"></a>Пример  
 Ниже приводится пример, ** \<** как использовать>`MyListener` элементы для добавления слушателей и `MyEventListener` коллекции **Слушателей.** `MyListener`создает вызванный `MyListener.log` файл и записывает вывод в файл. `MyEventListener`создает запись в журнале событий.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Схема настроек трассировки и отпараги](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
