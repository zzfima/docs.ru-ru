---
title: <clear>Элемент для <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 9816ba0f8e4ddd4c38537eb4e014a4240ff20407
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927172"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="3820b-102">\<Очистка элемента > для \<прослушивателей, \<> для трассировки ></span><span class="sxs-lookup"><span data-stu-id="3820b-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="3820b-103">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="3820b-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="3820b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3820b-104">\<configuration></span></span>  
<span data-ttu-id="3820b-105">\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="3820b-105">\<system.diagnostics></span></span>  
<span data-ttu-id="3820b-106">\<> трассировки</span><span class="sxs-lookup"><span data-stu-id="3820b-106">\<trace></span></span>  
<span data-ttu-id="3820b-107">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="3820b-107">\<listeners></span></span>  
<span data-ttu-id="3820b-108">\<очистить ></span><span class="sxs-lookup"><span data-stu-id="3820b-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3820b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3820b-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3820b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3820b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3820b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3820b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3820b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3820b-112">Attributes</span></span>  
 <span data-ttu-id="3820b-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="3820b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3820b-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3820b-114">Child Elements</span></span>  
 <span data-ttu-id="3820b-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="3820b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3820b-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3820b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3820b-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="3820b-117">Element</span></span>|<span data-ttu-id="3820b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3820b-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3820b-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3820b-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3820b-120">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="3820b-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="3820b-121">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="3820b-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="3820b-122">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="3820b-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="3820b-123">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="3820b-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3820b-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="3820b-124">Remarks</span></span>  
 <span data-ttu-id="3820b-125">Элемент удаляет все прослушиватели `Listeners` из коллекции для трассировки. `<clear>`</span><span class="sxs-lookup"><span data-stu-id="3820b-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="3820b-126">`<clear>` Элемент можно использовать перед `<add>` использованием элемента, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="3820b-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="3820b-127">Можно очистить `Listeners` коллекцию программным путем, <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> вызвав метод для <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> свойства (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="3820b-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="3820b-128">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="3820b-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3820b-129"><xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Элемент удаляет из коллекции`Listeners`, изменяя поведение методов ,,и.<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.DefaultTraceListener> `<clear>`</span><span class="sxs-lookup"><span data-stu-id="3820b-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="3820b-130">Вызов метода `Fail` или обычно приводит к отображению окна сообщения. `Assert`</span><span class="sxs-lookup"><span data-stu-id="3820b-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="3820b-131">Однако окно сообщения не отображается, если объект <xref:System.Diagnostics.DefaultTraceListener> отсутствует `Listeners` в коллекции.</span><span class="sxs-lookup"><span data-stu-id="3820b-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3820b-132">Пример</span><span class="sxs-lookup"><span data-stu-id="3820b-132">Example</span></span>  
 <span data-ttu-id="3820b-133">В следующем примере показано `<clear>` , как использовать элемент перед `<add>` использованием элемента для `Listeners` добавления прослушивателя `console` в коллекцию для трассировки.</span><span class="sxs-lookup"><span data-stu-id="3820b-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3820b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3820b-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="3820b-135">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="3820b-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3820b-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="3820b-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="3820b-137">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="3820b-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
