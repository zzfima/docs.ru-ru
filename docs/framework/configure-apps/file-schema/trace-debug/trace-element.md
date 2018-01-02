---
title: "&lt;трассировки&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d7ddcbdbdbbc2924d4f725d2fd401f873a4cfb0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lttracegt-element"></a><span data-ttu-id="a0125-102">&lt;трассировки&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="a0125-102">&lt;trace&gt; Element</span></span>
<span data-ttu-id="a0125-103">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="a0125-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="a0125-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a0125-104">\<configuration></span></span>  
<span data-ttu-id="a0125-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="a0125-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a0125-106">\<трассировки ></span><span class="sxs-lookup"><span data-stu-id="a0125-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0125-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0125-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0125-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a0125-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a0125-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a0125-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0125-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a0125-110">Attributes</span></span>  
  
|<span data-ttu-id="a0125-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a0125-111">Attribute</span></span>|<span data-ttu-id="a0125-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a0125-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="a0125-113">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a0125-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a0125-114">Указывает, является ли прослушиватели трассировки автоматически очищать выходной буфер после каждой операции записи.</span><span class="sxs-lookup"><span data-stu-id="a0125-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="a0125-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a0125-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a0125-116">Задает число пробелов для отступа.</span><span class="sxs-lookup"><span data-stu-id="a0125-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="a0125-117">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a0125-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a0125-118">Указывает, следует ли использовать глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="a0125-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="a0125-119">Автоматическая запись атрибута</span><span class="sxs-lookup"><span data-stu-id="a0125-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="a0125-120">Значение</span><span class="sxs-lookup"><span data-stu-id="a0125-120">Value</span></span>|<span data-ttu-id="a0125-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="a0125-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a0125-122">Не сбрасывает автоматически выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="a0125-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="a0125-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a0125-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a0125-124">Автоматически очищает выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="a0125-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="a0125-125">useGlobalLock атрибута</span><span class="sxs-lookup"><span data-stu-id="a0125-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="a0125-126">Значение</span><span class="sxs-lookup"><span data-stu-id="a0125-126">Value</span></span>|<span data-ttu-id="a0125-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="a0125-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a0125-128">Не использовать глобальную блокировку, если прослушиватель потокобезопасен; в противном случае использует глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="a0125-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="a0125-129">Использует глобальную блокировку, независимо от того, прослушиватель потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="a0125-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="a0125-130">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a0125-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0125-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a0125-131">Child Elements</span></span>  
  
|<span data-ttu-id="a0125-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0125-132">Element</span></span>|<span data-ttu-id="a0125-133">Описание:</span><span class="sxs-lookup"><span data-stu-id="a0125-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0125-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="a0125-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="a0125-135">Задает прослушиватель, собирающий, хранилища и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="a0125-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0125-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a0125-136">Parent Elements</span></span>  
  
|<span data-ttu-id="a0125-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0125-137">Element</span></span>|<span data-ttu-id="a0125-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a0125-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a0125-139">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a0125-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a0125-140">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="a0125-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a0125-141">Пример</span><span class="sxs-lookup"><span data-stu-id="a0125-141">Example</span></span>  
 <span data-ttu-id="a0125-142">В следующем примере показано, как использовать `<trace>` элемент для добавления прослушивателя `MyListener` для `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="a0125-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="a0125-143">`MyListener`Создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="a0125-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="a0125-144">`useGlobalLock` Атрибута задано значение `false`, чего не должно использоваться, если прослушиватель трассировки потокобезопасен глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="a0125-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="a0125-145">`autoflush` Атрибута задано значение `true`, которое вызывает прослушиватель трассировки для записи в файл независимо от того, следует ли <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="a0125-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="a0125-146">`indentsize` Атрибута задано значение 0 (ноль), вследствие чего слушатель в отступ при <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="a0125-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0125-147">См. также</span><span class="sxs-lookup"><span data-stu-id="a0125-147">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="a0125-148">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="a0125-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
