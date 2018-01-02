---
title: "&lt;Фильтр&gt; элемент для &lt;добавить&gt; для &lt;прослушиватели&gt; для &lt;источника&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ff5acf8edcda68979c04f5e62237464ee6f040a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="0519f-102">&lt;Фильтр&gt; элемент для &lt;добавить&gt; для &lt;прослушиватели&gt; для &lt;источника&gt;</span><span class="sxs-lookup"><span data-stu-id="0519f-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="0519f-103">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="0519f-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="0519f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0519f-104">\<configuration></span></span>  
<span data-ttu-id="0519f-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="0519f-105">\<system.diagnostics></span></span>  
<span data-ttu-id="0519f-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="0519f-106">\<sources></span></span>  
<span data-ttu-id="0519f-107">\<Источник ></span><span class="sxs-lookup"><span data-stu-id="0519f-107">\<source></span></span>  
<span data-ttu-id="0519f-108">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="0519f-108">\<listeners></span></span>  
<span data-ttu-id="0519f-109">\<add></span><span class="sxs-lookup"><span data-stu-id="0519f-109">\<add></span></span>  
<span data-ttu-id="0519f-110">\<Фильтр ></span><span class="sxs-lookup"><span data-stu-id="0519f-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0519f-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0519f-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0519f-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0519f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0519f-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0519f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0519f-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0519f-114">Attributes</span></span>  
  
|<span data-ttu-id="0519f-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0519f-115">Attribute</span></span>|<span data-ttu-id="0519f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0519f-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0519f-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0519f-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="0519f-118">Указывает тип фильтра, который должен быть производным от <xref:System.Diagnostics.TraceFilter> класса.</span><span class="sxs-lookup"><span data-stu-id="0519f-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="0519f-119">Можно использовать имя с указанием пространства имен типа, который соответствует типу <xref:System.Type.FullName%2A> свойства, или можно использовать полное имя, включая сведения о сборке, которая соответствует <xref:System.Type.AssemblyQualifiedName%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0519f-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="0519f-120">Сведения о полных именах см. в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="0519f-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="0519f-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0519f-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0519f-122">Строка, передаваемая в конструктор для заданного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="0519f-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0519f-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0519f-123">Child Elements</span></span>  
 <span data-ttu-id="0519f-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0519f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0519f-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0519f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0519f-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="0519f-126">Element</span></span>|<span data-ttu-id="0519f-127">Описание</span><span class="sxs-lookup"><span data-stu-id="0519f-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0519f-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0519f-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0519f-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="0519f-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="0519f-130">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="0519f-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="0519f-131">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="0519f-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="0519f-132">Содержит прослушиватели для сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="0519f-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="0519f-133">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="0519f-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="0519f-134">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="0519f-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0519f-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="0519f-135">Remarks</span></span>  
 <span data-ttu-id="0519f-136">`<filter>` Элемент, содержащийся в `<add>` элемент для прослушивателя трассировки источника, задающий тип прослушивателя не только имя прослушивателя, определенное в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="0519f-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="0519f-137">Если прослушиватель определен в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), фильтр для этого прослушивателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="0519f-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="0519f-138">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="0519f-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0519f-139">Пример</span><span class="sxs-lookup"><span data-stu-id="0519f-139">Example</span></span>  
 <span data-ttu-id="0519f-140">В следующем примере показано, как использовать `<filter>` элемент, чтобы добавить фильтр к прослушивателю `console` в `Listeners` коллекции для источника трассировки `myTraceSource`, указав уровень фильтра событий, как `Error`.</span><span class="sxs-lookup"><span data-stu-id="0519f-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0519f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="0519f-141">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="0519f-142">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="0519f-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
