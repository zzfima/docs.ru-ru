---
title: Элемент <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 92a1c8db43579048945d76082e3ebd2862efd7ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920442"
---
# <a name="switches-element"></a><span data-ttu-id="08fa1-102">\<переключает > элемент</span><span class="sxs-lookup"><span data-stu-id="08fa1-102">\<switches> Element</span></span>
<span data-ttu-id="08fa1-103">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="08fa1-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="08fa1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="08fa1-104">\<configuration></span></span>  
<span data-ttu-id="08fa1-105">\<> System. Diagnostics</span><span class="sxs-lookup"><span data-stu-id="08fa1-105">\<system.diagnostics></span></span>  
<span data-ttu-id="08fa1-106">\<переключатели ></span><span class="sxs-lookup"><span data-stu-id="08fa1-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08fa1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08fa1-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08fa1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08fa1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="08fa1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08fa1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08fa1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08fa1-110">Attributes</span></span>  
 <span data-ttu-id="08fa1-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="08fa1-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="08fa1-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08fa1-112">Child Elements</span></span>  
  
|<span data-ttu-id="08fa1-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="08fa1-113">Element</span></span>|<span data-ttu-id="08fa1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="08fa1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08fa1-115">\<add></span><span class="sxs-lookup"><span data-stu-id="08fa1-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="08fa1-116">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="08fa1-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08fa1-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08fa1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="08fa1-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="08fa1-118">Element</span></span>|<span data-ttu-id="08fa1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="08fa1-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="08fa1-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="08fa1-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="08fa1-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="08fa1-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08fa1-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="08fa1-122">Remarks</span></span>  
 <span data-ttu-id="08fa1-123">Уровень переключателя трассировки можно изменить, поместив его в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="08fa1-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="08fa1-124">Если параметр имеет <xref:System.Diagnostics.BooleanSwitch>значение, его можно включить и отключить.</span><span class="sxs-lookup"><span data-stu-id="08fa1-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="08fa1-125">Если параметр имеет <xref:System.Diagnostics.TraceSwitch>значение, можно назначить для него разные уровни, чтобы указать типы трассировки или сообщения отладки, выданные приложением.</span><span class="sxs-lookup"><span data-stu-id="08fa1-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08fa1-126">Пример</span><span class="sxs-lookup"><span data-stu-id="08fa1-126">Example</span></span>  
 <span data-ttu-id="08fa1-127">В следующем примере показано <xref:System.Diagnostics.TraceLevel> использование `Data` `General`  **\<элемента Switch >** для задания переключателя трассировки на уровне и включения логического переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="08fa1-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="08fa1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="08fa1-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="08fa1-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="08fa1-129">Trace and Debug Settings Schema</span></span>](index.md)
