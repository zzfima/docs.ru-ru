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
ms.openlocfilehash: c161f842192396101dcc6850f3b3da328958eac3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697087"
---
# <a name="switches-element"></a><span data-ttu-id="141f1-102">Элемент > @no__t 0switches</span><span class="sxs-lookup"><span data-stu-id="141f1-102">\<switches> Element</span></span>
<span data-ttu-id="141f1-103">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="141f1-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
[<span data-ttu-id="141f1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="141f1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="141f1-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="141f1-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="141f1-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<switches >**</span><span class="sxs-lookup"><span data-stu-id="141f1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="141f1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="141f1-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="141f1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="141f1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="141f1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="141f1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="141f1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="141f1-110">Attributes</span></span>  
 <span data-ttu-id="141f1-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="141f1-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="141f1-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="141f1-112">Child Elements</span></span>  
  
|<span data-ttu-id="141f1-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="141f1-113">Element</span></span>|<span data-ttu-id="141f1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="141f1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="141f1-115">\<add></span><span class="sxs-lookup"><span data-stu-id="141f1-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="141f1-116">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="141f1-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="141f1-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="141f1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="141f1-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="141f1-118">Element</span></span>|<span data-ttu-id="141f1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="141f1-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="141f1-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="141f1-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="141f1-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="141f1-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="141f1-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="141f1-122">Remarks</span></span>  
 <span data-ttu-id="141f1-123">Уровень переключателя трассировки можно изменить, поместив его в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="141f1-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="141f1-124">Если параметр имеет значение <xref:System.Diagnostics.BooleanSwitch>, его можно включить и отключить.</span><span class="sxs-lookup"><span data-stu-id="141f1-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="141f1-125">Если параметр имеет значение <xref:System.Diagnostics.TraceSwitch>, можно назначить ему разные уровни, чтобы указать типы трассировки или сообщения отладки, выданные приложением.</span><span class="sxs-lookup"><span data-stu-id="141f1-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="141f1-126">Пример</span><span class="sxs-lookup"><span data-stu-id="141f1-126">Example</span></span>  
 <span data-ttu-id="141f1-127">В следующем примере показано, как использовать элемент **\<switch >** , чтобы задать параметр трассировки `General` на уровне <xref:System.Diagnostics.TraceLevel> и включить логический коммутатор трассировки `Data`.</span><span class="sxs-lookup"><span data-stu-id="141f1-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="141f1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="141f1-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="141f1-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="141f1-129">Trace and Debug Settings Schema</span></span>](index.md)
 