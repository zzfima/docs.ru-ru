---
title: <remove>Элемент для <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 0c5c9efb8a22d26ea5d4467f9628af5935d6dbad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920475"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="d2309-102">\<Удаление > элемента для \<прослушивателей, \<> для трассировки ></span><span class="sxs-lookup"><span data-stu-id="d2309-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="d2309-103">Удаляет прослушиватель из коллекции **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="d2309-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="d2309-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d2309-104">\<configuration></span></span>  
<span data-ttu-id="d2309-105">\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="d2309-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d2309-106">\<> трассировки</span><span class="sxs-lookup"><span data-stu-id="d2309-106">\<trace></span></span>  
<span data-ttu-id="d2309-107">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="d2309-107">\<listeners></span></span>  
<span data-ttu-id="d2309-108">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="d2309-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2309-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2309-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2309-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d2309-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d2309-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d2309-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2309-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d2309-112">Attributes</span></span>  
  
|<span data-ttu-id="d2309-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d2309-113">Attribute</span></span>|<span data-ttu-id="d2309-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d2309-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2309-115">**name**</span><span class="sxs-lookup"><span data-stu-id="d2309-115">**name**</span></span>|<span data-ttu-id="d2309-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d2309-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="d2309-117">Имя прослушивателя, удаляемого из коллекции **прослушивателей** .</span><span class="sxs-lookup"><span data-stu-id="d2309-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2309-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d2309-118">Child Elements</span></span>  
 <span data-ttu-id="d2309-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="d2309-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2309-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d2309-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d2309-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="d2309-121">Element</span></span>|<span data-ttu-id="d2309-122">Описание</span><span class="sxs-lookup"><span data-stu-id="d2309-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d2309-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d2309-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="d2309-124">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="d2309-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="d2309-125">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="d2309-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d2309-126">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2309-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="d2309-127">Настраивает службу трассировки ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d2309-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2309-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2309-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2309-129"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>При удалении <xref:System.Diagnostics.DefaultTraceListener> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>из коллекции изменяется поведение методов,, и<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> . `Listeners`</span><span class="sxs-lookup"><span data-stu-id="d2309-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="d2309-130">Вызов метода `Fail` `Listeners` или обычно приводит к отображению окна сообщения, однако окно сообщения не отображается, если объект <xref:System.Diagnostics.DefaultTraceListener> отсутствует в коллекции. `Assert`</span><span class="sxs-lookup"><span data-stu-id="d2309-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2309-131">Пример</span><span class="sxs-lookup"><span data-stu-id="d2309-131">Example</span></span>  
 <span data-ttu-id="d2309-132">В следующем примере показано, как удалить прослушиватель трассировки по умолчанию из коллекции прослушивателей трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2309-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2309-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d2309-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="d2309-134">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="d2309-134">Trace and Debug Settings Schema</span></span>](index.md)
