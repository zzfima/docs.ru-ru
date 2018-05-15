---
title: '&lt;Фильтр&gt; элемент для &lt;добавить&gt; для &lt;прослушиватели&gt; для &lt;источника&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 763d15a1391d8c9539d5fb92d4ad50132c17c065
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="87a11-102">&lt;Фильтр&gt; элемент для &lt;добавить&gt; для &lt;прослушиватели&gt; для &lt;источника&gt;</span><span class="sxs-lookup"><span data-stu-id="87a11-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="87a11-103">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="87a11-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="87a11-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="87a11-104">\<configuration></span></span>  
<span data-ttu-id="87a11-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="87a11-105">\<system.diagnostics></span></span>  
<span data-ttu-id="87a11-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="87a11-106">\<sources></span></span>  
<span data-ttu-id="87a11-107">\<Источник ></span><span class="sxs-lookup"><span data-stu-id="87a11-107">\<source></span></span>  
<span data-ttu-id="87a11-108">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="87a11-108">\<listeners></span></span>  
<span data-ttu-id="87a11-109">\<add></span><span class="sxs-lookup"><span data-stu-id="87a11-109">\<add></span></span>  
<span data-ttu-id="87a11-110">\<Фильтр ></span><span class="sxs-lookup"><span data-stu-id="87a11-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a11-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87a11-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87a11-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87a11-112">Attributes and Elements</span></span>  
 <span data-ttu-id="87a11-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="87a11-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87a11-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87a11-114">Attributes</span></span>  
  
|<span data-ttu-id="87a11-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="87a11-115">Attribute</span></span>|<span data-ttu-id="87a11-116">Описание</span><span class="sxs-lookup"><span data-stu-id="87a11-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="87a11-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="87a11-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="87a11-118">Указывает тип фильтра, который должен быть производным от <xref:System.Diagnostics.TraceFilter> класса.</span><span class="sxs-lookup"><span data-stu-id="87a11-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="87a11-119">Можно использовать имя с указанием пространства имен типа, который соответствует типу <xref:System.Type.FullName%2A> свойства, или можно использовать полное имя, включая сведения о сборке, которая соответствует <xref:System.Type.AssemblyQualifiedName%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="87a11-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="87a11-120">Сведения о полных именах см. в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="87a11-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="87a11-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="87a11-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="87a11-122">Строка, передаваемая в конструктор для заданного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="87a11-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87a11-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87a11-123">Child Elements</span></span>  
 <span data-ttu-id="87a11-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="87a11-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87a11-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87a11-125">Parent Elements</span></span>  
  
|<span data-ttu-id="87a11-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="87a11-126">Element</span></span>|<span data-ttu-id="87a11-127">Описание</span><span class="sxs-lookup"><span data-stu-id="87a11-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="87a11-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87a11-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="87a11-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="87a11-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="87a11-130">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="87a11-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="87a11-131">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="87a11-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="87a11-132">Содержит прослушиватели для сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="87a11-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="87a11-133">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="87a11-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="87a11-134">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="87a11-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87a11-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="87a11-135">Remarks</span></span>  
 <span data-ttu-id="87a11-136">`<filter>` Элемент, содержащийся в `<add>` элемент для прослушивателя трассировки источника, задающий тип прослушивателя не только имя прослушивателя, определенное в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="87a11-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="87a11-137">Если прослушиватель определен в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), фильтр для этого прослушивателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="87a11-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="87a11-138">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="87a11-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87a11-139">Пример</span><span class="sxs-lookup"><span data-stu-id="87a11-139">Example</span></span>  
 <span data-ttu-id="87a11-140">В следующем примере показано, как использовать `<filter>` элемент, чтобы добавить фильтр к прослушивателю `console` в `Listeners` коллекции для источника трассировки `myTraceSource`, указав уровень фильтра событий, как `Error`.</span><span class="sxs-lookup"><span data-stu-id="87a11-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87a11-141">См. также</span><span class="sxs-lookup"><span data-stu-id="87a11-141">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="87a11-142">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="87a11-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
