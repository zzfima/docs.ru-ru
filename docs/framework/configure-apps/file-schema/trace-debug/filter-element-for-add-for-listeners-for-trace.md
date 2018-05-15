---
title: '&lt;Фильтр&gt; элемент для &lt;добавить&gt; для &lt;прослушиватели&gt; для &lt;трассировки&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 095212f73adb906d9d80db747c331c436c1cf846
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="d36c1-102">&lt;Фильтр&gt; элемент для &lt;добавить&gt; для &lt;прослушиватели&gt; для &lt;трассировки&gt;</span><span class="sxs-lookup"><span data-stu-id="d36c1-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="d36c1-103">Добавляет фильтр в прослушиватель в `Listeners` сбор данных для трассировки.</span><span class="sxs-lookup"><span data-stu-id="d36c1-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="d36c1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d36c1-104">\<configuration></span></span>  
<span data-ttu-id="d36c1-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="d36c1-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d36c1-106">\<трассировки ></span><span class="sxs-lookup"><span data-stu-id="d36c1-106">\<trace></span></span>  
<span data-ttu-id="d36c1-107">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="d36c1-107">\<listeners></span></span>  
<span data-ttu-id="d36c1-108">\<add></span><span class="sxs-lookup"><span data-stu-id="d36c1-108">\<add></span></span>  
<span data-ttu-id="d36c1-109">\<Фильтр ></span><span class="sxs-lookup"><span data-stu-id="d36c1-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36c1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d36c1-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d36c1-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d36c1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d36c1-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d36c1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d36c1-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d36c1-113">Attributes</span></span>  
  
|<span data-ttu-id="d36c1-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d36c1-114">Attribute</span></span>|<span data-ttu-id="d36c1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d36c1-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d36c1-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d36c1-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="d36c1-117">Указывает тип фильтра, который должен быть производным от <xref:System.Diagnostics.TraceFilter> класса.</span><span class="sxs-lookup"><span data-stu-id="d36c1-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="d36c1-118">Можно использовать имя с указанием пространства имен типа, который соответствует типу <xref:System.Type.FullName%2A> свойства, или можно использовать полное имя, включая сведения о сборке, которая соответствует <xref:System.Type.AssemblyQualifiedName%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d36c1-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="d36c1-119">Сведения о полных именах см. в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="d36c1-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="d36c1-120">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d36c1-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d36c1-121">Строка, передаваемая в конструктор для заданного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="d36c1-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d36c1-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d36c1-122">Child Elements</span></span>  
 <span data-ttu-id="d36c1-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d36c1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d36c1-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d36c1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d36c1-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="d36c1-125">Element</span></span>|<span data-ttu-id="d36c1-126">Описание</span><span class="sxs-lookup"><span data-stu-id="d36c1-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d36c1-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d36c1-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d36c1-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="d36c1-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="d36c1-129">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="d36c1-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d36c1-130">Содержит прослушиватели для сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="d36c1-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="d36c1-131">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="d36c1-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="d36c1-132">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="d36c1-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d36c1-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="d36c1-133">Remarks</span></span>  
 <span data-ttu-id="d36c1-134">`<filter>` Элемент, содержащийся в `<add>` элемент для прослушивателя трассировки, который указывает тип прослушивателя не только имя прослушивателя, определенное в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="d36c1-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="d36c1-135">Если прослушиватель определен в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), фильтр для этого прослушивателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="d36c1-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="d36c1-136">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d36c1-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d36c1-137">Пример</span><span class="sxs-lookup"><span data-stu-id="d36c1-137">Example</span></span>  
 <span data-ttu-id="d36c1-138">В следующем примере показано, как использовать `<filter>` элемент, чтобы добавить фильтр к прослушивателю `console` в `Listeners` сбор данных для трассировки с заданием уровня событий фильтра как `Error`.</span><span class="sxs-lookup"><span data-stu-id="d36c1-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d36c1-139">См. также</span><span class="sxs-lookup"><span data-stu-id="d36c1-139">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [<span data-ttu-id="d36c1-140">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="d36c1-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
