---
title: '&lt;прослушиватели&gt; элемент для &lt;источника&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 86b85779f4eff72e8ab910a5ccd32fd369270509
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399012"
---
# <a name="ltlistenersgt-element-for-ltsourcegt"></a><span data-ttu-id="c8d09-102">&lt;прослушиватели&gt; элемент для &lt;источника&gt;</span><span class="sxs-lookup"><span data-stu-id="c8d09-102">&lt;listeners&gt; Element for &lt;source&gt;</span></span>
<span data-ttu-id="c8d09-103">Добавляет или удаляет прослушиватели в <xref:System.Diagnostics.TraceSource.Listeners%2A> коллекции для <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="c8d09-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="c8d09-104">Прослушиватель направляет данные трассировки соответствующему целевому объекту, например журнал, окно или текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="c8d09-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="c8d09-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c8d09-105">\<configuration></span></span>  
<span data-ttu-id="c8d09-106">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="c8d09-106">\<system.diagnostics></span></span>  
<span data-ttu-id="c8d09-107">\<источники ></span><span class="sxs-lookup"><span data-stu-id="c8d09-107">\<sources></span></span>  
<span data-ttu-id="c8d09-108">\<Источник ></span><span class="sxs-lookup"><span data-stu-id="c8d09-108">\<source></span></span>  
<span data-ttu-id="c8d09-109">\<прослушиватели > элемент</span><span class="sxs-lookup"><span data-stu-id="c8d09-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d09-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8d09-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8d09-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c8d09-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c8d09-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c8d09-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8d09-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8d09-113">Attributes</span></span>  
 <span data-ttu-id="c8d09-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c8d09-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c8d09-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8d09-115">Child Elements</span></span>  
  
|<span data-ttu-id="c8d09-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8d09-116">Element</span></span>|<span data-ttu-id="c8d09-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c8d09-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8d09-118">\<add></span><span class="sxs-lookup"><span data-stu-id="c8d09-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="c8d09-119">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="c8d09-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="c8d09-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="c8d09-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="c8d09-121">Удаляет прослушиватель из `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="c8d09-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="c8d09-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="c8d09-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="c8d09-123">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="c8d09-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8d09-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c8d09-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c8d09-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8d09-125">Element</span></span>|<span data-ttu-id="c8d09-126">Описание</span><span class="sxs-lookup"><span data-stu-id="c8d09-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c8d09-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8d09-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c8d09-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="c8d09-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="c8d09-129">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="c8d09-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="c8d09-130">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="c8d09-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8d09-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8d09-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c8d09-132">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="c8d09-132">Configuration File</span></span>  
 <span data-ttu-id="c8d09-133">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="c8d09-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8d09-134">Пример</span><span class="sxs-lookup"><span data-stu-id="c8d09-134">Example</span></span>  
 <span data-ttu-id="c8d09-135">В следующем примере показано, как использовать `<listeners>` элемент, чтобы добавить прослушиватель трассировки консоли `mySource` источника и удалить прослушиватель трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c8d09-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8d09-136">См. также</span><span class="sxs-lookup"><span data-stu-id="c8d09-136">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="c8d09-137">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="c8d09-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="c8d09-138">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="c8d09-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
