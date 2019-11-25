---
title: Элемент <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 10530cfadf2e182f912c699e50294af4b57f47b5
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088860"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="be243-102">\<прослушиватели > элемента для \<трассировки ></span><span class="sxs-lookup"><span data-stu-id="be243-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="be243-103">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="be243-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="be243-104">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="be243-104">Listeners direct the tracing output to an appropriate target.</span></span>  

<span data-ttu-id="be243-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="be243-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="be243-106">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="be243-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="be243-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trace**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="be243-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="be243-108">&nbsp;&nbsp;&nbsp;&nbsp; **&nbsp;&nbsp;\<**</span><span class="sxs-lookup"><span data-stu-id="be243-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>

## <a name="syntax"></a><span data-ttu-id="be243-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be243-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be243-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="be243-110">Attributes and Elements</span></span>  
 <span data-ttu-id="be243-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="be243-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be243-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="be243-112">Attributes</span></span>  
 <span data-ttu-id="be243-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="be243-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be243-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="be243-114">Child Elements</span></span>  
  
|<span data-ttu-id="be243-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="be243-115">Element</span></span>|<span data-ttu-id="be243-116">Описание</span><span class="sxs-lookup"><span data-stu-id="be243-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be243-117">\<add></span><span class="sxs-lookup"><span data-stu-id="be243-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="be243-118">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="be243-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="be243-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="be243-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="be243-120">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="be243-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="be243-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="be243-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="be243-122">Удаляет прослушиватель из коллекции `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="be243-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be243-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="be243-123">Parent Elements</span></span>  
  
|<span data-ttu-id="be243-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="be243-124">Element</span></span>|<span data-ttu-id="be243-125">Описание</span><span class="sxs-lookup"><span data-stu-id="be243-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="be243-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="be243-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="be243-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="be243-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="be243-128">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="be243-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be243-129">Заметки</span><span class="sxs-lookup"><span data-stu-id="be243-129">Remarks</span></span>  
 <span data-ttu-id="be243-130">Классы <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> используют одну и ту же коллекцию **прослушивателей** .</span><span class="sxs-lookup"><span data-stu-id="be243-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="be243-131">При добавлении объекта прослушивателя в коллекцию в одном из этих классов другой класс использует тот же прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="be243-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="be243-132">Классы прослушивателей, поставляемые с .NET Framework, являются производными от класса <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="be243-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="be243-133">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="be243-133">Configuration File</span></span>  
 <span data-ttu-id="be243-134">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="be243-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be243-135">Пример</span><span class="sxs-lookup"><span data-stu-id="be243-135">Example</span></span>  
 <span data-ttu-id="be243-136">В следующем примере показано использование элемента **\<listeners >** для добавления прослушивателей `MyListener` и `MyEventListener` в коллекцию **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="be243-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="be243-137">`MyListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="be243-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="be243-138">`MyEventListener` создает запись в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="be243-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be243-139">См. также</span><span class="sxs-lookup"><span data-stu-id="be243-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="be243-140">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="be243-140">Trace and Debug Settings Schema</span></span>](index.md)
