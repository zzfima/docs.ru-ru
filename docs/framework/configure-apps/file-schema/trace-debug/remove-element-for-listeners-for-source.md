---
title: Элемент <remove> для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 4a11308278f755ec8271477352d91d8797d105c5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699489"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="02fa8-102">Элемент \<remove > для > \<listeners для \<source ></span><span class="sxs-lookup"><span data-stu-id="02fa8-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="02fa8-103">Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="02fa8-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="02fa8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="02fa8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="02fa8-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="02fa8-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="02fa8-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="02fa8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="02fa8-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="02fa8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="02fa8-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="02fa8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="02fa8-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1remove >**</span><span class="sxs-lookup"><span data-stu-id="02fa8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02fa8-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02fa8-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02fa8-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="02fa8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="02fa8-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="02fa8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02fa8-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="02fa8-113">Attributes</span></span>  
  
|<span data-ttu-id="02fa8-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="02fa8-114">Attribute</span></span>|<span data-ttu-id="02fa8-115">Описание</span><span class="sxs-lookup"><span data-stu-id="02fa8-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="02fa8-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="02fa8-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="02fa8-117">Имя прослушивателя, удаляемого из коллекции `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="02fa8-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02fa8-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="02fa8-118">Child Elements</span></span>  
 <span data-ttu-id="02fa8-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="02fa8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02fa8-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="02fa8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="02fa8-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="02fa8-121">Element</span></span>|<span data-ttu-id="02fa8-122">Описание</span><span class="sxs-lookup"><span data-stu-id="02fa8-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02fa8-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02fa8-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="02fa8-124">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="02fa8-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="02fa8-125">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="02fa8-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="02fa8-126">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="02fa8-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="02fa8-127">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="02fa8-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02fa8-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="02fa8-128">Remarks</span></span>  
 <span data-ttu-id="02fa8-129">Элемент `<remove>` удаляет указанный прослушиватель из коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="02fa8-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="02fa8-130">Можно удалить элемент из коллекции `Listeners` для источника трассировки программным путем, вызвав метод <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> для свойства <xref:System.Diagnostics.TraceSource.Listeners%2A> экземпляра <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="02fa8-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="02fa8-131">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="02fa8-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02fa8-132">Пример</span><span class="sxs-lookup"><span data-stu-id="02fa8-132">Example</span></span>  
 <span data-ttu-id="02fa8-133">В следующем примере показано, как использовать элемент `<remove>` перед использованием элемента `<add>` для добавления прослушивателя `console` в коллекцию `Listeners` для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="02fa8-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="02fa8-134">См. также</span><span class="sxs-lookup"><span data-stu-id="02fa8-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="02fa8-135">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="02fa8-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="02fa8-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="02fa8-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="02fa8-137">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="02fa8-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
