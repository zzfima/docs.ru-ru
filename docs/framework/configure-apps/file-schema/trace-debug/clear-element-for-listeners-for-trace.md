---
title: <clear>Элемент <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153546"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="d2959-102">\<ясно> \<Элемент для \<слушателей> для следа></span><span class="sxs-lookup"><span data-stu-id="d2959-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="d2959-103">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2959-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="d2959-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2959-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2959-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2959-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="d2959-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<след>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2959-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="d2959-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="d2959-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="d2959-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ясно>**</span><span class="sxs-lookup"><span data-stu-id="d2959-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d2959-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2959-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2959-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d2959-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d2959-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d2959-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2959-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d2959-112">Attributes</span></span>  
 <span data-ttu-id="d2959-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="d2959-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2959-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d2959-114">Child Elements</span></span>  
 <span data-ttu-id="d2959-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="d2959-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2959-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d2959-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d2959-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="d2959-117">Element</span></span>|<span data-ttu-id="d2959-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d2959-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d2959-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d2959-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d2959-120">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2959-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="d2959-121">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2959-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d2959-122">Содержит слушателей, которые собирают, хранят и направляют сообщения.</span><span class="sxs-lookup"><span data-stu-id="d2959-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="d2959-123">Слушатели направляют результаты отслеживания на соответствующую цель.</span><span class="sxs-lookup"><span data-stu-id="d2959-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2959-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2959-124">Remarks</span></span>  
 <span data-ttu-id="d2959-125">Элемент `<clear>` удаляет всех слушателей `Listeners` из коллекции для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2959-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="d2959-126">Вы можете `<clear>` использовать элемент, `<add>` прежде чем использовать элемент, чтобы быть уверенным, что в коллекции нет других активных слушателей.</span><span class="sxs-lookup"><span data-stu-id="d2959-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="d2959-127">Вы можете `Listeners` очистить коллекцию программно, <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> позвонив метод на <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> имущество (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="d2959-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="d2959-128">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d2959-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2959-129">Элемент `<clear>` <xref:System.Diagnostics.DefaultTraceListener> удаляет `Listeners` из коллекции, изменяя поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="d2959-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="d2959-130">Вызов `Assert` или `Fail` метод обычно приводит к отображению ящика сообщений.</span><span class="sxs-lookup"><span data-stu-id="d2959-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="d2959-131">Однако окно сообщений не отображается, <xref:System.Diagnostics.DefaultTraceListener> если `Listeners` его нет в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d2959-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2959-132">Пример</span><span class="sxs-lookup"><span data-stu-id="d2959-132">Example</span></span>  
 <span data-ttu-id="d2959-133">В следующем примере показано, `<clear>` как `<add>` использовать элемент перед `console` использованием `Listeners` элемента для добавления слушателя в коллекцию для отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2959-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2959-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2959-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="d2959-135">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="d2959-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d2959-136">\<удалить></span><span class="sxs-lookup"><span data-stu-id="d2959-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="d2959-137">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="d2959-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
