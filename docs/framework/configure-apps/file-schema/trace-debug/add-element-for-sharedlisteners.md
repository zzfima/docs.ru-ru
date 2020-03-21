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
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153611"
---
# <a name="add-element-for-sharedlisteners"></a>\<добавить элемент \<> для> общих слушателей
Добавляет прослушиватель в коллекцию `sharedListeners`. `sharedListeners`представляет собой набор слушателей, что любой [ \<источник>](source-element.md) или [ \<след>](trace-element.md) может ссылаться.  По умолчанию слушатели в `sharedListeners` коллекции `Listeners` не помещаются в коллекцию. Они должны быть добавлены по имени к [ \<источнику>](source-element.md) или [ \<>следа. ](trace-element.md) Невозможно получить слушателей в коллекции `sharedListeners` в коде во время выполнения.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<общиеслушатели>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**

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
  
|attribute|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Упоняет имя слушателя, который используется для добавления `Listeners` общего слушателя в коллекцию.|  
|`type`|Обязательный атрибут.<br /><br /> Определяет тип слушателя. Необходимо использовать строку, соответствующую требованиям, указанным в [определении полностью квалифицированных имен типов.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка перешла к конструктору для указанного класса.|  
|`traceOutputOptions`|Необязательный атрибут.<br/><br/>Представление строки одного <xref:System.Diagnostics.TraceOptions> или нескольких участников, отодевавав данные, которые должны быть записаны на вывод трассировки. Несколько элементов разделены запятыми. Значение по умолчанию — "Нет".|

### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<фильтр>](filter-element-for-add-for-sharedlisteners.md)|Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sharedListeners`|Коллекция слушателей, на которую может ссылаться любой источник или элемент микро- информации.|  
  
## <a name="remarks"></a>Remarks  
 Классы слушателя, поставляемые с помощью <xref:System.Diagnostics.TraceListener> рамочной программы .NET, происходят из класса. Значение для `name` атрибута используется для добавления `Listeners` общего слушателя в коллекцию для отслеживания или источника следов. Значение атрибута `initializeData` зависит от типа создаваемого слушателя. Не все слушатели трасстребуют `initializeData`указания.  
  
> [!NOTE]
> При использовании `initializeData` атрибута можно получить предупреждение компилятора "Атрибут "initializeData" не объявлен". Это предупреждение возникает из-за того, что <xref:System.Diagnostics.TraceListener>настройки конфигурации `initializeData` проверяются на основе абстрактного базового класса, который не распознает атрибут. Как правило, можно проигнорировать это предупреждение для реализации микрослушателя, у которых есть конструктор, который принимает параметр.  
  
 В следующей таблице показаны слушатели трасс, включенные в `initializeData` рамку .NET, и описывается значение их атрибутов.  
  
|Класс слушателя трассировки|инициализация значения атрибутаData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Значение `useErrorStream` для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.  Установите `initializeData` атрибут`true`на "для записи трассировки и отладки вывода в стандартный поток ошибок; установить его`false`на ", чтобы написать на стандартный поток вывода.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, который <xref:System.Diagnostics.EventSchemaTraceListener> пишет.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, который <xref:System.Diagnostics.TextWriterTraceListener> пишет.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Имя файла, который <xref:System.Diagnostics.XmlWriterTraceListener> пишет.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере `<add>` показано, как <xref:System.Diagnostics.TextWriterTraceListener> `textListener` использовать `sharedListeners` элементы для добавления в коллекцию.   `textListener`добавляется по имени `Listeners` в коллекцию `TraceSourceApp`для источника трассировки. Слушатель `textListener` записывает выход трассировки в файл myListener.log.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Схема настроек трассировки и отпараги](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
