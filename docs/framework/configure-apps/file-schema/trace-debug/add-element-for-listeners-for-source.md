---
title: <add>Элемент для <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 96bfde3ec425f6f77d1d655808d155eb0e6fcd0f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927195"
---
# <a name="add-element-for-listeners-for-source"></a>\<Добавление элемента > для \<прослушивателей, \<> для исходного >
Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.  
  
 \<configuration>  
\<> System. Diagnostics  
\<источники >  
\<исходный >  
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
|`type`|Обязательный атрибут, если вы не ссылаетесь на прослушиватель в `sharedListeners` коллекции. в этом случае необходимо ссылаться на него по имени (см. [Пример](#example)).<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса. <xref:System.Configuration.ConfigurationException> Исключение создается, если класс не имеет конструктора, принимающего строку.|  
|`name`|Необязательный атрибут.<br /><br /> Указывает имя прослушивателя.|  
|`traceOutputOptions`|Необязательный атрибут.<br /><br /> Указывает значение <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> свойства для прослушивателя трассировки.|  
|[настраиваемые атрибуты]|Необязательные атрибуты.<br /><br /> Задает значение для атрибутов <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> прослушивателя, определенных методом для этого прослушивателя. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>Пример дополнительного атрибута, уникального для <xref:System.Diagnostics.DelimitedListTraceListener> класса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
|`listeners`|Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.|  
  
## <a name="remarks"></a>Примечания  
 Классы прослушивателей, поставляемые с .NET Framework, являются производными от <xref:System.Diagnostics.TraceListener> класса.  
  
 Если `name` атрибут прослушивателя трассировки не указан <xref:System.Diagnostics.TraceListener.Name%2A> , свойство прослушивателя трассировки по умолчанию имеет пустую строку (""). Если у приложения есть только один прослушиватель, его можно добавить без указания имени, и его можно удалить, указав в качестве имени пустую строку. Однако если приложение имеет несколько прослушивателей, необходимо указать уникальное имя для каждого прослушивателя трассировки, что позволяет определять отдельные прослушиватели трассировки в <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> коллекции и управлять ими.  
  
> [!NOTE]
> Добавление нескольких прослушивателей трассировки одного и того же типа и с одним и тем же именем приводит к тому, что только один прослушиватель трассировки этого типа и `Listeners` имя добавляются в коллекцию. Тем не менее можно программно добавить несколько идентичных прослушивателей в `Listeners` коллекцию.  
  
 Значение `initializeData` атрибута зависит от типа создаваемого прослушивателя. Не все прослушиватели трассировки нуждаются в указании `initializeData`.  
  
> [!NOTE]
> При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен". Это предупреждение возникает из-за того, что параметры конфигурации проверяются <xref:System.Diagnostics.TraceListener>по абстрактному базовому классу, который не `initializeData` распознает атрибут. Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице показаны прослушиватели трассировки, которые включены в состав .NET Framework и описываются значения их `initializeData` атрибутов.  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream` Значение<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> для конструктора.  Задайте для`true``false`атрибута значение "", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок; задайте для него значение "", чтобы выполнить запись в стандартный выходной поток. `initializeData`|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.DelimitedListTraceListener> в который производится запись.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.EventSchemaTraceListener> производится запись.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.TextWriterTraceListener> производится запись.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.XmlWriterTraceListener> производится запись.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<add>` элементы для добавления прослушивателей `console` и `textListener` в `Listeners` коллекцию для источника `TraceSourceApp`трассировки. `textListener` Прослушиватель записывает выходные данные трассировки в файл myListener. log.  
  
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
