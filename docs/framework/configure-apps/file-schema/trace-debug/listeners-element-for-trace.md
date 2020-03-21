---
title: Элемент <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153377"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="cb4ab-102">\<слушатели> \<Элемент для следа></span><span class="sxs-lookup"><span data-stu-id="cb4ab-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="cb4ab-103">Определяет слушателя, который собирает, хранит и направляет сообщения.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="cb4ab-104">Слушатели направляют результаты отслеживания на соответствующую цель.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-104">Listeners direct the tracing output to an appropriate target.</span></span>  

<span data-ttu-id="cb4ab-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cb4ab-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cb4ab-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="cb4ab-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="cb4ab-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<след>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="cb4ab-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="cb4ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<слушатели>**</span><span class="sxs-lookup"><span data-stu-id="cb4ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>

## <a name="syntax"></a><span data-ttu-id="cb4ab-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb4ab-109">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb4ab-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb4ab-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cb4ab-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb4ab-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb4ab-112">Attributes</span></span>  
 <span data-ttu-id="cb4ab-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cb4ab-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb4ab-114">Child Elements</span></span>  
  
|<span data-ttu-id="cb4ab-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb4ab-115">Element</span></span>|<span data-ttu-id="cb4ab-116">Описание</span><span class="sxs-lookup"><span data-stu-id="cb4ab-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb4ab-117">\<добавить></span><span class="sxs-lookup"><span data-stu-id="cb4ab-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="cb4ab-118">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="cb4ab-119">\<ясно></span><span class="sxs-lookup"><span data-stu-id="cb4ab-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="cb4ab-120">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="cb4ab-121">\<удалить></span><span class="sxs-lookup"><span data-stu-id="cb4ab-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="cb4ab-122">Удаляет слушателя из `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb4ab-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb4ab-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cb4ab-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb4ab-124">Element</span></span>|<span data-ttu-id="cb4ab-125">Описание</span><span class="sxs-lookup"><span data-stu-id="cb4ab-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cb4ab-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="cb4ab-127">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="cb4ab-128">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb4ab-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb4ab-129">Remarks</span></span>  
 <span data-ttu-id="cb4ab-130"><xref:System.Diagnostics.Debug> Классы <xref:System.Diagnostics.Trace> и классы имеют одну и ту же коллекцию **Слушателей.**</span><span class="sxs-lookup"><span data-stu-id="cb4ab-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="cb4ab-131">Если вы добавляете объект слушателя в коллекцию в одном из этих классов, другой класс использует тот же самый слушатель.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="cb4ab-132">Классы слушателя, поставляемые с помощью <xref:System.Diagnostics.TraceListener> рамочной программы .NET, происходят из класса.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="cb4ab-133">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="cb4ab-133">Configuration File</span></span>  
 <span data-ttu-id="cb4ab-134">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb4ab-135">Пример</span><span class="sxs-lookup"><span data-stu-id="cb4ab-135">Example</span></span>  
 <span data-ttu-id="cb4ab-136">Ниже приводится следующий пример, как использовать `MyListener` \*\* \<слушателей>\*\* элемент для добавления слушателей и `MyEventListener` коллекции **Слушателей.**</span><span class="sxs-lookup"><span data-stu-id="cb4ab-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="cb4ab-137">`MyListener`создает вызванный `MyListener.log` файл и записывает вывод в файл.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="cb4ab-138">`MyEventListener`создает запись в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="cb4ab-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cb4ab-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cb4ab-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="cb4ab-140">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="cb4ab-140">Trace and Debug Settings Schema</span></span>](index.md)
