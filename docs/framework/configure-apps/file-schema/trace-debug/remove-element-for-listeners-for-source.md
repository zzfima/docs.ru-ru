---
title: <remove>Элемент для <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: edd27dd262004aead7db4d81db8ecab0e831dac1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926997"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="dc58d-102">\<Удаление > элемента для \<прослушивателей, \<> для исходного ></span><span class="sxs-lookup"><span data-stu-id="dc58d-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="dc58d-103">Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="dc58d-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="dc58d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dc58d-104">\<configuration></span></span>  
<span data-ttu-id="dc58d-105">\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="dc58d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="dc58d-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="dc58d-106">\<sources></span></span>  
<span data-ttu-id="dc58d-107">\<исходный ></span><span class="sxs-lookup"><span data-stu-id="dc58d-107">\<source></span></span>  
<span data-ttu-id="dc58d-108">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="dc58d-108">\<listeners></span></span>  
<span data-ttu-id="dc58d-109">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="dc58d-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc58d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc58d-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc58d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc58d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dc58d-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc58d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc58d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc58d-113">Attributes</span></span>  
  
|<span data-ttu-id="dc58d-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dc58d-114">Attribute</span></span>|<span data-ttu-id="dc58d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="dc58d-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="dc58d-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="dc58d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="dc58d-117">Имя прослушивателя, который необходимо удалить из `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="dc58d-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc58d-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc58d-118">Child Elements</span></span>  
 <span data-ttu-id="dc58d-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="dc58d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc58d-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc58d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="dc58d-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc58d-121">Element</span></span>|<span data-ttu-id="dc58d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="dc58d-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dc58d-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dc58d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="dc58d-124">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="dc58d-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="dc58d-125">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="dc58d-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="dc58d-126">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="dc58d-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="dc58d-127">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="dc58d-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc58d-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc58d-128">Remarks</span></span>  
 <span data-ttu-id="dc58d-129">Элемент удаляет указанный прослушиватель `Listeners` из коллекции для источника трассировки. `<remove>`</span><span class="sxs-lookup"><span data-stu-id="dc58d-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="dc58d-130">Можно удалить элемент `Listeners` из коллекции для источника трассировки программным путем, <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> вызвав метод <xref:System.Diagnostics.TraceSource> для <xref:System.Diagnostics.TraceSource.Listeners%2A> свойства экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dc58d-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="dc58d-131">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="dc58d-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc58d-132">Пример</span><span class="sxs-lookup"><span data-stu-id="dc58d-132">Example</span></span>  
 <span data-ttu-id="dc58d-133">В следующем примере `<remove>` показано, как использовать элемент перед `<add>` использованием элемента, чтобы `Listeners` добавить прослушиватель `console` в коллекцию для источника `TraceSourceApp`трассировки.</span><span class="sxs-lookup"><span data-stu-id="dc58d-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc58d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="dc58d-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="dc58d-135">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="dc58d-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dc58d-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="dc58d-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="dc58d-137">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="dc58d-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
