---
title: Элемент <filter> для <add> для <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 739acedcc83cd207a7ef4c10c220d27695dd713d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269306"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="a81cb-102">\<Фильтр > элемент для \<Добавить > для \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="a81cb-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="a81cb-103">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="a81cb-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="a81cb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a81cb-104">\<configuration></span></span>  
<span data-ttu-id="a81cb-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="a81cb-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a81cb-106">\<sharedListeners > элемент</span><span class="sxs-lookup"><span data-stu-id="a81cb-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="a81cb-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a81cb-107">\<add></span></span>  
<span data-ttu-id="a81cb-108">\<Фильтр ></span><span class="sxs-lookup"><span data-stu-id="a81cb-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a81cb-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a81cb-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a81cb-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a81cb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a81cb-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a81cb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a81cb-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a81cb-112">Attributes</span></span>  
  
|<span data-ttu-id="a81cb-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a81cb-113">Attribute</span></span>|<span data-ttu-id="a81cb-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="a81cb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a81cb-115">**type**</span><span class="sxs-lookup"><span data-stu-id="a81cb-115">**type**</span></span>|<span data-ttu-id="a81cb-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a81cb-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="a81cb-117">Указывает тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="a81cb-117">Specifies the type of the filter.</span></span> <span data-ttu-id="a81cb-118">Можно использовать только полное имя типа (в формате <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойство), или можно использовать имя полное имя типа, включая сведения о сборке (в формате <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> свойство).</span><span class="sxs-lookup"><span data-stu-id="a81cb-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="a81cb-119">Сведения о создании полное имя типа, см. в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="a81cb-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="a81cb-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="a81cb-120">**initializeData**</span></span>|<span data-ttu-id="a81cb-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a81cb-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a81cb-122">Строка, передаваемая в конструктор для заданного класса.</span><span class="sxs-lookup"><span data-stu-id="a81cb-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a81cb-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a81cb-123">Child Elements</span></span>  
 <span data-ttu-id="a81cb-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a81cb-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a81cb-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a81cb-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a81cb-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="a81cb-126">Element</span></span>|<span data-ttu-id="a81cb-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="a81cb-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a81cb-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a81cb-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a81cb-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="a81cb-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="a81cb-130">Коллекция прослушивателей, которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="a81cb-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="a81cb-131">Добавляет прослушиватель **sharedListeners** коллекции.</span><span class="sxs-lookup"><span data-stu-id="a81cb-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a81cb-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="a81cb-132">Remarks</span></span>  
 <span data-ttu-id="a81cb-133">Если прослушиватель определен в `<add>` элемент `<sharedListeners>` элемент, фильтр для этого прослушивателя, должен быть определен в `<filter>` элемент, который является дочерним объектом `<add>` элемент.</span><span class="sxs-lookup"><span data-stu-id="a81cb-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="a81cb-134">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="a81cb-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a81cb-135">Пример</span><span class="sxs-lookup"><span data-stu-id="a81cb-135">Example</span></span>  
 <span data-ttu-id="a81cb-136">В следующем примере показано, как использовать `<filter>` элемент, чтобы добавить фильтр к прослушивателю трассировки `console` в `sharedListeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="a81cb-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a81cb-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a81cb-137">See also</span></span>
- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="a81cb-138">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="a81cb-138">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
