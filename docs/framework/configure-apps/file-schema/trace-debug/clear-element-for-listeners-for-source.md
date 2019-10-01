---
title: Элемент <clear> для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 05c20040ef59f4dee6b15bbe0b0369281b532754
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697193"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="934e1-102">Элемент \<clear > для > \<listeners для \<source ></span><span class="sxs-lookup"><span data-stu-id="934e1-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="934e1-103">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="934e1-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="934e1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="934e1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="934e1-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="934e1-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="934e1-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="934e1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="934e1-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="934e1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="934e1-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="934e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="934e1-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1clear >**</span><span class="sxs-lookup"><span data-stu-id="934e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="934e1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="934e1-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="934e1-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="934e1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="934e1-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="934e1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="934e1-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="934e1-113">Attributes</span></span>  
 <span data-ttu-id="934e1-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="934e1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="934e1-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="934e1-115">Child Elements</span></span>  
 <span data-ttu-id="934e1-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="934e1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="934e1-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="934e1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="934e1-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="934e1-118">Element</span></span>|<span data-ttu-id="934e1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="934e1-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="934e1-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="934e1-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="934e1-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="934e1-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="934e1-122">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="934e1-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="934e1-123">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="934e1-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="934e1-124">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="934e1-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="934e1-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="934e1-125">Remarks</span></span>  
 <span data-ttu-id="934e1-126">Элемент `<clear>` удаляет все прослушиватели из коллекции `Listeners` для источника трассировки, включая <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="934e1-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="934e1-127">Можно использовать элемент `<clear>` перед использованием элемента `<add>`, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="934e1-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="934e1-128">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="934e1-128">Configuration File</span></span>  
 <span data-ttu-id="934e1-129">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="934e1-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="934e1-130">Пример</span><span class="sxs-lookup"><span data-stu-id="934e1-130">Example</span></span>  
 <span data-ttu-id="934e1-131">В следующем примере показано, как использовать элемент `<clear>` перед использованием элементов `<add>` для добавления прослушивателей `console` и `textListener` в коллекцию `Listeners` для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="934e1-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="934e1-132">См. также</span><span class="sxs-lookup"><span data-stu-id="934e1-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="934e1-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="934e1-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="934e1-134">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="934e1-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
