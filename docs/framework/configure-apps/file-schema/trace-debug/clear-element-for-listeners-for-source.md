---
title: '&lt;Очистить&gt; элемент для &lt;прослушиватели&gt; для &lt;источника&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3674b5e8f54735010da901c76b77bd617218891e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47209185"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="129b5-102">&lt;Очистить&gt; элемент для &lt;прослушиватели&gt; для &lt;источника&gt;</span><span class="sxs-lookup"><span data-stu-id="129b5-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="129b5-103">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="129b5-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="129b5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="129b5-104">\<configuration></span></span>  
<span data-ttu-id="129b5-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="129b5-105">\<system.diagnostics></span></span>  
<span data-ttu-id="129b5-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="129b5-106">\<sources></span></span>  
<span data-ttu-id="129b5-107">\<Источник ></span><span class="sxs-lookup"><span data-stu-id="129b5-107">\<source></span></span>  
<span data-ttu-id="129b5-108">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="129b5-108">\<listeners></span></span>  
<span data-ttu-id="129b5-109">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="129b5-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="129b5-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="129b5-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="129b5-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="129b5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="129b5-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="129b5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="129b5-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="129b5-113">Attributes</span></span>  
 <span data-ttu-id="129b5-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="129b5-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="129b5-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="129b5-115">Child Elements</span></span>  
 <span data-ttu-id="129b5-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="129b5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="129b5-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="129b5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="129b5-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="129b5-118">Element</span></span>|<span data-ttu-id="129b5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="129b5-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="129b5-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="129b5-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="129b5-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="129b5-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="129b5-122">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="129b5-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="129b5-123">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="129b5-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="129b5-124">Задает прослушиватели для сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="129b5-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="129b5-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="129b5-125">Remarks</span></span>  
 <span data-ttu-id="129b5-126">`<clear>` Элемент удаляет все прослушиватели `Listeners` коллекции для источника трассировки, включая <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="129b5-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="129b5-127">Можно использовать `<clear>` элемент перед использованием `<add>` элемент, чтобы быть уверенным, отсутствуют другие активные прослушиватели в коллекции.</span><span class="sxs-lookup"><span data-stu-id="129b5-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="129b5-128">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="129b5-128">Configuration File</span></span>  
 <span data-ttu-id="129b5-129">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="129b5-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="129b5-130">Пример</span><span class="sxs-lookup"><span data-stu-id="129b5-130">Example</span></span>  
 <span data-ttu-id="129b5-131">В следующем примере показано, как использовать `<clear>` элемент перед использованием `<add>` элементы для добавления прослушивателей `console` и `textListener` для `Listeners` коллекции для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="129b5-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="129b5-132">См. также</span><span class="sxs-lookup"><span data-stu-id="129b5-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="129b5-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="129b5-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="129b5-134">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="129b5-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
