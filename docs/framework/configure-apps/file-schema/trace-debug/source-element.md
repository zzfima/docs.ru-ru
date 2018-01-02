---
title: "&lt;источник&gt; элемент"
ms.date: 09/29/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d6c5c65be8a540fdbba64d5a604c0963f9797e0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsourcegt-element"></a><span data-ttu-id="4e78d-102">&lt;источник&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="4e78d-102">&lt;source&gt; Element</span></span>
<span data-ttu-id="4e78d-103">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="4e78d-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="4e78d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4e78d-104">\<configuration></span></span>  
<span data-ttu-id="4e78d-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="4e78d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4e78d-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="4e78d-106">\<sources></span></span>  
<span data-ttu-id="4e78d-107">\<Источник ></span><span class="sxs-lookup"><span data-stu-id="4e78d-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e78d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e78d-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e78d-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4e78d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4e78d-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4e78d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e78d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4e78d-111">Attributes</span></span>  
  
|<span data-ttu-id="4e78d-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4e78d-112">Attribute</span></span>|<span data-ttu-id="4e78d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4e78d-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="4e78d-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4e78d-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4e78d-115">Задает имя источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="4e78d-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="4e78d-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4e78d-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4e78d-117">Задает имя экземпляра коммутатора трассировки в приложении.</span><span class="sxs-lookup"><span data-stu-id="4e78d-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="4e78d-118">Если параметр не указан в `<switches>` элемент, значение задает уровень для переключателя.</span><span class="sxs-lookup"><span data-stu-id="4e78d-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="4e78d-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4e78d-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4e78d-120">Указывает тип переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="4e78d-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="4e78d-121">Если он имеется, тип должен быть допустимым именем класса и не может быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="4e78d-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="4e78d-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4e78d-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4e78d-123">Указывает значение для атрибута каждого источника трассировки, определяется <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> метода для этого источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="4e78d-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e78d-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4e78d-124">Child Elements</span></span>  
  
|<span data-ttu-id="4e78d-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e78d-125">Element</span></span>|<span data-ttu-id="4e78d-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="4e78d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e78d-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="4e78d-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="4e78d-128">Содержит прослушиватели для сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="4e78d-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e78d-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4e78d-129">Parent Elements</span></span>  
  
|<span data-ttu-id="4e78d-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e78d-130">Element</span></span>|<span data-ttu-id="4e78d-131">Описание</span><span class="sxs-lookup"><span data-stu-id="4e78d-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4e78d-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4e78d-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4e78d-133">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="4e78d-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4e78d-134">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="4e78d-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e78d-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e78d-135">Remarks</span></span>  
 <span data-ttu-id="4e78d-136">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4e78d-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e78d-137">Пример</span><span class="sxs-lookup"><span data-stu-id="4e78d-137">Example</span></span>  
 <span data-ttu-id="4e78d-138">В следующем примере показано, как использовать `<source>` элемента для добавления источника трассировки `mySource` и задать уровень для переключателя источника с именем `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="4e78d-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="4e78d-139">Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="4e78d-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e78d-140">См. также</span><span class="sxs-lookup"><span data-stu-id="4e78d-140">See Also</span></span>  
 [<span data-ttu-id="4e78d-141">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="4e78d-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="4e78d-142">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="4e78d-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
