---
title: Элемент <trace>
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
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153170"
---
# <a name="trace-element"></a><span data-ttu-id="a17fa-102">\<след> Элемент</span><span class="sxs-lookup"><span data-stu-id="a17fa-102">\<trace> Element</span></span>
<span data-ttu-id="a17fa-103">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="a17fa-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[<span data-ttu-id="a17fa-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="a17fa-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a17fa-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="a17fa-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="a17fa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<след>**</span><span class="sxs-lookup"><span data-stu-id="a17fa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a17fa-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a17fa-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a17fa-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a17fa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a17fa-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a17fa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a17fa-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a17fa-110">Attributes</span></span>  
  
|<span data-ttu-id="a17fa-111">attribute</span><span class="sxs-lookup"><span data-stu-id="a17fa-111">Attribute</span></span>|<span data-ttu-id="a17fa-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a17fa-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="a17fa-113">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a17fa-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a17fa-114">Определяет, автоматически ли слушатели трассировки промывают буфер вывода после каждой операции записи.</span><span class="sxs-lookup"><span data-stu-id="a17fa-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="a17fa-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a17fa-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a17fa-116">Определяет количество пробелов для отступа.</span><span class="sxs-lookup"><span data-stu-id="a17fa-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="a17fa-117">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a17fa-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a17fa-118">Указывает, следует ли использовать глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="a17fa-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="a17fa-119">autoflush Атрибут</span><span class="sxs-lookup"><span data-stu-id="a17fa-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="a17fa-120">Значение</span><span class="sxs-lookup"><span data-stu-id="a17fa-120">Value</span></span>|<span data-ttu-id="a17fa-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a17fa-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a17fa-122">Не автоматически сбрасывает буфер вывода.</span><span class="sxs-lookup"><span data-stu-id="a17fa-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="a17fa-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a17fa-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a17fa-124">Автоматически сбрасывает буфер вывода.</span><span class="sxs-lookup"><span data-stu-id="a17fa-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="a17fa-125">useGlobalLock Атрибут</span><span class="sxs-lookup"><span data-stu-id="a17fa-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="a17fa-126">Значение</span><span class="sxs-lookup"><span data-stu-id="a17fa-126">Value</span></span>|<span data-ttu-id="a17fa-127">Описание</span><span class="sxs-lookup"><span data-stu-id="a17fa-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a17fa-128">Не использует глобальную блокировку, если слушатель является безопасным потоком; в противном случае использует глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="a17fa-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="a17fa-129">Использует глобальную блокировку независимо от того, является ли слушатель безопасным потоком.</span><span class="sxs-lookup"><span data-stu-id="a17fa-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="a17fa-130">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a17fa-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a17fa-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a17fa-131">Child Elements</span></span>  
  
|<span data-ttu-id="a17fa-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="a17fa-132">Element</span></span>|<span data-ttu-id="a17fa-133">Описание</span><span class="sxs-lookup"><span data-stu-id="a17fa-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a17fa-134">\<слушатели></span><span class="sxs-lookup"><span data-stu-id="a17fa-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="a17fa-135">Определяет слушателя, который собирает, хранит и направляет сообщения.</span><span class="sxs-lookup"><span data-stu-id="a17fa-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a17fa-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a17fa-136">Parent Elements</span></span>  
  
|<span data-ttu-id="a17fa-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="a17fa-137">Element</span></span>|<span data-ttu-id="a17fa-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a17fa-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a17fa-139">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a17fa-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a17fa-140">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="a17fa-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a17fa-141">Пример</span><span class="sxs-lookup"><span data-stu-id="a17fa-141">Example</span></span>  
 <span data-ttu-id="a17fa-142">В следующем примере показано, как использовать `<trace>` `MyListener` элемент `Listeners` для добавления слушателя в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="a17fa-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="a17fa-143">`MyListener`создает файл, который `MyListener.log` называется, и записывает вывод в файл.</span><span class="sxs-lookup"><span data-stu-id="a17fa-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="a17fa-144">Атрибут `useGlobalLock` установлен на, `false`что приводит к глобальной блокировки не будет использоваться, если слушатель трассировки поток безопасно.</span><span class="sxs-lookup"><span data-stu-id="a17fa-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="a17fa-145">Атрибут `autoflush` установлен на, `true`который вызывает слушателя следа, чтобы написать в файл, независимо от того, <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> метод называется.</span><span class="sxs-lookup"><span data-stu-id="a17fa-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="a17fa-146">Атрибут `indentsize` установлен до 0 (ноль), что приводит к тому, <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> что при вызове метода слушателю будут установлены нулевые пробелы.</span><span class="sxs-lookup"><span data-stu-id="a17fa-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a17fa-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a17fa-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="a17fa-148">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="a17fa-148">Trace and Debug Settings Schema</span></span>](index.md)
