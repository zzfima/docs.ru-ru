---
title: '&lt;прослушиватели&gt; элемент для &lt;трассировки&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: bfcf96c553f85aeb0a40dfd6ea36667d504e8eee
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47172840"
---
# <a name="ltlistenersgt-element-for-lttracegt"></a><span data-ttu-id="ad583-102">&lt;прослушиватели&gt; элемент для &lt;трассировки&gt;</span><span class="sxs-lookup"><span data-stu-id="ad583-102">&lt;listeners&gt; Element for &lt;trace&gt;</span></span>
<span data-ttu-id="ad583-103">Указывает прослушиватель, который собирает, хранилищ и направляет сообщения.</span><span class="sxs-lookup"><span data-stu-id="ad583-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="ad583-104">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="ad583-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="ad583-105">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="ad583-105">\<configuration> Element</span></span>  
<span data-ttu-id="ad583-106">\<System.Diagnostics > элемент</span><span class="sxs-lookup"><span data-stu-id="ad583-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="ad583-107">\<трассировки > элемент</span><span class="sxs-lookup"><span data-stu-id="ad583-107">\<trace> Element</span></span>  
<span data-ttu-id="ad583-108">\<прослушиватели > элемент для \<трассировки ></span><span class="sxs-lookup"><span data-stu-id="ad583-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad583-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad583-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad583-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ad583-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ad583-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ad583-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad583-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad583-112">Attributes</span></span>  
 <span data-ttu-id="ad583-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ad583-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad583-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad583-114">Child Elements</span></span>  
  
|<span data-ttu-id="ad583-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad583-115">Element</span></span>|<span data-ttu-id="ad583-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ad583-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad583-117">\<add></span><span class="sxs-lookup"><span data-stu-id="ad583-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="ad583-118">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="ad583-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="ad583-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="ad583-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="ad583-120">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ad583-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="ad583-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="ad583-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="ad583-122">Удаляет прослушиватель из `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="ad583-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad583-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad583-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ad583-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad583-124">Element</span></span>|<span data-ttu-id="ad583-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ad583-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ad583-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad583-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ad583-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ad583-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="ad583-128">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ad583-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad583-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad583-129">Remarks</span></span>  
 <span data-ttu-id="ad583-130"><xref:System.Diagnostics.Debug> И <xref:System.Diagnostics.Trace> классы одного и того же **прослушиватели** коллекции.</span><span class="sxs-lookup"><span data-stu-id="ad583-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="ad583-131">Если добавить объект прослушивателя в коллекцию в одном из этих классов, другой класс использует этот же прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="ad583-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="ad583-132">Классы прослушивателя, поставлявшихся с .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="ad583-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ad583-133">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="ad583-133">Configuration File</span></span>  
 <span data-ttu-id="ad583-134">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="ad583-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad583-135">Пример</span><span class="sxs-lookup"><span data-stu-id="ad583-135">Example</span></span>  
 <span data-ttu-id="ad583-136">В следующем примере показано, как использовать  **\<прослушиватели >** элемент для добавления прослушивателей `MyListener` и `MyEventListener` для **прослушиватели** коллекции.</span><span class="sxs-lookup"><span data-stu-id="ad583-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="ad583-137">`MyListener` Создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="ad583-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="ad583-138">`MyEventListener` создает запись в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="ad583-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad583-139">См. также</span><span class="sxs-lookup"><span data-stu-id="ad583-139">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="ad583-140">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="ad583-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
