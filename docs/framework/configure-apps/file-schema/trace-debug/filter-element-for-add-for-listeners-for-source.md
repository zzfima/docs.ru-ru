---
title: <filter>Элемент <add> для <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0cb668782de263d5f784691f46cb8b74541d942b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153520"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="53c2e-102">\<фильтр> \<элемент амва для добавления> для \<слушателей> для \<исходных></span><span class="sxs-lookup"><span data-stu-id="53c2e-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="53c2e-103">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="53c2e-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="53c2e-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="53c2e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="53c2e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<источники>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="53c2e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<источник>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="53c2e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="53c2e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>\
<span data-ttu-id="53c2e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<фильтр>**</span><span class="sxs-lookup"><span data-stu-id="53c2e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="53c2e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53c2e-111">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53c2e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="53c2e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="53c2e-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="53c2e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53c2e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="53c2e-114">Attributes</span></span>  
  
|<span data-ttu-id="53c2e-115">attribute</span><span class="sxs-lookup"><span data-stu-id="53c2e-115">Attribute</span></span>|<span data-ttu-id="53c2e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="53c2e-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="53c2e-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="53c2e-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="53c2e-118">Определяет тип фильтра, который должен наследовать <xref:System.Diagnostics.TraceFilter> сяокласс.</span><span class="sxs-lookup"><span data-stu-id="53c2e-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="53c2e-119">Вы можете использовать имя, квалифицированное для имени типа, которое соответствует <xref:System.Type.FullName%2A> свойству типа, или вы можете использовать полностью <xref:System.Type.AssemblyQualifiedName%2A> квалифицированное имя типа, включая информацию о сборке, которая соответствует свойству.</span><span class="sxs-lookup"><span data-stu-id="53c2e-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="53c2e-120">Для получения информации о полностью квалифицированных именах типов [см.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="53c2e-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="53c2e-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="53c2e-122">Строка перешла к конструктору для указанного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="53c2e-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53c2e-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="53c2e-123">Child Elements</span></span>  
 <span data-ttu-id="53c2e-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="53c2e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53c2e-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="53c2e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="53c2e-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="53c2e-126">Element</span></span>|<span data-ttu-id="53c2e-127">Описание</span><span class="sxs-lookup"><span data-stu-id="53c2e-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="53c2e-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="53c2e-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="53c2e-129">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="53c2e-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="53c2e-130">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="53c2e-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="53c2e-131">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="53c2e-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="53c2e-132">Содержит слушателей, которые собирают, хранят и направляют сообщения.</span><span class="sxs-lookup"><span data-stu-id="53c2e-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="53c2e-133">Слушатели направляют результаты отслеживания на соответствующую цель.</span><span class="sxs-lookup"><span data-stu-id="53c2e-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="53c2e-134">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="53c2e-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53c2e-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="53c2e-135">Remarks</span></span>  
 <span data-ttu-id="53c2e-136">Элемент `<filter>` должен содержаться `<add>` в элементе для слушателя источника трассировки, который определяет тип слушателя, а не только имя слушателя, определенного в [ \<общей>Слушатела. ](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="53c2e-137">Если слушатель определен в [ \<общей>Слушателя, ](sharedlisteners-element.md)фильтр для этого слушателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="53c2e-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="53c2e-138">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="53c2e-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53c2e-139">Пример</span><span class="sxs-lookup"><span data-stu-id="53c2e-139">Example</span></span>  
 <span data-ttu-id="53c2e-140">В следующем примере показано, как использовать `<filter>` элемент для `console` добавления фильтра к слушателю в `Listeners` сборе для источника `myTraceSource`трассировки, указывая уровень события фильтра как. `Error`</span><span class="sxs-lookup"><span data-stu-id="53c2e-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="53c2e-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="53c2e-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="53c2e-142">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="53c2e-142">Trace and Debug Settings Schema</span></span>](index.md)
