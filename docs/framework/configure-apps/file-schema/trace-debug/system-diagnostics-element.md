---
title: < System. Diagnostics > элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: dc05c46cb1ba74baceaaeadc2959a6889faf19c9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699197"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="1ff8d-102">\<System. Diagnostics > элемент</span><span class="sxs-lookup"><span data-stu-id="1ff8d-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="1ff8d-103">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="1ff8d-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1ff8d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1ff8d-105">&nbsp;&nbsp; **\<System. diagnostics >**</span><span class="sxs-lookup"><span data-stu-id="1ff8d-105">&nbsp;&nbsp;**\<system.diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff8d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ff8d-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ff8d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1ff8d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1ff8d-108">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ff8d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ff8d-109">Attributes</span></span>  
 <span data-ttu-id="1ff8d-110">Нет</span><span class="sxs-lookup"><span data-stu-id="1ff8d-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ff8d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ff8d-111">Child Elements</span></span>  
  
|<span data-ttu-id="1ff8d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ff8d-112">Element</span></span>|<span data-ttu-id="1ff8d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1ff8d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ff8d-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="1ff8d-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="1ff8d-115">Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="1ff8d-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="1ff8d-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="1ff8d-117">Задает размер глобальной памяти, совместно используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="1ff8d-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="1ff8d-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="1ff8d-119">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="1ff8d-120">Прослушиватели, идентифицированные как общие прослушиватели, можно добавлять в источники или трассировки по имени.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="1ff8d-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="1ff8d-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="1ff8d-122">Указывает источники трассировки, инициирующие сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="1ff8d-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="1ff8d-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="1ff8d-124">Содержит переключатели трассировки и уровни, на которых заданы переключатели трассировки.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="1ff8d-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="1ff8d-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="1ff8d-126">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ff8d-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1ff8d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1ff8d-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ff8d-128">Element</span></span>|<span data-ttu-id="1ff8d-129">Описание</span><span class="sxs-lookup"><span data-stu-id="1ff8d-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1ff8d-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ff8d-131">Пример</span><span class="sxs-lookup"><span data-stu-id="1ff8d-131">Example</span></span>  
 <span data-ttu-id="1ff8d-132">В следующем примере показано, как внедрить переключатель трассировки и прослушиватель трассировки в элемент **\<System. diagnostics >** .</span><span class="sxs-lookup"><span data-stu-id="1ff8d-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="1ff8d-133">Для параметра трассировки `General` задан уровень <xref:System.Diagnostics.TraceLevel>.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="1ff8d-134">Прослушиватель трассировки `myListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ff8d-135">В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="1ff8d-136">Например, можно указать `true` для <xref:System.Diagnostics.BooleanSwitch> или использовать текст, представляющий значение перечисления, например `Error` для <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="1ff8d-137">Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="1ff8d-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ff8d-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ff8d-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="1ff8d-139">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="1ff8d-139">Trace and Debug Settings Schema</span></span>](index.md)
