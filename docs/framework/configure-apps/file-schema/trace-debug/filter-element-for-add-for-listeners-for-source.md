---
title: <filter><add> Элемент для<listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0d25d0b955a94986147922914068c8a1cf2d96c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920521"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a>\<элемент Filter > для \<добавления > для \<прослушивателей > \<для источника >
Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.  
  
 \<configuration>  
\<> System. Diagnostics  
\<источники >  
\<исходный >  
\<прослушиватели >  
\<add>  
\<> фильтра  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`type`|Обязательный атрибут.<br /><br /> Указывает тип фильтра, который должен наследоваться от <xref:System.Diagnostics.TraceFilter> класса. Можно использовать имя, уточненное пространством имен типа, которое соответствует <xref:System.Type.FullName%2A> свойству типа, или можно использовать полное имя типа, включая сведения о сборке, соответствующие <xref:System.Type.AssemblyQualifiedName%2A> свойству. Дополнительные сведения о полных именах типов см. в разделе Указание полных [имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса фильтра.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
|`add`|Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Элемент должен содержаться `<add>` в элементе для прослушивателя источника трассировки, который указывает тип прослушивателя, а не только имя прослушивателя, определенного в [ \<> шаредлистенерс.](sharedlisteners-element.md) `<filter>` Если прослушиватель определен в [ \<> шаредлистенерс](sharedlisteners-element.md), то фильтр для этого прослушивателя должен быть определен в этом элементе.  
  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как с помощью `<filter>` элемента добавить фильтр в прослушиватель `console` в `Listeners` коллекции для источника `myTraceSource`трассировки, указав уровень событий фильтра как `Error`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Схема параметров трассировки и отладки](index.md)
