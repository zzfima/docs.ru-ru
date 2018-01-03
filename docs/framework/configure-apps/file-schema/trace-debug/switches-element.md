---
title: "&lt;Коммутаторы&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 64cf3ba9e5529c4a46b2d5365931a47ad2ab211a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="cddc7-102">&lt;Коммутаторы&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="cddc7-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="cddc7-103">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="cddc7-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="cddc7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cddc7-104">\<configuration></span></span>  
<span data-ttu-id="cddc7-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="cddc7-105">\<system.diagnostics></span></span>  
<span data-ttu-id="cddc7-106">\<Коммутаторы ></span><span class="sxs-lookup"><span data-stu-id="cddc7-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cddc7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cddc7-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cddc7-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cddc7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cddc7-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cddc7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cddc7-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cddc7-110">Attributes</span></span>  
 <span data-ttu-id="cddc7-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cddc7-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cddc7-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cddc7-112">Child Elements</span></span>  
  
|<span data-ttu-id="cddc7-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="cddc7-113">Element</span></span>|<span data-ttu-id="cddc7-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="cddc7-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cddc7-115">\<add></span><span class="sxs-lookup"><span data-stu-id="cddc7-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="cddc7-116">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="cddc7-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cddc7-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cddc7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cddc7-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="cddc7-118">Element</span></span>|<span data-ttu-id="cddc7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cddc7-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cddc7-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cddc7-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="cddc7-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="cddc7-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cddc7-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="cddc7-122">Remarks</span></span>  
 <span data-ttu-id="cddc7-123">Уровень переключателя трассировки можно изменить, поместив его в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cddc7-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="cddc7-124">Если параметр <xref:System.Diagnostics.BooleanSwitch>, вы можете включать и отключать.</span><span class="sxs-lookup"><span data-stu-id="cddc7-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="cddc7-125">Если параметр <xref:System.Diagnostics.TraceSwitch>, можно назначать различные уровни для указания типов трассировки или выводимых приложением сообщений отладки.</span><span class="sxs-lookup"><span data-stu-id="cddc7-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cddc7-126">Пример</span><span class="sxs-lookup"><span data-stu-id="cddc7-126">Example</span></span>  
 <span data-ttu-id="cddc7-127">В следующем примере показано, как использовать  **\<переключения >** элемента `General` для переключателя трассировки <xref:System.Diagnostics.TraceLevel> уровня и включить `Data` логический переключатель трассировки.</span><span class="sxs-lookup"><span data-stu-id="cddc7-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cddc7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cddc7-128">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="cddc7-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="cddc7-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
