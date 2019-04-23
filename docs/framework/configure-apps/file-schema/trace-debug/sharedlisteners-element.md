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
ms.openlocfilehash: 48cb59dfc0871822bfcff5e16d4283008a411479
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190802"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="41f72-102">\<sharedListeners > элемент</span><span class="sxs-lookup"><span data-stu-id="41f72-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="41f72-103">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="41f72-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="41f72-104">Эти прослушиватели не получают все трассировки по умолчанию, и невозможно извлечь эти прослушиватели во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="41f72-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="41f72-105">Прослушиватели, определенные как общие могут добавляться к источникам и трассировки по имени.</span><span class="sxs-lookup"><span data-stu-id="41f72-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="41f72-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="41f72-106">\<configuration></span></span>  
<span data-ttu-id="41f72-107">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="41f72-107">\<system.diagnostics></span></span>  
<span data-ttu-id="41f72-108">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="41f72-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41f72-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41f72-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41f72-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="41f72-110">Attributes and Elements</span></span>  
 <span data-ttu-id="41f72-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="41f72-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41f72-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="41f72-112">Attributes</span></span>  
 <span data-ttu-id="41f72-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="41f72-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="41f72-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="41f72-114">Child Elements</span></span>  
  
|<span data-ttu-id="41f72-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="41f72-115">Element</span></span>|<span data-ttu-id="41f72-116">Описание</span><span class="sxs-lookup"><span data-stu-id="41f72-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41f72-117">\<add></span><span class="sxs-lookup"><span data-stu-id="41f72-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="41f72-118">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="41f72-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41f72-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="41f72-119">Parent Elements</span></span>  
  
|<span data-ttu-id="41f72-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="41f72-120">Element</span></span>|<span data-ttu-id="41f72-121">Описание</span><span class="sxs-lookup"><span data-stu-id="41f72-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="41f72-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41f72-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="41f72-123">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="41f72-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41f72-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="41f72-124">Remarks</span></span>  
 <span data-ttu-id="41f72-125">Добавление прослушивателя к общей коллекции прослушивателей не делает его активным.</span><span class="sxs-lookup"><span data-stu-id="41f72-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="41f72-126">Оно по-прежнему добавлено к источнику трассировки или трассировки путем добавления его в `Listeners` коллекции для этого элемента трассировки.</span><span class="sxs-lookup"><span data-stu-id="41f72-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="41f72-127">Классы прослушивателя в .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="41f72-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="41f72-128">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="41f72-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41f72-129">Пример</span><span class="sxs-lookup"><span data-stu-id="41f72-129">Example</span></span>  
 <span data-ttu-id="41f72-130">В следующем примере показано, как использовать `<sharedListeners>` элемент, чтобы добавить прослушиватель `console` для `Listeners` коллекции для обоих <xref:System.Diagnostics.TraceSource> и <xref:System.Diagnostics.Trace> классы.</span><span class="sxs-lookup"><span data-stu-id="41f72-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="41f72-131">Прослушиватель трассировки консоли записывает сведения трассировки на консоль, через вызовы к либо <xref:System.Diagnostics.TraceSource> или <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="41f72-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="41f72-132">См. также</span><span class="sxs-lookup"><span data-stu-id="41f72-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="41f72-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="41f72-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="41f72-134">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="41f72-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
