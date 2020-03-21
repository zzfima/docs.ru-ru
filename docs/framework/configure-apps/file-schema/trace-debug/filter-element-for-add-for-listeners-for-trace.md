---
title: <filter>Элемент <add> для <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153470"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="73c83-102">\<фильтр> \<элемент для \<добавления> для слушателей> для \<> трассировки</span><span class="sxs-lookup"><span data-stu-id="73c83-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="73c83-103">Добавляет фильтр слушателю в `Listeners` коллекцию для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="73c83-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="73c83-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73c83-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73c83-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="73c83-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="73c83-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<след>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="73c83-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="73c83-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="73c83-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="73c83-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="73c83-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="73c83-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<фильтр>**</span><span class="sxs-lookup"><span data-stu-id="73c83-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="73c83-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73c83-110">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73c83-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73c83-111">Attributes and Elements</span></span>  
 <span data-ttu-id="73c83-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73c83-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73c83-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73c83-113">Attributes</span></span>  
  
|<span data-ttu-id="73c83-114">attribute</span><span class="sxs-lookup"><span data-stu-id="73c83-114">Attribute</span></span>|<span data-ttu-id="73c83-115">Описание</span><span class="sxs-lookup"><span data-stu-id="73c83-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="73c83-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="73c83-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="73c83-117">Определяет тип фильтра, который должен наследовать <xref:System.Diagnostics.TraceFilter> сяокласс.</span><span class="sxs-lookup"><span data-stu-id="73c83-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="73c83-118">Вы можете использовать имя, квалифицированное для имени типа, которое соответствует <xref:System.Type.FullName%2A> свойству типа, или вы можете использовать полностью <xref:System.Type.AssemblyQualifiedName%2A> квалифицированное имя типа, включая информацию о сборке, которая соответствует свойству.</span><span class="sxs-lookup"><span data-stu-id="73c83-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="73c83-119">Для получения информации о полностью квалифицированных именах типов [см.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span><span class="sxs-lookup"><span data-stu-id="73c83-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="73c83-120">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="73c83-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="73c83-121">Строка перешла к конструктору для указанного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="73c83-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73c83-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73c83-122">Child Elements</span></span>  
 <span data-ttu-id="73c83-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="73c83-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73c83-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73c83-124">Parent Elements</span></span>  
  
|<span data-ttu-id="73c83-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="73c83-125">Element</span></span>|<span data-ttu-id="73c83-126">Описание</span><span class="sxs-lookup"><span data-stu-id="73c83-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="73c83-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73c83-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="73c83-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="73c83-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="73c83-129">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="73c83-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="73c83-130">Содержит слушателей, которые собирают, хранят и направляют сообщения.</span><span class="sxs-lookup"><span data-stu-id="73c83-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="73c83-131">Слушатели направляют результаты отслеживания на соответствующую цель.</span><span class="sxs-lookup"><span data-stu-id="73c83-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="73c83-132">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="73c83-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73c83-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="73c83-133">Remarks</span></span>  
 <span data-ttu-id="73c83-134">Элемент `<filter>` должен содержаться `<add>` в элементе для слушателя трассировки, который определяет тип слушателя, а не только имя слушателя, определенного в [ \<общей>. ](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="73c83-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="73c83-135">Если слушатель определен в [ \<общей>Слушателя, ](sharedlisteners-element.md)фильтр для этого слушателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="73c83-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="73c83-136">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="73c83-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73c83-137">Пример</span><span class="sxs-lookup"><span data-stu-id="73c83-137">Example</span></span>  
 <span data-ttu-id="73c83-138">В следующем примере показано, как `<filter>` использовать элемент для `console` добавления фильтра для отслеживания фильтра в `Listeners` коллекции, указывая уровень события фильтра как. `Error`</span><span class="sxs-lookup"><span data-stu-id="73c83-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73c83-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="73c83-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="73c83-140">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="73c83-140">Trace and Debug Settings Schema</span></span>](index.md)
