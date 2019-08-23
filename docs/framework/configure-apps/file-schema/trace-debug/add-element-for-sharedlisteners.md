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
ms.openlocfilehash: c4b83834fb7aaf64a696b85bd2c8da47cfba2397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927211"
---
# <a name="add-element-for-sharedlisteners"></a>\<Добавление элемента > для \<шаредлистенерс >
Добавляет прослушиватель в коллекцию `sharedListeners`. `sharedListeners`— Это коллекция прослушивателей, на которые могут ссылаться любые [ \<исходные >](source-element.md) или [ \<> трассировки](trace-element.md) .  По умолчанию прослушиватели в `sharedListeners` коллекции не помещаются `Listeners` в коллекцию. Они должны быть добавлены по имени в [ \<исходный >](source-element.md) или [ \<> трассировки](trace-element.md). Невозможно получить прослушиватели в `sharedListeners` коллекции в коде во время выполнения.  
  
 \<configuration>  
&nbsp;&nbsp;\<> System. Diagnostics  
&nbsp;&nbsp;&nbsp;&nbsp;\<Элемент > Шаредлистенерс  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<Добавить >  
  
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
|`name`|Обязательный атрибут.<br /><br /> Указывает имя прослушивателя, который используется для добавления общего прослушивателя в `Listeners` коллекцию.|  
|`type`|Обязательный атрибут.<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса.|  
|`traceOutputOptions`|Необязательный атрибут.<br/><br/>Строковое представление одного или нескольких <xref:System.Diagnostics.TraceOptions> элементов перечисления, которое указывает данные, записываемые в выходные данные трассировки. Несколько элементов разделяются запятыми. Значение по умолчанию — None.|

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
  
## <a name="remarks"></a>Примечания  
 Классы прослушивателей, поставляемые с .NET Framework, являются производными от <xref:System.Diagnostics.TraceListener> класса. Значение `name` атрибута используется для добавления общего прослушивателя `Listeners` в коллекцию либо для трассировки, либо для источника трассировки. Значение `initializeData` атрибута зависит от типа создаваемого прослушивателя. Не все прослушиватели трассировки нуждаются в указании `initializeData`.  
  
> [!NOTE]
> При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен". Это предупреждение возникает из-за того, что параметры конфигурации проверяются <xref:System.Diagnostics.TraceListener>по абстрактному базовому классу, который не `initializeData` распознает атрибут. Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице показаны прослушиватели трассировки, которые включены в состав .NET Framework и описываются значения их `initializeData` атрибутов.  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|`useErrorStream` Значение<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> для конструктора.  Задайте для`true``false`атрибута значение "", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок; задайте для него значение "", чтобы выполнить запись в стандартный выходной поток. `initializeData`|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Имя файла, <xref:System.Diagnostics.DelimitedListTraceListener> в который производится запись.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.EventSchemaTraceListener> производится запись.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.TextWriterTraceListener> производится запись.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Имя файла, в который <xref:System.Diagnostics.XmlWriterTraceListener> производится запись.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<add>` элементы для <xref:System.Diagnostics.TextWriterTraceListener> `textListener` добавления `sharedListeners` в коллекцию.   `textListener`добавляется по имени в `Listeners` коллекцию для источника `TraceSourceApp`трассировки. `textListener` Прослушиватель записывает выходные данные трассировки в файл myListener. log.  
  
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
