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
ms.openlocfilehash: ed5d30408b2c0f45f3bef091f4828bd812a63a7a
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083357"
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="73b75-102">&lt;Коммутаторы&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="73b75-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="73b75-103">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="73b75-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="73b75-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73b75-104">\<configuration></span></span>  
<span data-ttu-id="73b75-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="73b75-105">\<system.diagnostics></span></span>  
<span data-ttu-id="73b75-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="73b75-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b75-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73b75-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73b75-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73b75-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73b75-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73b75-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73b75-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73b75-110">Attributes</span></span>  
 <span data-ttu-id="73b75-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="73b75-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73b75-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73b75-112">Child Elements</span></span>  
  
|<span data-ttu-id="73b75-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="73b75-113">Element</span></span>|<span data-ttu-id="73b75-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="73b75-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73b75-115">\<add></span><span class="sxs-lookup"><span data-stu-id="73b75-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="73b75-116">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="73b75-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73b75-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73b75-117">Parent Elements</span></span>  
  
|<span data-ttu-id="73b75-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="73b75-118">Element</span></span>|<span data-ttu-id="73b75-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="73b75-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="73b75-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73b75-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="73b75-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="73b75-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73b75-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="73b75-122">Remarks</span></span>  
 <span data-ttu-id="73b75-123">Уровень переключателя трассировки можно изменить, поместив его в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="73b75-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="73b75-124">Если значение параметра равно <xref:System.Diagnostics.BooleanSwitch>, вы можете включать и отключать.</span><span class="sxs-lookup"><span data-stu-id="73b75-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="73b75-125">Если значение параметра равно <xref:System.Diagnostics.TraceSwitch>, можно назначать различные уровни для указания типов трассировки или отладки сообщений выходные данные приложения.</span><span class="sxs-lookup"><span data-stu-id="73b75-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b75-126">Пример</span><span class="sxs-lookup"><span data-stu-id="73b75-126">Example</span></span>  
 <span data-ttu-id="73b75-127">В следующем примере показано, как использовать  **\<переключения >** задаваемого элемента `General` для переключателя трассировки <xref:System.Diagnostics.TraceLevel> уровня и включить `Data` логический переключатель трассировки.</span><span class="sxs-lookup"><span data-stu-id="73b75-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73b75-128">См. также</span><span class="sxs-lookup"><span data-stu-id="73b75-128">See also</span></span>
- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="73b75-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="73b75-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
