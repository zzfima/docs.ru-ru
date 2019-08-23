---
title: Элемент <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: e4550d4c4cd9ff37c5937ad366cccf91387c0e3f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927023"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="690ea-102">\<Listeners > элемент \<для > трассировки</span><span class="sxs-lookup"><span data-stu-id="690ea-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="690ea-103">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="690ea-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="690ea-104">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="690ea-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="690ea-105">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="690ea-105">\<configuration> Element</span></span>  
<span data-ttu-id="690ea-106">\<Элемент System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="690ea-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="690ea-107">\<Элемент > трассировки</span><span class="sxs-lookup"><span data-stu-id="690ea-107">\<trace> Element</span></span>  
<span data-ttu-id="690ea-108">\<Listeners > элемент \<для > трассировки</span><span class="sxs-lookup"><span data-stu-id="690ea-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="690ea-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="690ea-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="690ea-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="690ea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="690ea-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="690ea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="690ea-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="690ea-112">Attributes</span></span>  
 <span data-ttu-id="690ea-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="690ea-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="690ea-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="690ea-114">Child Elements</span></span>  
  
|<span data-ttu-id="690ea-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="690ea-115">Element</span></span>|<span data-ttu-id="690ea-116">Описание</span><span class="sxs-lookup"><span data-stu-id="690ea-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="690ea-117">\<add></span><span class="sxs-lookup"><span data-stu-id="690ea-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="690ea-118">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="690ea-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="690ea-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="690ea-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="690ea-120">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="690ea-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="690ea-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="690ea-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="690ea-122">Удаляет прослушиватель из `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="690ea-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="690ea-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="690ea-123">Parent Elements</span></span>  
  
|<span data-ttu-id="690ea-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="690ea-124">Element</span></span>|<span data-ttu-id="690ea-125">Описание</span><span class="sxs-lookup"><span data-stu-id="690ea-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="690ea-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="690ea-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="690ea-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="690ea-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="690ea-128">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="690ea-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="690ea-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="690ea-129">Remarks</span></span>  
 <span data-ttu-id="690ea-130">Классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> совместно используют одну и ту же коллекцию Listeners.</span><span class="sxs-lookup"><span data-stu-id="690ea-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="690ea-131">При добавлении объекта прослушивателя в коллекцию в одном из этих классов другой класс использует тот же прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="690ea-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="690ea-132">Классы прослушивателей, поставляемые с .NET Framework, являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="690ea-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="690ea-133">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="690ea-133">Configuration File</span></span>  
 <span data-ttu-id="690ea-134">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="690ea-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="690ea-135">Пример</span><span class="sxs-lookup"><span data-stu-id="690ea-135">Example</span></span>  
 <span data-ttu-id="690ea-136">В следующем примере показано, `MyListener` `MyEventListener`  **\<** как использовать элемент Listeners > для добавления прослушивателей и в коллекцию Listeners.</span><span class="sxs-lookup"><span data-stu-id="690ea-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="690ea-137">`MyListener`создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="690ea-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="690ea-138">`MyEventListener`создает запись в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="690ea-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="690ea-139">См. также</span><span class="sxs-lookup"><span data-stu-id="690ea-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="690ea-140">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="690ea-140">Trace and Debug Settings Schema</span></span>](index.md)
