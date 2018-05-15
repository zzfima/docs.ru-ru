---
title: '&lt;Добавить&gt; элемент для &lt;коммутаторов&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e0dc425327f6577606e1205a23fdaffcc39f6e01
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltswitchesgt"></a><span data-ttu-id="c9da4-102">&lt;Добавить&gt; элемент для &lt;коммутаторов&gt;</span><span class="sxs-lookup"><span data-stu-id="c9da4-102">&lt;add&gt; Element for &lt;switches&gt;</span></span>
<span data-ttu-id="c9da4-103">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="c9da4-103">Specifies the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="c9da4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c9da4-104">\<configuration></span></span>  
<span data-ttu-id="c9da4-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="c9da4-105">\<system.diagnostics></span></span>  
<span data-ttu-id="c9da4-106">\<Коммутаторы ></span><span class="sxs-lookup"><span data-stu-id="c9da4-106">\<switches></span></span>  
<span data-ttu-id="c9da4-107">\<add></span><span class="sxs-lookup"><span data-stu-id="c9da4-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9da4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9da4-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9da4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9da4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c9da4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c9da4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9da4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9da4-111">Attributes</span></span>  
  
|<span data-ttu-id="c9da4-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9da4-112">Attribute</span></span>|<span data-ttu-id="c9da4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c9da4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9da4-114">**name**</span><span class="sxs-lookup"><span data-stu-id="c9da4-114">**name**</span></span>|<span data-ttu-id="c9da4-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c9da4-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="c9da4-116">Задает имя коммутатора.</span><span class="sxs-lookup"><span data-stu-id="c9da4-116">Specifies the name of the switch.</span></span> <span data-ttu-id="c9da4-117">Значение этого атрибута соответствует *displayName* параметр, передаваемый конструктору переключателя.</span><span class="sxs-lookup"><span data-stu-id="c9da4-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="c9da4-118">**value**</span><span class="sxs-lookup"><span data-stu-id="c9da4-118">**value**</span></span>|<span data-ttu-id="c9da4-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c9da4-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="c9da4-120">Указывает уровень переключателя.</span><span class="sxs-lookup"><span data-stu-id="c9da4-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9da4-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9da4-121">Child Elements</span></span>  
 <span data-ttu-id="c9da4-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c9da4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9da4-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9da4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c9da4-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9da4-124">Element</span></span>|<span data-ttu-id="c9da4-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c9da4-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c9da4-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9da4-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="c9da4-127">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="c9da4-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c9da4-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="c9da4-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9da4-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9da4-129">Remarks</span></span>  
 <span data-ttu-id="c9da4-130">Уровень переключателя трассировки можно изменить, поместив его в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9da4-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="c9da4-131">Если параметр <xref:System.Diagnostics.BooleanSwitch>, вы можете включать и отключать.</span><span class="sxs-lookup"><span data-stu-id="c9da4-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="c9da4-132">Если параметр <xref:System.Diagnostics.TraceSwitch>, можно назначать различные уровни для указания типов трассировки или выводимых приложением сообщений отладки.</span><span class="sxs-lookup"><span data-stu-id="c9da4-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9da4-133">Пример</span><span class="sxs-lookup"><span data-stu-id="c9da4-133">Example</span></span>  
 <span data-ttu-id="c9da4-134">В следующем примере показано, как использовать  **\<Добавить >** элемента `General` для переключателя трассировки <xref:System.Diagnostics.TraceLevel> уровня и включить `Data` логический переключатель трассировки.</span><span class="sxs-lookup"><span data-stu-id="c9da4-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9da4-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c9da4-135">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="c9da4-136">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="c9da4-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
