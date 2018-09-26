---
title: '&lt;Коммутаторы&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7ca375935c1dfcdb406257ece1a9dfd18851dddf
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47113888"
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="0992d-102">&lt;Коммутаторы&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="0992d-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="0992d-103">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="0992d-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="0992d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0992d-104">\<configuration></span></span>  
<span data-ttu-id="0992d-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="0992d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="0992d-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="0992d-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0992d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0992d-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0992d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0992d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0992d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0992d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0992d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0992d-110">Attributes</span></span>  
 <span data-ttu-id="0992d-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0992d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0992d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0992d-112">Child Elements</span></span>  
  
|<span data-ttu-id="0992d-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="0992d-113">Element</span></span>|<span data-ttu-id="0992d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0992d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0992d-115">\<add></span><span class="sxs-lookup"><span data-stu-id="0992d-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="0992d-116">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="0992d-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0992d-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0992d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0992d-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="0992d-118">Element</span></span>|<span data-ttu-id="0992d-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0992d-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0992d-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0992d-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="0992d-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="0992d-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0992d-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="0992d-122">Remarks</span></span>  
 <span data-ttu-id="0992d-123">Уровень переключателя трассировки можно изменить, поместив его в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0992d-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="0992d-124">Если значение параметра равно <xref:System.Diagnostics.BooleanSwitch>, вы можете включать и отключать.</span><span class="sxs-lookup"><span data-stu-id="0992d-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="0992d-125">Если значение параметра равно <xref:System.Diagnostics.TraceSwitch>, можно назначать различные уровни для указания типов трассировки или отладки сообщений выходные данные приложения.</span><span class="sxs-lookup"><span data-stu-id="0992d-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0992d-126">Пример</span><span class="sxs-lookup"><span data-stu-id="0992d-126">Example</span></span>  
 <span data-ttu-id="0992d-127">В следующем примере показано, как использовать  **\<переключения >** задаваемого элемента `General` для переключателя трассировки <xref:System.Diagnostics.TraceLevel> уровня и включить `Data` логический переключатель трассировки.</span><span class="sxs-lookup"><span data-stu-id="0992d-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0992d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="0992d-128">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="0992d-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="0992d-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
