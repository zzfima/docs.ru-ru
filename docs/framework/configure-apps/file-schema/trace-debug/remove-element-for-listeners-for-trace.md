---
title: Элемент <remove> для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 56d1e56514aed98d5f3b9f7363e461af6ac68a8c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697217"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="20199-102">Элемент \<remove > для > \<listeners для \<trace ></span><span class="sxs-lookup"><span data-stu-id="20199-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="20199-103">Удаляет прослушиватель из коллекции **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="20199-103">Removes a listener from the **Listeners** collection.</span></span>  
  
[<span data-ttu-id="20199-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="20199-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="20199-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="20199-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="20199-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="20199-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="20199-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="20199-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="20199-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="20199-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20199-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20199-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20199-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="20199-110">Attributes and Elements</span></span>  
 <span data-ttu-id="20199-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="20199-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20199-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="20199-112">Attributes</span></span>  
  
|<span data-ttu-id="20199-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="20199-113">Attribute</span></span>|<span data-ttu-id="20199-114">Описание</span><span class="sxs-lookup"><span data-stu-id="20199-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20199-115">**name**</span><span class="sxs-lookup"><span data-stu-id="20199-115">**name**</span></span>|<span data-ttu-id="20199-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="20199-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="20199-117">Имя прослушивателя, удаляемого из коллекции **прослушивателей** .</span><span class="sxs-lookup"><span data-stu-id="20199-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20199-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="20199-118">Child Elements</span></span>  
 <span data-ttu-id="20199-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="20199-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20199-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="20199-120">Parent Elements</span></span>  
  
|<span data-ttu-id="20199-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="20199-121">Element</span></span>|<span data-ttu-id="20199-122">Описание</span><span class="sxs-lookup"><span data-stu-id="20199-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="20199-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20199-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="20199-124">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="20199-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="20199-125">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="20199-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="20199-126">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="20199-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="20199-127">Настраивает службу трассировки ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="20199-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20199-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="20199-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20199-129">Удаление <xref:System.Diagnostics.DefaultTraceListener> из коллекции `Listeners` изменяет поведение методов <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="20199-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="20199-130">Вызов метода `Assert` или `Fail` обычно приводит к отображению окна сообщения, однако окно сообщения не отображается, если <xref:System.Diagnostics.DefaultTraceListener> не находится в коллекции `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="20199-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20199-131">Пример</span><span class="sxs-lookup"><span data-stu-id="20199-131">Example</span></span>  
 <span data-ttu-id="20199-132">В следующем примере показано, как удалить прослушиватель трассировки по умолчанию из коллекции **прослушивателей** трассировки.</span><span class="sxs-lookup"><span data-stu-id="20199-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20199-133">См. также</span><span class="sxs-lookup"><span data-stu-id="20199-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="20199-134">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="20199-134">Trace and Debug Settings Schema</span></span>](index.md)
