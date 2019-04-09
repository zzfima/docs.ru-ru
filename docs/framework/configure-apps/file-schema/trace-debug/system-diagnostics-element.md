---
title: Элемент < system.diagnostics >
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 026805ffb9b89aa55e84cf9a5c4afb8ed63cec09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142718"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="cd9b9-102">\<System.Diagnostics > элемент</span><span class="sxs-lookup"><span data-stu-id="cd9b9-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="cd9b9-103">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="cd9b9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cd9b9-104">\<configuration></span></span>  
<span data-ttu-id="cd9b9-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="cd9b9-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd9b9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd9b9-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd9b9-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cd9b9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cd9b9-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd9b9-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cd9b9-109">Attributes</span></span>  
 <span data-ttu-id="cd9b9-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cd9b9-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cd9b9-111">Child Elements</span></span>  
  
|<span data-ttu-id="cd9b9-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd9b9-112">Element</span></span>|<span data-ttu-id="cd9b9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cd9b9-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd9b9-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="cd9b9-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="cd9b9-115">Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="cd9b9-116">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="cd9b9-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="cd9b9-117">Задает размер глобальной памяти, совместно используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="cd9b9-118">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="cd9b9-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="cd9b9-119">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="cd9b9-120">Прослушиватели, определенные как общие могут добавляться к источникам и трассировки по имени.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="cd9b9-121">\<источники ></span><span class="sxs-lookup"><span data-stu-id="cd9b9-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="cd9b9-122">Задает источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="cd9b9-123">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="cd9b9-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="cd9b9-124">Содержит переключатели трассировки и уровни, где они установлены.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="cd9b9-125">\<трассировки ></span><span class="sxs-lookup"><span data-stu-id="cd9b9-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="cd9b9-126">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd9b9-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cd9b9-127">Parent Elements</span></span>  
  
|<span data-ttu-id="cd9b9-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd9b9-128">Element</span></span>|<span data-ttu-id="cd9b9-129">Описание</span><span class="sxs-lookup"><span data-stu-id="cd9b9-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cd9b9-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cd9b9-131">Пример</span><span class="sxs-lookup"><span data-stu-id="cd9b9-131">Example</span></span>  
 <span data-ttu-id="cd9b9-132">В следующем примере показано, как внедрение переключателя трассировки и прослушивателя трассировки в  **\<system.diagnostics >** элемент.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="cd9b9-133">`General` Установлен переключатель трассировки <xref:System.Diagnostics.TraceLevel> уровень.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="cd9b9-134">Прослушиватель трассировки `myListener` создается файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd9b9-135">В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="cd9b9-136">Например, можно указать `true` для <xref:System.Diagnostics.BooleanSwitch> или текст, представляющий значение перечисления, таких как `Error` для <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="cd9b9-137">Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="cd9b9-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd9b9-138">См. также</span><span class="sxs-lookup"><span data-stu-id="cd9b9-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="cd9b9-139">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="cd9b9-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
