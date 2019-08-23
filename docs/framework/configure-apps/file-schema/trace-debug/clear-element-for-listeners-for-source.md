---
title: <clear>Элемент для <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 768d51a74b4c31d1250d2f5d6517f760f886e0a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920562"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="d6be3-102">\<Очистка элемента > для \<прослушивателей, \<> для исходного ></span><span class="sxs-lookup"><span data-stu-id="d6be3-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="d6be3-103">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="d6be3-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="d6be3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d6be3-104">\<configuration></span></span>  
<span data-ttu-id="d6be3-105">\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="d6be3-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d6be3-106">\<источники ></span><span class="sxs-lookup"><span data-stu-id="d6be3-106">\<sources></span></span>  
<span data-ttu-id="d6be3-107">\<исходный ></span><span class="sxs-lookup"><span data-stu-id="d6be3-107">\<source></span></span>  
<span data-ttu-id="d6be3-108">\<прослушиватели ></span><span class="sxs-lookup"><span data-stu-id="d6be3-108">\<listeners></span></span>  
<span data-ttu-id="d6be3-109">\<очистить ></span><span class="sxs-lookup"><span data-stu-id="d6be3-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6be3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6be3-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6be3-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d6be3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d6be3-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d6be3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6be3-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d6be3-113">Attributes</span></span>  
 <span data-ttu-id="d6be3-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="d6be3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d6be3-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d6be3-115">Child Elements</span></span>  
 <span data-ttu-id="d6be3-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="d6be3-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6be3-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d6be3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d6be3-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6be3-118">Element</span></span>|<span data-ttu-id="d6be3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d6be3-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d6be3-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6be3-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d6be3-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="d6be3-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d6be3-122">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="d6be3-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="d6be3-123">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="d6be3-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d6be3-124">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="d6be3-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6be3-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6be3-125">Remarks</span></span>  
 <span data-ttu-id="d6be3-126">Элемент удаляет все прослушиватели `Listeners` из коллекции для источника <xref:System.Diagnostics.DefaultTraceListener>трассировки, включая. `<clear>`</span><span class="sxs-lookup"><span data-stu-id="d6be3-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="d6be3-127">`<clear>` Элемент можно использовать перед `<add>` использованием элемента, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d6be3-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d6be3-128">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="d6be3-128">Configuration File</span></span>  
 <span data-ttu-id="d6be3-129">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d6be3-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6be3-130">Пример</span><span class="sxs-lookup"><span data-stu-id="d6be3-130">Example</span></span>  
 <span data-ttu-id="d6be3-131">В следующем примере `<clear>` показано, как использовать элемент перед `<add>` использованием элементов для добавления прослушивателей `console` и `textListener` в `Listeners` коллекцию для источника `TraceSourceApp`трассировки.</span><span class="sxs-lookup"><span data-stu-id="d6be3-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="d6be3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d6be3-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="d6be3-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="d6be3-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d6be3-134">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="d6be3-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
