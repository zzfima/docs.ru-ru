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
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="212aa-102">\<элемент Filter > для \<добавления > для \<прослушивателей > \<для источника ></span><span class="sxs-lookup"><span data-stu-id="212aa-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="212aa-103">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="212aa-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="212aa-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="212aa-104">\<configuration></span></span>  
<span data-ttu-id="212aa-105">\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="212aa-105">\<system.diagnostics></span></span>  
<span data-ttu-id="212aa-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="212aa-106">\<sources></span></span>  
<span data-ttu-id="212aa-107">\<исходный ></span><span class="sxs-lookup"><span data-stu-id="212aa-107">\<source></span></span>  
<span data-ttu-id="212aa-108">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="212aa-108">\<listeners></span></span>  
<span data-ttu-id="212aa-109">\<add></span><span class="sxs-lookup"><span data-stu-id="212aa-109">\<add></span></span>  
<span data-ttu-id="212aa-110">\<> фильтра</span><span class="sxs-lookup"><span data-stu-id="212aa-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="212aa-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="212aa-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="212aa-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="212aa-112">Attributes and Elements</span></span>  
 <span data-ttu-id="212aa-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="212aa-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="212aa-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="212aa-114">Attributes</span></span>  
  
|<span data-ttu-id="212aa-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="212aa-115">Attribute</span></span>|<span data-ttu-id="212aa-116">Описание</span><span class="sxs-lookup"><span data-stu-id="212aa-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="212aa-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="212aa-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="212aa-118">Указывает тип фильтра, который должен наследоваться от <xref:System.Diagnostics.TraceFilter> класса.</span><span class="sxs-lookup"><span data-stu-id="212aa-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="212aa-119">Можно использовать имя, уточненное пространством имен типа, которое соответствует <xref:System.Type.FullName%2A> свойству типа, или можно использовать полное имя типа, включая сведения о сборке, соответствующие <xref:System.Type.AssemblyQualifiedName%2A> свойству.</span><span class="sxs-lookup"><span data-stu-id="212aa-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="212aa-120">Дополнительные сведения о полных именах типов см. в разделе Указание полных [имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="212aa-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="212aa-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="212aa-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="212aa-122">Строка, передаваемая конструктору для указанного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="212aa-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="212aa-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="212aa-123">Child Elements</span></span>  
 <span data-ttu-id="212aa-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="212aa-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="212aa-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="212aa-125">Parent Elements</span></span>  
  
|<span data-ttu-id="212aa-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="212aa-126">Element</span></span>|<span data-ttu-id="212aa-127">Описание</span><span class="sxs-lookup"><span data-stu-id="212aa-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="212aa-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="212aa-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="212aa-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="212aa-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="212aa-130">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="212aa-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="212aa-131">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="212aa-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="212aa-132">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="212aa-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="212aa-133">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="212aa-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="212aa-134">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="212aa-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="212aa-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="212aa-135">Remarks</span></span>  
 <span data-ttu-id="212aa-136">Элемент должен содержаться `<add>` в элементе для прослушивателя источника трассировки, который указывает тип прослушивателя, а не только имя прослушивателя, определенного в [ \<> шаредлистенерс.](sharedlisteners-element.md) `<filter>`</span><span class="sxs-lookup"><span data-stu-id="212aa-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="212aa-137">Если прослушиватель определен в [ \<> шаредлистенерс](sharedlisteners-element.md), то фильтр для этого прослушивателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="212aa-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="212aa-138">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="212aa-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="212aa-139">Пример</span><span class="sxs-lookup"><span data-stu-id="212aa-139">Example</span></span>  
 <span data-ttu-id="212aa-140">В следующем примере показано, как с помощью `<filter>` элемента добавить фильтр в прослушиватель `console` в `Listeners` коллекции для источника `myTraceSource`трассировки, указав уровень событий фильтра как `Error`.</span><span class="sxs-lookup"><span data-stu-id="212aa-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="212aa-141">См. также</span><span class="sxs-lookup"><span data-stu-id="212aa-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="212aa-142">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="212aa-142">Trace and Debug Settings Schema</span></span>](index.md)
