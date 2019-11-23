---
title: Элемент <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: b419ecf451b79808e545525c7b8761175f390200
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699293"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="43071-102">\<Шаредлистенерс > элемент</span><span class="sxs-lookup"><span data-stu-id="43071-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="43071-103">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="43071-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="43071-104">По умолчанию эти прослушиватели не получают никаких трассировок, поэтому невозможно получить эти прослушиватели во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="43071-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="43071-105">Прослушиватели, идентифицированные как общие прослушиватели, можно добавлять в источники или трассировки по имени.</span><span class="sxs-lookup"><span data-stu-id="43071-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[<span data-ttu-id="43071-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="43071-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="43071-107">&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="43071-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="43071-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<шаредлистенерс >**</span><span class="sxs-lookup"><span data-stu-id="43071-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43071-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43071-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43071-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="43071-110">Attributes and Elements</span></span>  
 <span data-ttu-id="43071-111">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="43071-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43071-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="43071-112">Attributes</span></span>  
 <span data-ttu-id="43071-113">Нет</span><span class="sxs-lookup"><span data-stu-id="43071-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="43071-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="43071-114">Child Elements</span></span>  
  
|<span data-ttu-id="43071-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="43071-115">Element</span></span>|<span data-ttu-id="43071-116">Описание</span><span class="sxs-lookup"><span data-stu-id="43071-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43071-117">\<add></span><span class="sxs-lookup"><span data-stu-id="43071-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="43071-118">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="43071-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43071-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="43071-119">Parent Elements</span></span>  
  
|<span data-ttu-id="43071-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="43071-120">Element</span></span>|<span data-ttu-id="43071-121">Описание</span><span class="sxs-lookup"><span data-stu-id="43071-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="43071-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="43071-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="43071-123">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="43071-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43071-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="43071-124">Remarks</span></span>  
 <span data-ttu-id="43071-125">Добавление прослушивателя в коллекцию общих прослушивателей не сделает его активным прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="43071-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="43071-126">Он по-прежнему должен быть добавлен в источник трассировки или в трассировку путем добавления его в коллекцию `Listeners` для этого элемента Trace.</span><span class="sxs-lookup"><span data-stu-id="43071-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="43071-127">Классы прослушивателей в .NET Framework являются производными от класса <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="43071-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="43071-128">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="43071-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43071-129">Пример</span><span class="sxs-lookup"><span data-stu-id="43071-129">Example</span></span>  
 <span data-ttu-id="43071-130">В следующем примере показано, как использовать элемент `<sharedListeners>` для добавления `console` прослушивателя в коллекцию `Listeners` для классов <xref:System.Diagnostics.TraceSource> и <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="43071-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="43071-131">Прослушиватель трассировки консоли записывает данные трассировки в консоль с помощью вызовов либо <xref:System.Diagnostics.TraceSource>, либо <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="43071-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="43071-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="43071-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="43071-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="43071-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="43071-134">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="43071-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
