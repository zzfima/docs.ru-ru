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
ms.openlocfilehash: 4e92f80e9f6069b5fa70501e13a55d5a6fe95e7a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697322"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="a8643-102">Элемент \<filter > для > \<Add для \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="a8643-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="a8643-103">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="a8643-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
[<span data-ttu-id="a8643-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a8643-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a8643-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8643-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="a8643-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sharedListeners >** ](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8643-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>  
<span data-ttu-id="a8643-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<add >** ](add-element-for-sharedlisteners.md)</span><span class="sxs-lookup"><span data-stu-id="a8643-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)</span></span>  
<span data-ttu-id="a8643-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<filter >**</span><span class="sxs-lookup"><span data-stu-id="a8643-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8643-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8643-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8643-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8643-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a8643-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a8643-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8643-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8643-112">Attributes</span></span>  
  
|<span data-ttu-id="a8643-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a8643-113">Attribute</span></span>|<span data-ttu-id="a8643-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a8643-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8643-115">**type**</span><span class="sxs-lookup"><span data-stu-id="a8643-115">**type**</span></span>|<span data-ttu-id="a8643-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8643-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="a8643-117">Указывает тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="a8643-117">Specifies the type of the filter.</span></span> <span data-ttu-id="a8643-118">Можно использовать только полное имя типа (в формате свойства <xref:System.Type.FullName%2A?displayProperty=nameWithType>) или можно использовать полное имя типа, включая сведения о сборке (в формате свойства <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="a8643-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="a8643-119">Сведения о создании полного имени типа см. в разделе [Указание полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="a8643-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="a8643-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="a8643-120">**initializeData**</span></span>|<span data-ttu-id="a8643-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8643-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a8643-122">Строка, передаваемая конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="a8643-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8643-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8643-123">Child Elements</span></span>  
 <span data-ttu-id="a8643-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="a8643-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8643-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8643-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a8643-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8643-126">Element</span></span>|<span data-ttu-id="a8643-127">Описание</span><span class="sxs-lookup"><span data-stu-id="a8643-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a8643-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8643-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a8643-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="a8643-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="a8643-130">Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="a8643-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="a8643-131">Добавляет прослушиватель в коллекцию **шаредлистенерс** .</span><span class="sxs-lookup"><span data-stu-id="a8643-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8643-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8643-132">Remarks</span></span>  
 <span data-ttu-id="a8643-133">Если прослушиватель определен в элементе `<add>` элемента `<sharedListeners>`, то фильтр для этого прослушивателя должен быть определен в элементе `<filter>`, который является дочерним по отношению к элементу `<add>`.</span><span class="sxs-lookup"><span data-stu-id="a8643-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="a8643-134">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="a8643-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8643-135">Пример</span><span class="sxs-lookup"><span data-stu-id="a8643-135">Example</span></span>  
 <span data-ttu-id="a8643-136">В следующем примере показано, как использовать элемент `<filter>` для добавления фильтра в прослушиватель трассировки `console` в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="a8643-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8643-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a8643-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="a8643-138">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="a8643-138">Trace and Debug Settings Schema</span></span>](index.md)
