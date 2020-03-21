---
title: <add>Элемент <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153689"
---
# <a name="add-element-for-listeners-for-source"></a>\<добавить элемент \<> \<для слушателей> для исходных>
Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<источники>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<источник>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`type`|Требуемый атрибут, если вы не ссылаетесь `sharedListeners` на слушателя в коллекции, и в этом случае вам нужно только сослаться на него по имени (см. [пример).](#example)<br /><br /> Определяет тип слушателя. Необходимо использовать строку, соответствующую требованиям, указанным в [определении полностью квалифицированных имен типов.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка перешла к конструктору для указанного класса. A <xref:System.Configuration.ConfigurationException> брошен, если класс не имеет конструктора, который занимает строку.|  
|`name`|Необязательный атрибут.<br /><br /> Определяет имя слушателя.|  
|`traceOutputOptions`|Необязательный атрибут.<br /><br /> Определяет значение <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> свойства для слушателя трассировки.|  
|(таможенные атрибуты)|Дополнительные атрибуты.<br /><br /> Определяет значение для специфических атрибутов, определенных <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> методом для этого слушателя. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>является примером дополнительного атрибута, уникального <xref:System.Diagnostics.DelimitedListTraceListener> для класса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<фильтр>](filter-element-for-add-for-listeners-for-source.md)|Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
|`listeners`|Определяет слушателей, которые собирают, хранят и направляют сообщения.|  
  
## <a name="remarks"></a>Remarks  
 Классы слушателя, поставляемые с помощью <xref:System.Diagnostics.TraceListener> рамочной программы .NET, происходят из класса.  
  
 Если вы не `name` указываете атрибут слушателя <xref:System.Diagnostics.TraceListener.Name%2A> трассировки, свойство слушателя трассировки по умолчанию по умолчанию к пустой строке (""). Если в приложении есть только один слушатель, вы можете добавить его, не указывая имя, и вы можете удалить его, указав пустую строку для имени. Однако, если в вашем приложении более одного слушателя, следует указать уникальное имя для каждого слушателя трассы, что позволяет идентифицировать и управлять отдельными слушателями трассировки в коллекции. <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType>  
  
> [!NOTE]
> Добавление более одного слушателя трассы одного и того же типа и с тем же именем `Listeners` приводит к добавлению в коллекцию только одного слушателя этого типа и имени. Тем не менее, вы можете программно `Listeners` добавить несколько идентичных слушателей в коллекцию.  
  
 Значение атрибута `initializeData` зависит от типа создаваемого слушателя. Не все слушатели трасстребуют `initializeData`указания.  
  
> [!NOTE]
> При использовании `initializeData` атрибута можно получить предупреждение компилятора "Атрибут "initializeData" не объявлен". Это предупреждение возникает из-за того, что <xref:System.Diagnostics.TraceListener>настройки конфигурации `initializeData` проверяются на основе абстрактного базового класса, который не распознает атрибут. Как правило, можно проигнорировать это предупреждение для реализации микрослушателя, у которых есть конструктор, который принимает параметр.  
  
 В следующей таблице показаны слушатели трасс, включенные в `initializeData` рамку .NET, и описывается значение их атрибутов.  
  
|Класс слушателя трассировки|инициализация значения атрибутаData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Значение `useErrorStream` для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.  Установите `initializeData` атрибут`true`на "для записи трассировки и отладки вывода в стандартный поток ошибок; установить его`false`на ", чтобы написать на стандартный поток вывода.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, который <xref:System.Diagnostics.EventSchemaTraceListener> пишет.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, который <xref:System.Diagnostics.TextWriterTraceListener> пишет.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, который <xref:System.Diagnostics.XmlWriterTraceListener> пишет.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 Ниже приводится следующий `<add>` пример, как `console` `textListener` использовать `Listeners` элементы для `TraceSourceApp`добавления слушателей и в коллекцию для источника трассировки. Слушатель `textListener` записывает выход трассировки в файл myListener.log.  
  
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
