---
title: Элемент <remove> для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 522319c64ddff6eb6872584937d540a8955b7c8f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260337"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="4ef75-102">\<Удалить > элемент для \<прослушиватели > для \<источника ></span><span class="sxs-lookup"><span data-stu-id="4ef75-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="4ef75-103">Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="4ef75-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="4ef75-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4ef75-104">\<configuration></span></span>  
<span data-ttu-id="4ef75-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="4ef75-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4ef75-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="4ef75-106">\<sources></span></span>  
<span data-ttu-id="4ef75-107">\<Источник ></span><span class="sxs-lookup"><span data-stu-id="4ef75-107">\<source></span></span>  
<span data-ttu-id="4ef75-108">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="4ef75-108">\<listeners></span></span>  
<span data-ttu-id="4ef75-109">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="4ef75-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ef75-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ef75-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ef75-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4ef75-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4ef75-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4ef75-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ef75-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4ef75-113">Attributes</span></span>  
  
|<span data-ttu-id="4ef75-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4ef75-114">Attribute</span></span>|<span data-ttu-id="4ef75-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4ef75-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="4ef75-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4ef75-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="4ef75-117">Имя прослушивателя для удаления из `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="4ef75-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ef75-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4ef75-118">Child Elements</span></span>  
 <span data-ttu-id="4ef75-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4ef75-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ef75-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4ef75-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4ef75-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="4ef75-121">Element</span></span>|<span data-ttu-id="4ef75-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="4ef75-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4ef75-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ef75-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4ef75-124">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="4ef75-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4ef75-125">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="4ef75-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="4ef75-126">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="4ef75-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="4ef75-127">Задает прослушиватели для сбора, хранения и маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="4ef75-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ef75-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ef75-128">Remarks</span></span>  
 <span data-ttu-id="4ef75-129">`<remove>` Элемент Удаляет указанный прослушиватель из `Listeners` коллекции для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="4ef75-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="4ef75-130">Можно удалить элемент из `Listeners` коллекции для источника трассировки программно, вызвав <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> метод <xref:System.Diagnostics.TraceSource.Listeners%2A> свойство <xref:System.Diagnostics.TraceSource> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4ef75-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="4ef75-131">Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4ef75-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ef75-132">Пример</span><span class="sxs-lookup"><span data-stu-id="4ef75-132">Example</span></span>  
 <span data-ttu-id="4ef75-133">В следующем примере показано, как использовать `<remove>` элемент перед использованием `<add>` элемент, чтобы добавить прослушиватель `console` для `Listeners` коллекции для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="4ef75-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ef75-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4ef75-134">See also</span></span>
- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="4ef75-135">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="4ef75-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="4ef75-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="4ef75-136">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="4ef75-137">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="4ef75-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
