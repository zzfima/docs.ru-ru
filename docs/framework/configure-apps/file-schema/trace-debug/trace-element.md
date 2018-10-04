---
title: '&lt;трассировки&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 55a7eb431432b67b3252853d14bf93be304ee883
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780821"
---
# <a name="lttracegt-element"></a><span data-ttu-id="161c1-102">&lt;трассировки&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="161c1-102">&lt;trace&gt; Element</span></span>
<span data-ttu-id="161c1-103">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="161c1-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="161c1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="161c1-104">\<configuration></span></span>  
<span data-ttu-id="161c1-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="161c1-105">\<system.diagnostics></span></span>  
<span data-ttu-id="161c1-106">\<трассировки ></span><span class="sxs-lookup"><span data-stu-id="161c1-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="161c1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="161c1-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="161c1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="161c1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="161c1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="161c1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="161c1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="161c1-110">Attributes</span></span>  
  
|<span data-ttu-id="161c1-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="161c1-111">Attribute</span></span>|<span data-ttu-id="161c1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="161c1-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="161c1-113">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="161c1-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="161c1-114">Указывает ли прослушиватели трассировки автоматически очистку буфера после каждой операции записи.</span><span class="sxs-lookup"><span data-stu-id="161c1-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="161c1-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="161c1-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="161c1-116">Задает количество пробелов для отступа.</span><span class="sxs-lookup"><span data-stu-id="161c1-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="161c1-117">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="161c1-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="161c1-118">Указывает, следует ли использовать глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="161c1-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="161c1-119">AutoFlush атрибут</span><span class="sxs-lookup"><span data-stu-id="161c1-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="161c1-120">Значение</span><span class="sxs-lookup"><span data-stu-id="161c1-120">Value</span></span>|<span data-ttu-id="161c1-121">Описание</span><span class="sxs-lookup"><span data-stu-id="161c1-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="161c1-122">Не очищает автоматически выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="161c1-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="161c1-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="161c1-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="161c1-124">Автоматически очищает выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="161c1-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="161c1-125">useGlobalLock атрибут</span><span class="sxs-lookup"><span data-stu-id="161c1-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="161c1-126">Значение</span><span class="sxs-lookup"><span data-stu-id="161c1-126">Value</span></span>|<span data-ttu-id="161c1-127">Описание</span><span class="sxs-lookup"><span data-stu-id="161c1-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="161c1-128">Не использовать глобальную блокировку, если прослушиватель является потокобезопасным; в противном случае использует глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="161c1-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="161c1-129">Использует глобальную блокировку, независимо от того, является ли прослушиватель потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="161c1-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="161c1-130">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="161c1-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="161c1-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="161c1-131">Child Elements</span></span>  
  
|<span data-ttu-id="161c1-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="161c1-132">Element</span></span>|<span data-ttu-id="161c1-133">Описание</span><span class="sxs-lookup"><span data-stu-id="161c1-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="161c1-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="161c1-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="161c1-135">Указывает прослушиватель, который собирает, хранилищ и направляет сообщения.</span><span class="sxs-lookup"><span data-stu-id="161c1-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="161c1-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="161c1-136">Parent Elements</span></span>  
  
|<span data-ttu-id="161c1-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="161c1-137">Element</span></span>|<span data-ttu-id="161c1-138">Описание</span><span class="sxs-lookup"><span data-stu-id="161c1-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="161c1-139">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="161c1-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="161c1-140">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="161c1-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="161c1-141">Пример</span><span class="sxs-lookup"><span data-stu-id="161c1-141">Example</span></span>  
 <span data-ttu-id="161c1-142">В следующем примере показано, как использовать `<trace>` элемент, чтобы добавить прослушиватель `MyListener` для `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="161c1-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="161c1-143">`MyListener` Создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="161c1-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="161c1-144">`useGlobalLock` Атрибут имеет значение `false`, что вызывает глобальной блокировки не должна использоваться, если прослушиватель трассировки потокобезопасен.</span><span class="sxs-lookup"><span data-stu-id="161c1-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="161c1-145">`autoflush` Атрибуту присваивается `true`, чего прослушиватель трассировки для записи в файл, независимо от того, следует ли <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="161c1-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="161c1-146">`indentsize` Атрибут имеет значение 0 (ноль), что приводит к прослушивателю в отступ при <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="161c1-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="161c1-147">См. также</span><span class="sxs-lookup"><span data-stu-id="161c1-147">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="161c1-148">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="161c1-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
