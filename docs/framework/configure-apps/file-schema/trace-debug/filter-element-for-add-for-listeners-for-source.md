---
title: Элемент <filter> для <add> для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: ec288685f47c8a35e2371c31d359b604a4967196
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697162"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="5ffe7-102">Элемент \<filter > для > \<Add для \<listeners > @no__t 3source</span><span class="sxs-lookup"><span data-stu-id="5ffe7-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="5ffe7-103">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="5ffe7-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5ffe7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="5ffe7-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ffe7-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="5ffe7-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ffe7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="5ffe7-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ffe7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="5ffe7-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="5ffe7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="5ffe7-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9[ **&nbsp;2Add >** ](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="5ffe7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>  
<span data-ttu-id="5ffe7-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5, no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 @ no__t-10 @ no__t-11 **&nbsp;3filter >**</span><span class="sxs-lookup"><span data-stu-id="5ffe7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ffe7-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ffe7-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ffe7-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5ffe7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5ffe7-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ffe7-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ffe7-114">Attributes</span></span>  
  
|<span data-ttu-id="5ffe7-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ffe7-115">Attribute</span></span>|<span data-ttu-id="5ffe7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5ffe7-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="5ffe7-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="5ffe7-118">Указывает тип фильтра, который должен наследовать от класса <xref:System.Diagnostics.TraceFilter>.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="5ffe7-119">Можно использовать имя, уточненное пространством имен типа, которое соответствует свойству <xref:System.Type.FullName%2A> типа, или можно использовать полное имя типа, включая сведения о сборке, соответствующие свойству <xref:System.Type.AssemblyQualifiedName%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="5ffe7-120">Дополнительные сведения о полных именах типов см. в разделе Указание полных [имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="5ffe7-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="5ffe7-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5ffe7-122">Строка, передаваемая конструктору для указанного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ffe7-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5ffe7-123">Child Elements</span></span>  
 <span data-ttu-id="5ffe7-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ffe7-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5ffe7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5ffe7-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ffe7-126">Element</span></span>|<span data-ttu-id="5ffe7-127">Описание</span><span class="sxs-lookup"><span data-stu-id="5ffe7-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5ffe7-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5ffe7-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="5ffe7-130">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="5ffe7-131">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="5ffe7-132">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="5ffe7-133">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="5ffe7-134">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ffe7-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ffe7-135">Remarks</span></span>  
 <span data-ttu-id="5ffe7-136">Элемент `<filter>` должен содержаться в элементе `<add>` для прослушивателя источника трассировки, который указывает тип прослушивателя, а не только имя прослушивателя, определенного в [@no__t 3sharedListeners >](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="5ffe7-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="5ffe7-137">Если прослушиватель определен в [@no__t >](sharedlisteners-element.md), то фильтр для этого прослушивателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="5ffe7-138">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ffe7-139">Пример</span><span class="sxs-lookup"><span data-stu-id="5ffe7-139">Example</span></span>  
 <span data-ttu-id="5ffe7-140">В следующем примере показано, как использовать элемент `<filter>` для добавления фильтра в прослушиватель `console` в коллекции `Listeners` для источника трассировки `myTraceSource`, указав уровень событий Filter как `Error`.</span><span class="sxs-lookup"><span data-stu-id="5ffe7-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ffe7-141">См. также</span><span class="sxs-lookup"><span data-stu-id="5ffe7-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="5ffe7-142">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="5ffe7-142">Trace and Debug Settings Schema</span></span>](index.md)
