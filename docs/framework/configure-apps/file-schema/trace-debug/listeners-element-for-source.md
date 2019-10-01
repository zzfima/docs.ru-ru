---
title: Элемент <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: d7641611e5d8257b49bc6a6abd0a2fadfde66e91
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697302"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="6b406-102">Элемент > @no__t 0listeners для \<source ></span><span class="sxs-lookup"><span data-stu-id="6b406-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="6b406-103">Добавляет или удаляет прослушиватели в коллекции <xref:System.Diagnostics.TraceSource.Listeners%2A> для <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="6b406-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="6b406-104">Прослушиватель направляет выходные данные трассировки в соответствующий целевой объект, например журнал, окно или текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="6b406-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="6b406-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="6b406-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6b406-106">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b406-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="6b406-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b406-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="6b406-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b406-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="6b406-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<listeners >**</span><span class="sxs-lookup"><span data-stu-id="6b406-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b406-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b406-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b406-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6b406-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6b406-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6b406-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b406-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6b406-113">Attributes</span></span>  
 <span data-ttu-id="6b406-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="6b406-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6b406-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6b406-115">Child Elements</span></span>  
  
|<span data-ttu-id="6b406-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="6b406-116">Element</span></span>|<span data-ttu-id="6b406-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6b406-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b406-118">\<add></span><span class="sxs-lookup"><span data-stu-id="6b406-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="6b406-119">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="6b406-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="6b406-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="6b406-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="6b406-121">Удаляет прослушиватель из коллекции `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="6b406-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="6b406-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="6b406-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="6b406-123">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="6b406-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b406-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6b406-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6b406-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="6b406-125">Element</span></span>|<span data-ttu-id="6b406-126">Описание</span><span class="sxs-lookup"><span data-stu-id="6b406-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6b406-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b406-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6b406-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="6b406-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="6b406-129">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="6b406-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="6b406-130">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="6b406-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b406-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b406-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="6b406-132">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="6b406-132">Configuration File</span></span>  
 <span data-ttu-id="6b406-133">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="6b406-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b406-134">Пример</span><span class="sxs-lookup"><span data-stu-id="6b406-134">Example</span></span>  
 <span data-ttu-id="6b406-135">В следующем примере показано, как использовать элемент `<listeners>`, чтобы добавить прослушиватель трассировки консоли в источник `mySource` и удалить прослушиватель трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b406-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6b406-136">См. также</span><span class="sxs-lookup"><span data-stu-id="6b406-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="6b406-137">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="6b406-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6b406-138">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="6b406-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
