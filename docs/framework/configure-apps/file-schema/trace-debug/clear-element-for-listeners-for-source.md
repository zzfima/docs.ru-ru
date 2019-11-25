---
title: Элемент <clear> для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 4567f236397435e89371ca4c80730ff964fddd21
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088936"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="5528f-102">\<очистить элемент > для прослушивателей \<> для \<исходного кода ></span><span class="sxs-lookup"><span data-stu-id="5528f-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="5528f-103">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="5528f-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="5528f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5528f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5528f-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="5528f-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="5528f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="5528f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="5528f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="5528f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="5528f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="5528f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="5528f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="5528f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5528f-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5528f-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5528f-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5528f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5528f-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5528f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5528f-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5528f-113">Attributes</span></span>  
 <span data-ttu-id="5528f-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5528f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5528f-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5528f-115">Child Elements</span></span>  
 <span data-ttu-id="5528f-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5528f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5528f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5528f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5528f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="5528f-118">Element</span></span>|<span data-ttu-id="5528f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5528f-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5528f-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5528f-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5528f-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="5528f-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="5528f-122">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="5528f-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="5528f-123">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="5528f-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="5528f-124">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="5528f-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5528f-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="5528f-125">Remarks</span></span>  
 <span data-ttu-id="5528f-126">Элемент `<clear>` удаляет все прослушиватели из коллекции `Listeners` для источника трассировки, включая <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="5528f-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="5528f-127">Элемент `<clear>` можно использовать перед использованием элемента `<add>`, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5528f-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="5528f-128">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="5528f-128">Configuration File</span></span>  
 <span data-ttu-id="5528f-129">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5528f-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5528f-130">Пример</span><span class="sxs-lookup"><span data-stu-id="5528f-130">Example</span></span>  
 <span data-ttu-id="5528f-131">В следующем примере показано, как использовать элемент `<clear>` перед использованием элементов `<add>` для добавления прослушивателей `console` и `textListener` в коллекцию `Listeners` для источника трассировки `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="5528f-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5528f-132">См. также</span><span class="sxs-lookup"><span data-stu-id="5528f-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="5528f-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="5528f-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5528f-134">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="5528f-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
