---
title: '&lt;Очистить&gt; элемент для &lt;прослушиватели&gt; для &lt;трассировки&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 91b4b4f132138fa6752c1da9b28e7a3ab7fad006
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033451"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="ea58c-102">&lt;Очистить&gt; элемент для &lt;прослушиватели&gt; для &lt;трассировки&gt;</span><span class="sxs-lookup"><span data-stu-id="ea58c-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="ea58c-103">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ea58c-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="ea58c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ea58c-104">\<configuration></span></span>  
<span data-ttu-id="ea58c-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="ea58c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="ea58c-106">\<трассировки ></span><span class="sxs-lookup"><span data-stu-id="ea58c-106">\<trace></span></span>  
<span data-ttu-id="ea58c-107">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="ea58c-107">\<listeners></span></span>  
<span data-ttu-id="ea58c-108">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="ea58c-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea58c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea58c-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea58c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea58c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ea58c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea58c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea58c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea58c-112">Attributes</span></span>  
 <span data-ttu-id="ea58c-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea58c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea58c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea58c-114">Child Elements</span></span>  
 <span data-ttu-id="ea58c-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea58c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea58c-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea58c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ea58c-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea58c-117">Element</span></span>|<span data-ttu-id="ea58c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ea58c-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ea58c-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea58c-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ea58c-120">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ea58c-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="ea58c-121">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ea58c-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="ea58c-122">Содержит прослушиватели, сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="ea58c-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="ea58c-123">Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="ea58c-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea58c-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea58c-124">Remarks</span></span>  
 <span data-ttu-id="ea58c-125">`<clear>` Элемент удаляет все прослушиватели `Listeners` коллекции для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ea58c-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="ea58c-126">Можно использовать `<clear>` элемент перед использованием `<add>` элемент, чтобы быть уверенным, отсутствуют другие активные прослушиватели в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ea58c-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="ea58c-127">Можно снять `Listeners` коллекцию программно, вызвав <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> метод <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> свойство (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="ea58c-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="ea58c-128">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="ea58c-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea58c-129">`<clear>` Приводит к удалению <xref:System.Diagnostics.DefaultTraceListener> из `Listeners` коллекции, меняет поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="ea58c-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="ea58c-130">Вызов `Assert` или `Fail` метод обычно приводит к отображению окна сообщения.</span><span class="sxs-lookup"><span data-stu-id="ea58c-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="ea58c-131">В окне сообщения тем не менее, не отображается, если <xref:System.Diagnostics.DefaultTraceListener> не находится в `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="ea58c-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea58c-132">Пример</span><span class="sxs-lookup"><span data-stu-id="ea58c-132">Example</span></span>  
 <span data-ttu-id="ea58c-133">В следующем примере показано, как использовать `<clear>` элемент перед использованием `<add>` элемент, чтобы добавить прослушиватель `console` для `Listeners` коллекции для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ea58c-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ea58c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ea58c-134">See Also</span></span>  
 <xref:System.Diagnostics.Trace.Listeners%2A>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="ea58c-135">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="ea58c-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="ea58c-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="ea58c-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)  
 [<span data-ttu-id="ea58c-137">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="ea58c-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
