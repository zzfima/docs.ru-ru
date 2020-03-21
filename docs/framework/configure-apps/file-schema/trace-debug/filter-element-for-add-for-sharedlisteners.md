---
title: <filter>Элемент <add> для<sharedListeners>
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
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153457"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="67c64-102">\<фильтр> \<элемент амва для добавления> для \<> общей слушателей</span><span class="sxs-lookup"><span data-stu-id="67c64-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="67c64-103">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="67c64-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

<span data-ttu-id="67c64-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="67c64-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="67c64-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="67c64-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="67c64-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<общиеслушатели>**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="67c64-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="67c64-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add-element-for-sharedlisteners.md)</span><span class="sxs-lookup"><span data-stu-id="67c64-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)</span></span>\
<span data-ttu-id="67c64-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<фильтр>**</span><span class="sxs-lookup"><span data-stu-id="67c64-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="67c64-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67c64-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67c64-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="67c64-110">Attributes and Elements</span></span>  
 <span data-ttu-id="67c64-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="67c64-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67c64-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67c64-112">Attributes</span></span>  
  
|<span data-ttu-id="67c64-113">attribute</span><span class="sxs-lookup"><span data-stu-id="67c64-113">Attribute</span></span>|<span data-ttu-id="67c64-114">Описание</span><span class="sxs-lookup"><span data-stu-id="67c64-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67c64-115">**тип**</span><span class="sxs-lookup"><span data-stu-id="67c64-115">**type**</span></span>|<span data-ttu-id="67c64-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="67c64-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="67c64-117">Определяет тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="67c64-117">Specifies the type of the filter.</span></span> <span data-ttu-id="67c64-118">Вы можете использовать только полное имя типа (в формате <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойства), или вы можете использовать полностью квалифицированное имя типа, включая информацию о сборке (в формате <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> свойства).</span><span class="sxs-lookup"><span data-stu-id="67c64-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="67c64-119">Для получения информации о создании полностью квалифицированного имени типа [см.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span><span class="sxs-lookup"><span data-stu-id="67c64-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="67c64-120">**инициализацияДанны**</span><span class="sxs-lookup"><span data-stu-id="67c64-120">**initializeData**</span></span>|<span data-ttu-id="67c64-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="67c64-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="67c64-122">Строка перешла к конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="67c64-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67c64-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="67c64-123">Child Elements</span></span>  
 <span data-ttu-id="67c64-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="67c64-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67c64-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="67c64-125">Parent Elements</span></span>  
  
|<span data-ttu-id="67c64-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="67c64-126">Element</span></span>|<span data-ttu-id="67c64-127">Описание</span><span class="sxs-lookup"><span data-stu-id="67c64-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="67c64-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="67c64-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="67c64-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="67c64-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="67c64-130">Коллекция слушателей, на которую может ссылаться любой источник или элемент микро- информации.</span><span class="sxs-lookup"><span data-stu-id="67c64-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="67c64-131">Добавляет слушателя в коллекцию **sharedListeners.**</span><span class="sxs-lookup"><span data-stu-id="67c64-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c64-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="67c64-132">Remarks</span></span>  
 <span data-ttu-id="67c64-133">Если слушатель определен в `<add>` элементе `<sharedListeners>` элемента, фильтр для этого слушателя `<filter>` должен быть определен `<add>` в элементе, который является ребенком элемента.</span><span class="sxs-lookup"><span data-stu-id="67c64-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="67c64-134">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="67c64-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67c64-135">Пример</span><span class="sxs-lookup"><span data-stu-id="67c64-135">Example</span></span>  
 <span data-ttu-id="67c64-136">В следующем примере показано, как использовать `<filter>` элемент для `console` добавления фильтра к слушателю трассировки в коллекции. `sharedListeners`</span><span class="sxs-lookup"><span data-stu-id="67c64-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="67c64-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="67c64-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="67c64-138">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="67c64-138">Trace and Debug Settings Schema</span></span>](index.md)
