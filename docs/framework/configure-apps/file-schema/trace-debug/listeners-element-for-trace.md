---
title: Элемент <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 84b67532825372e7f69d86e1ef6060f4263587eb
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699352"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="1d71a-102">Элемент > @no__t 0listeners для \<trace ></span><span class="sxs-lookup"><span data-stu-id="1d71a-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="1d71a-103">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="1d71a-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="1d71a-104">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="1d71a-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
[<span data-ttu-id="1d71a-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1d71a-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1d71a-106">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="1d71a-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="1d71a-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="1d71a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="1d71a-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<listeners >**</span><span class="sxs-lookup"><span data-stu-id="1d71a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d71a-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d71a-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d71a-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1d71a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1d71a-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1d71a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d71a-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1d71a-112">Attributes</span></span>  
 <span data-ttu-id="1d71a-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="1d71a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d71a-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1d71a-114">Child Elements</span></span>  
  
|<span data-ttu-id="1d71a-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d71a-115">Element</span></span>|<span data-ttu-id="1d71a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="1d71a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d71a-117">\<add></span><span class="sxs-lookup"><span data-stu-id="1d71a-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="1d71a-118">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="1d71a-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="1d71a-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="1d71a-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="1d71a-120">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="1d71a-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="1d71a-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="1d71a-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="1d71a-122">Удаляет прослушиватель из коллекции `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="1d71a-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d71a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1d71a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1d71a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d71a-124">Element</span></span>|<span data-ttu-id="1d71a-125">Описание</span><span class="sxs-lookup"><span data-stu-id="1d71a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1d71a-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d71a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1d71a-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1d71a-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="1d71a-128">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="1d71a-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d71a-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d71a-129">Remarks</span></span>  
 <span data-ttu-id="1d71a-130">Классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> используют одну и ту же коллекцию **прослушивателей** .</span><span class="sxs-lookup"><span data-stu-id="1d71a-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="1d71a-131">При добавлении объекта прослушивателя в коллекцию в одном из этих классов другой класс использует тот же прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="1d71a-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="1d71a-132">Классы прослушивателей, поставляемые с .NET Framework, являются производными от класса <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="1d71a-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1d71a-133">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="1d71a-133">Configuration File</span></span>  
 <span data-ttu-id="1d71a-134">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="1d71a-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d71a-135">Пример</span><span class="sxs-lookup"><span data-stu-id="1d71a-135">Example</span></span>  
 <span data-ttu-id="1d71a-136">В следующем примере показано, как использовать элемент **\<listeners >** для добавления прослушивателей `MyListener` и `MyEventListener` в коллекцию **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="1d71a-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="1d71a-137">`MyListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="1d71a-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="1d71a-138">`MyEventListener` создает запись в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="1d71a-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d71a-139">См. также</span><span class="sxs-lookup"><span data-stu-id="1d71a-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="1d71a-140">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="1d71a-140">Trace and Debug Settings Schema</span></span>](index.md)
