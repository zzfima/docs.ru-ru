---
title: Элемент <filter> для <add> <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: cc970240ac07ad3ea72be50d1e9af452da638fa9
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088891"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="62921-102">\<> элемент фильтра для \<Добавить > для \<трассировки ></span><span class="sxs-lookup"><span data-stu-id="62921-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="62921-103">Добавляет фильтр к прослушивателю в коллекции `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="62921-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="62921-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="62921-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="62921-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="62921-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="62921-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trace**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="62921-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="62921-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**прослушиватели**](listeners-element-for-trace.md) ></span><span class="sxs-lookup"><span data-stu-id="62921-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="62921-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<добавить >** ](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="62921-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="62921-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filter >**</span><span class="sxs-lookup"><span data-stu-id="62921-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="62921-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62921-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62921-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="62921-111">Attributes and Elements</span></span>  
 <span data-ttu-id="62921-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="62921-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62921-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="62921-113">Attributes</span></span>  
  
|<span data-ttu-id="62921-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="62921-114">Attribute</span></span>|<span data-ttu-id="62921-115">Описание</span><span class="sxs-lookup"><span data-stu-id="62921-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="62921-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="62921-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="62921-117">Указывает тип фильтра, который должен наследовать от класса <xref:System.Diagnostics.TraceFilter>.</span><span class="sxs-lookup"><span data-stu-id="62921-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="62921-118">Можно использовать имя типа, уточненное пространством имен, которое соответствует свойству <xref:System.Type.FullName%2A> типа, или можно использовать полное имя типа, включая сведения о сборке, соответствующие свойству <xref:System.Type.AssemblyQualifiedName%2A>.</span><span class="sxs-lookup"><span data-stu-id="62921-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="62921-119">Дополнительные сведения о полных именах типов см. в разделе Указание полных [имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="62921-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="62921-120">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="62921-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="62921-121">Строка, передаваемая конструктору для указанного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="62921-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62921-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="62921-122">Child Elements</span></span>  
 <span data-ttu-id="62921-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="62921-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62921-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="62921-124">Parent Elements</span></span>  
  
|<span data-ttu-id="62921-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="62921-125">Element</span></span>|<span data-ttu-id="62921-126">Описание</span><span class="sxs-lookup"><span data-stu-id="62921-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="62921-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="62921-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="62921-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="62921-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="62921-129">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="62921-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="62921-130">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="62921-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="62921-131">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="62921-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="62921-132">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="62921-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62921-133">Заметки</span><span class="sxs-lookup"><span data-stu-id="62921-133">Remarks</span></span>  
 <span data-ttu-id="62921-134">Элемент `<filter>` должен содержаться в элементе `<add>` для прослушивателя трассировки, который указывает тип прослушивателя, а не только имя прослушивателя, определенного в [\<шаредлистенерс >](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="62921-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="62921-135">Если прослушиватель определен в [\<е > шаредлистенерс](sharedlisteners-element.md), то фильтр для этого прослушивателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="62921-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="62921-136">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="62921-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62921-137">Пример</span><span class="sxs-lookup"><span data-stu-id="62921-137">Example</span></span>  
 <span data-ttu-id="62921-138">В следующем примере показано, как использовать элемент `<filter>`, чтобы добавить фильтр в `console` прослушивателя в коллекции `Listeners` для трассировки, указав уровень событий фильтра `Error`.</span><span class="sxs-lookup"><span data-stu-id="62921-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62921-139">См. также</span><span class="sxs-lookup"><span data-stu-id="62921-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="62921-140">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="62921-140">Trace and Debug Settings Schema</span></span>](index.md)
