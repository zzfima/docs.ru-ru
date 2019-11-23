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
# <a name="trace-element"></a><span data-ttu-id="bbc14-102">Элемент > трассировки \<</span><span class="sxs-lookup"><span data-stu-id="bbc14-102">\<trace> Element</span></span>
<span data-ttu-id="bbc14-103">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="bbc14-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[<span data-ttu-id="bbc14-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="bbc14-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="bbc14-105">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="bbc14-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="bbc14-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<трассировки >**</span><span class="sxs-lookup"><span data-stu-id="bbc14-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbc14-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbc14-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbc14-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bbc14-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bbc14-109">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bbc14-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbc14-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bbc14-110">Attributes</span></span>  
  
|<span data-ttu-id="bbc14-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bbc14-111">Attribute</span></span>|<span data-ttu-id="bbc14-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bbc14-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="bbc14-113">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bbc14-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bbc14-114">Указывает, будут ли прослушиватели трассировки автоматически сбрасывать выходной буфер после каждой операции записи.</span><span class="sxs-lookup"><span data-stu-id="bbc14-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="bbc14-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bbc14-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bbc14-116">Задает количество пробелов для отступа.</span><span class="sxs-lookup"><span data-stu-id="bbc14-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="bbc14-117">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bbc14-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bbc14-118">Указывает, следует ли использовать глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="bbc14-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="bbc14-119">Атрибут автозаписи</span><span class="sxs-lookup"><span data-stu-id="bbc14-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="bbc14-120">Значение</span><span class="sxs-lookup"><span data-stu-id="bbc14-120">Value</span></span>|<span data-ttu-id="bbc14-121">Описание</span><span class="sxs-lookup"><span data-stu-id="bbc14-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="bbc14-122">Не очищает выходной буфер автоматически.</span><span class="sxs-lookup"><span data-stu-id="bbc14-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="bbc14-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbc14-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="bbc14-124">Автоматически очищает выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="bbc14-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="bbc14-125">Атрибут useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="bbc14-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="bbc14-126">Значение</span><span class="sxs-lookup"><span data-stu-id="bbc14-126">Value</span></span>|<span data-ttu-id="bbc14-127">Описание</span><span class="sxs-lookup"><span data-stu-id="bbc14-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="bbc14-128">Не использует глобальную блокировку, если прослушиватель является потокобезопасным; в противном случае использует глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="bbc14-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="bbc14-129">Использует глобальную блокировку независимо от того, является ли прослушиватель потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="bbc14-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="bbc14-130">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbc14-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bbc14-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bbc14-131">Child Elements</span></span>  
  
|<span data-ttu-id="bbc14-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbc14-132">Element</span></span>|<span data-ttu-id="bbc14-133">Описание</span><span class="sxs-lookup"><span data-stu-id="bbc14-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bbc14-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="bbc14-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="bbc14-135">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="bbc14-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bbc14-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bbc14-136">Parent Elements</span></span>  
  
|<span data-ttu-id="bbc14-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbc14-137">Element</span></span>|<span data-ttu-id="bbc14-138">Описание</span><span class="sxs-lookup"><span data-stu-id="bbc14-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bbc14-139">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bbc14-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bbc14-140">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="bbc14-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bbc14-141">Пример</span><span class="sxs-lookup"><span data-stu-id="bbc14-141">Example</span></span>  
 <span data-ttu-id="bbc14-142">В следующем примере показано, как использовать элемент `<trace>` для добавления `MyListener` прослушивателя в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="bbc14-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="bbc14-143">`MyListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="bbc14-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="bbc14-144">Атрибут `useGlobalLock` имеет значение `false`, что приводит к тому, что глобальная блокировка не будет использоваться, если прослушиватель трассировки является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="bbc14-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="bbc14-145">Атрибут `autoflush` имеет значение `true`, что приводит к тому, что прослушиватель трассировки будет записывать данные в файл независимо от того, вызван ли метод <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bbc14-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="bbc14-146">Атрибуту `indentsize` присваивается значение 0 (ноль), что приводит к тому, что при вызове метода <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> прослушиватель устанавливает отступы в ноль пробелов.</span><span class="sxs-lookup"><span data-stu-id="bbc14-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bbc14-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="bbc14-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="bbc14-148">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="bbc14-148">Trace and Debug Settings Schema</span></span>](index.md)
