---
title: <remove>Элемент <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153339"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="f2069-102">\<удалить элемент \<> для \<слушателей> для исходных></span><span class="sxs-lookup"><span data-stu-id="f2069-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="f2069-103">Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="f2069-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="f2069-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2069-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f2069-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2069-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="f2069-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<источники>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2069-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="f2069-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<источник>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2069-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="f2069-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<слушатели>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="f2069-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="f2069-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<удалить>**</span><span class="sxs-lookup"><span data-stu-id="f2069-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f2069-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2069-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2069-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f2069-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f2069-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f2069-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2069-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f2069-113">Attributes</span></span>  
  
|<span data-ttu-id="f2069-114">attribute</span><span class="sxs-lookup"><span data-stu-id="f2069-114">Attribute</span></span>|<span data-ttu-id="f2069-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f2069-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="f2069-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f2069-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f2069-117">Имя слушателя удалить из коллекции. `Listeners`</span><span class="sxs-lookup"><span data-stu-id="f2069-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2069-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f2069-118">Child Elements</span></span>  
 <span data-ttu-id="f2069-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="f2069-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2069-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f2069-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f2069-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f2069-121">Element</span></span>|<span data-ttu-id="f2069-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f2069-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f2069-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2069-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f2069-124">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="f2069-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="f2069-125">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="f2069-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="f2069-126">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="f2069-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="f2069-127">Определяет слушателей, которые собирают, хранят и направляют сообщения.</span><span class="sxs-lookup"><span data-stu-id="f2069-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2069-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2069-128">Remarks</span></span>  
 <span data-ttu-id="f2069-129">Элемент `<remove>` удаляет указанного слушателя `Listeners` из коллекции для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="f2069-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="f2069-130">Элемент можно удалить из `Listeners` коллекции для исходного источника <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> программно, <xref:System.Diagnostics.TraceSource.Listeners%2A> позвонив по способу свойства <xref:System.Diagnostics.TraceSource> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f2069-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="f2069-131">Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f2069-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2069-132">Пример</span><span class="sxs-lookup"><span data-stu-id="f2069-132">Example</span></span>  
 <span data-ttu-id="f2069-133">В следующем примере показано, `<remove>` как `<add>` использовать элемент перед `console` использованием `Listeners` элемента для `TraceSourceApp`добавления слушателя в коллекцию для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="f2069-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f2069-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2069-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="f2069-135">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="f2069-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f2069-136">\<ясно></span><span class="sxs-lookup"><span data-stu-id="f2069-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="f2069-137">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="f2069-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
