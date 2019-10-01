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
ms.openlocfilehash: 02fd794eb7b7b7f46f7f7bc4e43036cb4a4758ed
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699181"
---
# <a name="trace-element"></a><span data-ttu-id="ae244-102">Элемент > @no__t 0trace</span><span class="sxs-lookup"><span data-stu-id="ae244-102">\<trace> Element</span></span>
<span data-ttu-id="ae244-103">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ae244-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[<span data-ttu-id="ae244-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ae244-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ae244-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="ae244-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="ae244-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<trace >**</span><span class="sxs-lookup"><span data-stu-id="ae244-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae244-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae244-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae244-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ae244-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ae244-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ae244-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae244-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ae244-110">Attributes</span></span>  
  
|<span data-ttu-id="ae244-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ae244-111">Attribute</span></span>|<span data-ttu-id="ae244-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ae244-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="ae244-113">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ae244-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ae244-114">Указывает, будут ли прослушиватели трассировки автоматически сбрасывать выходной буфер после каждой операции записи.</span><span class="sxs-lookup"><span data-stu-id="ae244-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="ae244-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ae244-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ae244-116">Задает количество пробелов для отступа.</span><span class="sxs-lookup"><span data-stu-id="ae244-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="ae244-117">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ae244-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ae244-118">Указывает, следует ли использовать глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="ae244-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="ae244-119">Атрибут автозаписи</span><span class="sxs-lookup"><span data-stu-id="ae244-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="ae244-120">Значение</span><span class="sxs-lookup"><span data-stu-id="ae244-120">Value</span></span>|<span data-ttu-id="ae244-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ae244-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ae244-122">Не очищает выходной буфер автоматически.</span><span class="sxs-lookup"><span data-stu-id="ae244-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="ae244-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae244-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="ae244-124">Автоматически очищает выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="ae244-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="ae244-125">Атрибут useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="ae244-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="ae244-126">Значение</span><span class="sxs-lookup"><span data-stu-id="ae244-126">Value</span></span>|<span data-ttu-id="ae244-127">Описание</span><span class="sxs-lookup"><span data-stu-id="ae244-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ae244-128">Не использует глобальную блокировку, если прослушиватель является потокобезопасным; в противном случае использует глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="ae244-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="ae244-129">Использует глобальную блокировку независимо от того, является ли прослушиватель потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="ae244-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="ae244-130">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae244-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae244-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ae244-131">Child Elements</span></span>  
  
|<span data-ttu-id="ae244-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae244-132">Element</span></span>|<span data-ttu-id="ae244-133">Описание</span><span class="sxs-lookup"><span data-stu-id="ae244-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae244-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="ae244-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="ae244-135">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="ae244-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae244-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ae244-136">Parent Elements</span></span>  
  
|<span data-ttu-id="ae244-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae244-137">Element</span></span>|<span data-ttu-id="ae244-138">Описание</span><span class="sxs-lookup"><span data-stu-id="ae244-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ae244-139">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ae244-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ae244-140">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ae244-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ae244-141">Пример</span><span class="sxs-lookup"><span data-stu-id="ae244-141">Example</span></span>  
 <span data-ttu-id="ae244-142">В следующем примере показано, как использовать элемент `<trace>` для добавления прослушивателя `MyListener` в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="ae244-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="ae244-143">`MyListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="ae244-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="ae244-144">Атрибут `useGlobalLock` имеет значение `false`, что приводит к тому, что глобальная блокировка не будет использоваться, если прослушиватель трассировки является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="ae244-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="ae244-145">Атрибут `autoflush` имеет значение `true`, что приводит к тому, что прослушиватель трассировки будет записывать данные в файл независимо от того, вызывается ли метод <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ae244-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="ae244-146">Атрибут `indentsize` имеет значение 0 (ноль), что приводит к тому, что при вызове метода <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> прослушиватель помещает отступы в ноль пробелов.</span><span class="sxs-lookup"><span data-stu-id="ae244-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae244-147">См. также</span><span class="sxs-lookup"><span data-stu-id="ae244-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="ae244-148">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="ae244-148">Trace and Debug Settings Schema</span></span>](index.md)
