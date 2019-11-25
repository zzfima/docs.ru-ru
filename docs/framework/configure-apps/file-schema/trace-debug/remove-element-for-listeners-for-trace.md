---
title: Элемент <remove> для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088836"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="01101-102">\<удалить элемент > для прослушивателей \<> для \<Trace ></span><span class="sxs-lookup"><span data-stu-id="01101-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="01101-103">Удаляет прослушиватель из коллекции **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="01101-103">Removes a listener from the **Listeners** collection.</span></span>  

<span data-ttu-id="01101-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="01101-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="01101-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="01101-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="01101-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trace**](trace-element.md) ></span><span class="sxs-lookup"><span data-stu-id="01101-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="01101-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**прослушиватели**](listeners-element-for-trace.md) ></span><span class="sxs-lookup"><span data-stu-id="01101-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="01101-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<удалить >**</span><span class="sxs-lookup"><span data-stu-id="01101-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="01101-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01101-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01101-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="01101-110">Attributes and Elements</span></span>  
 <span data-ttu-id="01101-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="01101-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01101-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="01101-112">Attributes</span></span>  
  
|<span data-ttu-id="01101-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="01101-113">Attribute</span></span>|<span data-ttu-id="01101-114">Описание</span><span class="sxs-lookup"><span data-stu-id="01101-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01101-115">**name**</span><span class="sxs-lookup"><span data-stu-id="01101-115">**name**</span></span>|<span data-ttu-id="01101-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="01101-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="01101-117">Имя прослушивателя, удаляемого из коллекции **прослушивателей** .</span><span class="sxs-lookup"><span data-stu-id="01101-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01101-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="01101-118">Child Elements</span></span>  
 <span data-ttu-id="01101-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="01101-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01101-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="01101-120">Parent Elements</span></span>  
  
|<span data-ttu-id="01101-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="01101-121">Element</span></span>|<span data-ttu-id="01101-122">Описание</span><span class="sxs-lookup"><span data-stu-id="01101-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="01101-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01101-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="01101-124">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="01101-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="01101-125">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="01101-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="01101-126">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="01101-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="01101-127">Настраивает службу трассировки ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="01101-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01101-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="01101-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01101-129">Удаление <xref:System.Diagnostics.DefaultTraceListener> из коллекции `Listeners` изменяет поведение методов <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01101-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="01101-130">Вызов метода `Assert` или `Fail` обычно приводит к отображению окна сообщения, однако окно сообщения не отображается, если <xref:System.Diagnostics.DefaultTraceListener> не находится в коллекции `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="01101-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01101-131">Пример</span><span class="sxs-lookup"><span data-stu-id="01101-131">Example</span></span>  
 <span data-ttu-id="01101-132">В следующем примере показано, как удалить прослушиватель трассировки по умолчанию из коллекции **прослушивателей** трассировки.</span><span class="sxs-lookup"><span data-stu-id="01101-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="01101-133">См. также</span><span class="sxs-lookup"><span data-stu-id="01101-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="01101-134">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="01101-134">Trace and Debug Settings Schema</span></span>](index.md)
