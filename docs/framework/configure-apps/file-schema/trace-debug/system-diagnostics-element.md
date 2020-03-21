---
title: <система.диагностика> Элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153211"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="ce787-102">\<system.diagnostics> Элемент</span><span class="sxs-lookup"><span data-stu-id="ce787-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="ce787-103">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce787-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="ce787-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="ce787-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ce787-105">&nbsp;&nbsp;**\<system.diagnostics>**</span><span class="sxs-lookup"><span data-stu-id="ce787-105">&nbsp;&nbsp;**\<system.diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce787-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce787-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce787-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ce787-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ce787-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ce787-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce787-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ce787-109">Attributes</span></span>  
 <span data-ttu-id="ce787-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="ce787-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce787-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ce787-111">Child Elements</span></span>  
  
|<span data-ttu-id="ce787-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ce787-112">Element</span></span>|<span data-ttu-id="ce787-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ce787-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce787-114">\<утверждать></span><span class="sxs-lookup"><span data-stu-id="ce787-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="ce787-115">Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.</span><span class="sxs-lookup"><span data-stu-id="ce787-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="ce787-116">\<производительностьКонтры></span><span class="sxs-lookup"><span data-stu-id="ce787-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="ce787-117">Задает размер глобальной памяти, совместно используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="ce787-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="ce787-118">\<общиеслушатели></span><span class="sxs-lookup"><span data-stu-id="ce787-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="ce787-119">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce787-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="ce787-120">Слушатели, идентифицированные как общие слушатели, могут быть добавлены к источникам или следам по имени.</span><span class="sxs-lookup"><span data-stu-id="ce787-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="ce787-121">\<источники></span><span class="sxs-lookup"><span data-stu-id="ce787-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="ce787-122">Определяет источники трассировки, которые инициируют отслеживание сообщений.</span><span class="sxs-lookup"><span data-stu-id="ce787-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="ce787-123">\<переключатели></span><span class="sxs-lookup"><span data-stu-id="ce787-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="ce787-124">Содержит переключатели трассировки и уровни, на которых установлены переключатели трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce787-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="ce787-125">\<след></span><span class="sxs-lookup"><span data-stu-id="ce787-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="ce787-126">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce787-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce787-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ce787-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ce787-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="ce787-128">Element</span></span>|<span data-ttu-id="ce787-129">Описание</span><span class="sxs-lookup"><span data-stu-id="ce787-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ce787-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce787-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ce787-131">Пример</span><span class="sxs-lookup"><span data-stu-id="ce787-131">Example</span></span>  
 <span data-ttu-id="ce787-132">В следующем примере показано, как встраить в \*\* \<>систему\*\* переключатель трассировки и слушателя.</span><span class="sxs-lookup"><span data-stu-id="ce787-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="ce787-133">Переключатель `General` трассировки <xref:System.Diagnostics.TraceLevel> установлен на уровне.</span><span class="sxs-lookup"><span data-stu-id="ce787-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="ce787-134">Слушатель `myListener` трассировки создает `MyListener.log` вызванный файл и записывает вывод в файл.</span><span class="sxs-lookup"><span data-stu-id="ce787-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce787-135">В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст.</span><span class="sxs-lookup"><span data-stu-id="ce787-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="ce787-136">Например, можно `true` указать <xref:System.Diagnostics.BooleanSwitch> текст или использовать текст, представляющий значение `Error` перечисления, например <xref:System.Diagnostics.TraceSwitch>для .</span><span class="sxs-lookup"><span data-stu-id="ce787-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="ce787-137">Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="ce787-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce787-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ce787-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="ce787-139">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="ce787-139">Trace and Debug Settings Schema</span></span>](index.md)
