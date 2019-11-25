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
ms.openlocfilehash: 4aeb3cb0cd75f0fb27e3b359b86da61a77b491c7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088805"
---
# <a name="switches-element"></a><span data-ttu-id="82552-102">\<ные переключатели > элемента</span><span class="sxs-lookup"><span data-stu-id="82552-102">\<switches> Element</span></span>
<span data-ttu-id="82552-103">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="82552-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="82552-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="82552-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="82552-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="82552-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="82552-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<коммутаторы >**</span><span class="sxs-lookup"><span data-stu-id="82552-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="82552-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82552-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82552-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82552-108">Attributes and Elements</span></span>  
 <span data-ttu-id="82552-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82552-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82552-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82552-110">Attributes</span></span>  
 <span data-ttu-id="82552-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="82552-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82552-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82552-112">Child Elements</span></span>  
  
|<span data-ttu-id="82552-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="82552-113">Element</span></span>|<span data-ttu-id="82552-114">Описание</span><span class="sxs-lookup"><span data-stu-id="82552-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82552-115">\<add></span><span class="sxs-lookup"><span data-stu-id="82552-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="82552-116">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="82552-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82552-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82552-117">Parent Elements</span></span>  
  
|<span data-ttu-id="82552-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="82552-118">Element</span></span>|<span data-ttu-id="82552-119">Описание</span><span class="sxs-lookup"><span data-stu-id="82552-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="82552-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82552-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="82552-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="82552-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82552-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="82552-122">Remarks</span></span>  
 <span data-ttu-id="82552-123">Уровень переключателя трассировки можно изменить, поместив его в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="82552-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="82552-124">Если параметр является <xref:System.Diagnostics.BooleanSwitch>, его можно включить и отключить.</span><span class="sxs-lookup"><span data-stu-id="82552-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="82552-125">Если параметр является <xref:System.Diagnostics.TraceSwitch>, можно назначить ему разные уровни, чтобы указать типы трассировки или сообщения отладки, выданные приложением.</span><span class="sxs-lookup"><span data-stu-id="82552-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82552-126">Пример</span><span class="sxs-lookup"><span data-stu-id="82552-126">Example</span></span>  
 <span data-ttu-id="82552-127">В следующем примере показано, как использовать элемент **\<switch >** , чтобы установить переключение трассировки `General` на уровень <xref:System.Diagnostics.TraceLevel> и включить `Data` логический параметр трассировки.</span><span class="sxs-lookup"><span data-stu-id="82552-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82552-128">См. также</span><span class="sxs-lookup"><span data-stu-id="82552-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="82552-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="82552-129">Trace and Debug Settings Schema</span></span>](index.md)
