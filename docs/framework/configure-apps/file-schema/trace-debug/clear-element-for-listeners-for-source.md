---
title: <clear>Элемент <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153585"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="fac6e-102">\<ясно> \<элемент для \<слушателей> для источников></span><span class="sxs-lookup"><span data-stu-id="fac6e-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="fac6e-103">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="fac6e-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="fac6e-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fac6e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fac6e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="fac6e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="fac6e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<источники>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="fac6e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="fac6e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<источник>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="fac6e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="fac6e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="fac6e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="fac6e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ясно>**</span><span class="sxs-lookup"><span data-stu-id="fac6e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fac6e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fac6e-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fac6e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fac6e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fac6e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fac6e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fac6e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fac6e-113">Attributes</span></span>  
 <span data-ttu-id="fac6e-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="fac6e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fac6e-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fac6e-115">Child Elements</span></span>  
 <span data-ttu-id="fac6e-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="fac6e-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fac6e-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fac6e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fac6e-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="fac6e-118">Element</span></span>|<span data-ttu-id="fac6e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fac6e-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fac6e-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fac6e-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fac6e-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="fac6e-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="fac6e-122">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="fac6e-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="fac6e-123">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="fac6e-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="fac6e-124">Определяет слушателей, которые собирают, хранят и направляют сообщения.</span><span class="sxs-lookup"><span data-stu-id="fac6e-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fac6e-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="fac6e-125">Remarks</span></span>  
 <span data-ttu-id="fac6e-126">Элемент `<clear>` удаляет всех слушателей `Listeners` из коллекции для <xref:System.Diagnostics.DefaultTraceListener>источника трассировки, включая .</span><span class="sxs-lookup"><span data-stu-id="fac6e-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="fac6e-127">Вы можете `<clear>` использовать элемент, `<add>` прежде чем использовать элемент, чтобы быть уверенным, что в коллекции нет других активных слушателей.</span><span class="sxs-lookup"><span data-stu-id="fac6e-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="fac6e-128">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="fac6e-128">Configuration File</span></span>  
 <span data-ttu-id="fac6e-129">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="fac6e-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fac6e-130">Пример</span><span class="sxs-lookup"><span data-stu-id="fac6e-130">Example</span></span>  
 <span data-ttu-id="fac6e-131">Ниже приводится следующий `<clear>` пример, как `<add>` использовать элемент `console` перед `textListener` использованием элементов для добавления слушателей и в коллекцию `Listeners` для источника `TraceSourceApp`трассировки.</span><span class="sxs-lookup"><span data-stu-id="fac6e-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fac6e-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fac6e-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="fac6e-133">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="fac6e-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fac6e-134">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="fac6e-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
