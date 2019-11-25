---
title: Элемент <add> для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: c32205310f9fc451a5a55a943f925ee52f65c8a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088990"
---
# <a name="add-element-for-listeners-for-source"></a>\<добавить элемент > для прослушивателей \<> для \<исходного кода >
Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sources >** ](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**source >** ](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<listeners >** ](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**

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
|`type`|Обязательный атрибут, если вы не ссылаетесь на прослушиватель в коллекции `sharedListeners`. в этом случае необходимо ссылаться на него по имени (см. [Пример](#example)).<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса. Если у класса нет конструктора, который принимает строку, создается <xref:System.Configuration.ConfigurationException>.|  
|`name`|Необязательный атрибут.<br /><br /> Указывает имя прослушивателя.|  
|`traceOutputOptions`|Необязательный атрибут.<br /><br /> Задает значение свойства <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> для прослушивателя трассировки.|  
|[настраиваемые атрибуты]|Необязательные атрибуты.<br /><br /> Задает значение для атрибутов прослушивателя, определенных методом <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> для этого прослушивателя. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> является примером дополнительного атрибута, уникального для класса <xref:System.Diagnostics.DelimitedListTraceListener>.|  
  
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
  
## <a name="remarks"></a>Заметки  
 Классы прослушивателей, поставляемые с .NET Framework, являются производными от класса <xref:System.Diagnostics.TraceListener>.  
  
 Если не указать атрибут `name` прослушивателя трассировки, свойство <xref:System.Diagnostics.TraceListener.Name%2A> прослушивателя трассировки по умолчанию имеет пустую строку (""). Если у приложения есть только один прослушиватель, его можно добавить без указания имени, и его можно удалить, указав в качестве имени пустую строку. Однако если приложение имеет несколько прослушивателей, необходимо указать уникальное имя для каждого прослушивателя трассировки, что позволяет определять отдельные прослушиватели трассировки в коллекции <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> и управлять ими.  
  
> [!NOTE]
> Добавление нескольких прослушивателей трассировки одного и того же типа и с одним и тем же именем приводит к тому, что только один прослушиватель трассировки этого типа и имя добавляются в коллекцию `Listeners`. Однако можно программно добавить несколько идентичных прослушивателей в коллекцию `Listeners`.  
  
 Значение атрибута `initializeData` зависит от типа создаваемого прослушивателя. Не все прослушиватели трассировки должны указывать `initializeData`.  
  
> [!NOTE]
> При использовании атрибута `initializeData` может появиться предупреждение компилятора "атрибут initializeData не объявлен". Это предупреждение возникает из-за того, что параметры конфигурации проверяются на основе абстрактного базового класса <xref:System.Diagnostics.TraceListener>, который не распознает атрибут `initializeData`. Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице показаны прослушиватели трассировки, которые включены в .NET Framework и описаны значения их `initializeData`ных атрибутов.  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Значение `useErrorStream` для конструктора <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Присвойте атрибуту `initializeData` значение "`true`", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок. Задайте для него значение "`false`", чтобы выполнить запись в стандартный выходной поток.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла, в который <xref:System.Diagnostics.DelimitedListTraceListener> записывается.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, в который записывается <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который записывается <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, в который записывается <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<add>` элементы для добавления прослушивателей `console` и `textListener` в коллекцию `Listeners` для источника трассировки `TraceSourceApp`. Прослушиватель `textListener` записывает выходные данные трассировки в файл myListener. log.  
  
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
