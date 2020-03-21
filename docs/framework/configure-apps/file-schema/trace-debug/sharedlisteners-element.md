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
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153325"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="51763-102">\<общиеслушатели> Элемент</span><span class="sxs-lookup"><span data-stu-id="51763-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="51763-103">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="51763-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="51763-104">Эти слушатели не получают никаких следов по умолчанию, и невозможно получить эти слушатели во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="51763-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="51763-105">Слушатели, идентифицированные как общие слушатели, могут быть добавлены к источникам или следам по имени.</span><span class="sxs-lookup"><span data-stu-id="51763-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[<span data-ttu-id="51763-106">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="51763-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="51763-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="51763-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="51763-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<общиеслушатели>**</span><span class="sxs-lookup"><span data-stu-id="51763-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51763-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51763-109">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51763-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="51763-110">Attributes and Elements</span></span>  
 <span data-ttu-id="51763-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="51763-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51763-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51763-112">Attributes</span></span>  
 <span data-ttu-id="51763-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="51763-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="51763-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51763-114">Child Elements</span></span>  
  
|<span data-ttu-id="51763-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="51763-115">Element</span></span>|<span data-ttu-id="51763-116">Описание</span><span class="sxs-lookup"><span data-stu-id="51763-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51763-117">\<добавить></span><span class="sxs-lookup"><span data-stu-id="51763-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="51763-118">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="51763-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51763-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="51763-119">Parent Elements</span></span>  
  
|<span data-ttu-id="51763-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="51763-120">Element</span></span>|<span data-ttu-id="51763-121">Описание</span><span class="sxs-lookup"><span data-stu-id="51763-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="51763-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51763-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="51763-123">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="51763-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51763-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="51763-124">Remarks</span></span>  
 <span data-ttu-id="51763-125">Добавление слушателя в общую коллекцию слушателей не делает его активным слушателем.</span><span class="sxs-lookup"><span data-stu-id="51763-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="51763-126">Он должен быть добавлен в источник трассировки или `Listeners` след, добавив его в коллекцию для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="51763-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="51763-127">Классы слушателя в рамках .NET <xref:System.Diagnostics.TraceListener> вытекают из класса.</span><span class="sxs-lookup"><span data-stu-id="51763-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="51763-128">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="51763-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51763-129">Пример</span><span class="sxs-lookup"><span data-stu-id="51763-129">Example</span></span>  
 <span data-ttu-id="51763-130">В следующем примере показано, как `<sharedListeners>` использовать `console` элемент `Listeners` для добавления слушателя в коллекцию как для классов, <xref:System.Diagnostics.TraceSource> так и <xref:System.Diagnostics.Trace> для классов.</span><span class="sxs-lookup"><span data-stu-id="51763-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="51763-131">Консольный след слушатель записывает информацию <xref:System.Diagnostics.TraceSource> о <xref:System.Diagnostics.Trace>следах на консоль через звонки либо или .</span><span class="sxs-lookup"><span data-stu-id="51763-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51763-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="51763-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="51763-133">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="51763-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="51763-134">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="51763-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
