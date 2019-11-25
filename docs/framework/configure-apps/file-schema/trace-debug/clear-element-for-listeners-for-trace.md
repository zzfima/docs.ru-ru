---
title: Элемент <clear> для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 049b8e7ed17633c0f34b062915afaf719927dad6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088914"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="063c8-102">\<очистить элемент > для прослушивателей \<> для \<трассировки ></span><span class="sxs-lookup"><span data-stu-id="063c8-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="063c8-103">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="063c8-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="063c8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="063c8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="063c8-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="063c8-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="063c8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trace**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="063c8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="063c8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**прослушиватели**](listeners-element-for-trace.md) ></span><span class="sxs-lookup"><span data-stu-id="063c8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="063c8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="063c8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="063c8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="063c8-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="063c8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="063c8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="063c8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="063c8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="063c8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="063c8-112">Attributes</span></span>  
 <span data-ttu-id="063c8-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="063c8-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="063c8-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="063c8-114">Child Elements</span></span>  
 <span data-ttu-id="063c8-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="063c8-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="063c8-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="063c8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="063c8-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="063c8-117">Element</span></span>|<span data-ttu-id="063c8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="063c8-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="063c8-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="063c8-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="063c8-120">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="063c8-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="063c8-121">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="063c8-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="063c8-122">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="063c8-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="063c8-123">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="063c8-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="063c8-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="063c8-124">Remarks</span></span>  
 <span data-ttu-id="063c8-125">Элемент `<clear>` удаляет все прослушиватели из коллекции `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="063c8-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="063c8-126">Элемент `<clear>` можно использовать перед использованием элемента `<add>`, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="063c8-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="063c8-127">Можно очистить коллекцию `Listeners` программным способом, вызвав метод <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> в свойстве <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="063c8-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="063c8-128">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="063c8-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="063c8-129">Элемент `<clear>` удаляет <xref:System.Diagnostics.DefaultTraceListener> из коллекции `Listeners`, изменяя поведение методов <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="063c8-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="063c8-130">Вызов метода `Assert` или `Fail` обычно приводит к отображению окна сообщения.</span><span class="sxs-lookup"><span data-stu-id="063c8-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="063c8-131">Однако окно сообщения не отображается, если <xref:System.Diagnostics.DefaultTraceListener> не находится в коллекции `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="063c8-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="063c8-132">Пример</span><span class="sxs-lookup"><span data-stu-id="063c8-132">Example</span></span>  
 <span data-ttu-id="063c8-133">В следующем примере показано, как использовать элемент `<clear>` перед использованием элемента `<add>`, чтобы добавить `console` прослушивателя в коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="063c8-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="063c8-134">См. также</span><span class="sxs-lookup"><span data-stu-id="063c8-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="063c8-135">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="063c8-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="063c8-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="063c8-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="063c8-137">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="063c8-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
