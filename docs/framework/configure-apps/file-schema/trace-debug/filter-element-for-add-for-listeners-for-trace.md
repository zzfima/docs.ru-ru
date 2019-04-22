---
title: <filter> Элемент для <add> для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: 5961125e1b8d0d0f5711f8b942b68ba71d61888f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143433"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="e339f-102">\<Фильтр > элемент для \<Добавить > для \<прослушиватели > для \<трассировки ></span><span class="sxs-lookup"><span data-stu-id="e339f-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="e339f-103">Добавляет фильтр к прослушивателю в `Listeners` коллекции трассировки.</span><span class="sxs-lookup"><span data-stu-id="e339f-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="e339f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e339f-104">\<configuration></span></span>  
<span data-ttu-id="e339f-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="e339f-105">\<system.diagnostics></span></span>  
<span data-ttu-id="e339f-106">\<трассировки ></span><span class="sxs-lookup"><span data-stu-id="e339f-106">\<trace></span></span>  
<span data-ttu-id="e339f-107">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="e339f-107">\<listeners></span></span>  
<span data-ttu-id="e339f-108">\<add></span><span class="sxs-lookup"><span data-stu-id="e339f-108">\<add></span></span>  
<span data-ttu-id="e339f-109">\<Фильтр ></span><span class="sxs-lookup"><span data-stu-id="e339f-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e339f-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e339f-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e339f-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e339f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e339f-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e339f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e339f-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e339f-113">Attributes</span></span>  
  
|<span data-ttu-id="e339f-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e339f-114">Attribute</span></span>|<span data-ttu-id="e339f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e339f-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e339f-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e339f-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e339f-117">Указывает тип фильтра, который должен быть производным от <xref:System.Diagnostics.TraceFilter> класса.</span><span class="sxs-lookup"><span data-stu-id="e339f-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="e339f-118">Можно использовать имя с указанием пространства имен типа, который соответствует типу <xref:System.Type.FullName%2A> свойство, или можно использовать полное имя, включая сведения о сборке, которая соответствует <xref:System.Type.AssemblyQualifiedName%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e339f-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="e339f-119">Сведения о полных имен типов, см. в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e339f-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="e339f-120">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e339f-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e339f-121">Строка, передаваемая в конструктор для заданного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="e339f-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e339f-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e339f-122">Child Elements</span></span>  
 <span data-ttu-id="e339f-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e339f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e339f-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e339f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e339f-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="e339f-125">Element</span></span>|<span data-ttu-id="e339f-126">Описание</span><span class="sxs-lookup"><span data-stu-id="e339f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e339f-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e339f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e339f-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="e339f-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="e339f-129">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="e339f-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e339f-130">Содержит прослушиватели, сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="e339f-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="e339f-131">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="e339f-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="e339f-132">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="e339f-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e339f-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="e339f-133">Remarks</span></span>  
 <span data-ttu-id="e339f-134">`<filter>` Элемент должен быть включен в `<add>` элемент для прослушивателя трассировки, которое указывает тип прослушивателя не только имя прослушивателя, определенное в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="e339f-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="e339f-135">Если прослушиватель определен в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), фильтр для этого прослушивателя, должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="e339f-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="e339f-136">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e339f-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e339f-137">Пример</span><span class="sxs-lookup"><span data-stu-id="e339f-137">Example</span></span>  
 <span data-ttu-id="e339f-138">В следующем примере показано, как использовать `<filter>` элемент, чтобы добавить фильтр к прослушивателю `console` в `Listeners` коллекции для трассировки, указывающие уровень фильтра событий как `Error`.</span><span class="sxs-lookup"><span data-stu-id="e339f-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e339f-139">См. также</span><span class="sxs-lookup"><span data-stu-id="e339f-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="e339f-140">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="e339f-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
