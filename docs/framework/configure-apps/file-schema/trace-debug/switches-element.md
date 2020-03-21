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
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153234"
---
# <a name="switches-element"></a><span data-ttu-id="b6932-102">\<переключатели> элемента</span><span class="sxs-lookup"><span data-stu-id="b6932-102">\<switches> Element</span></span>
<span data-ttu-id="b6932-103">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="b6932-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="b6932-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6932-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6932-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6932-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b6932-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<переключатели>**</span><span class="sxs-lookup"><span data-stu-id="b6932-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b6932-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6932-107">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6932-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6932-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b6932-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6932-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6932-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6932-110">Attributes</span></span>  
 <span data-ttu-id="b6932-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="b6932-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6932-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6932-112">Child Elements</span></span>  
  
|<span data-ttu-id="b6932-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6932-113">Element</span></span>|<span data-ttu-id="b6932-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b6932-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6932-115">\<добавить></span><span class="sxs-lookup"><span data-stu-id="b6932-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="b6932-116">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="b6932-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6932-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6932-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b6932-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6932-118">Element</span></span>|<span data-ttu-id="b6932-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b6932-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b6932-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6932-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="b6932-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="b6932-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6932-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="b6932-122">Remarks</span></span>  
 <span data-ttu-id="b6932-123">Вы можете изменить уровень переключателя трассировки, поместив его в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b6932-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="b6932-124">Если переключатель, <xref:System.Diagnostics.BooleanSwitch>вы можете включить и выключить его.</span><span class="sxs-lookup"><span data-stu-id="b6932-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="b6932-125">Если коммутатор <xref:System.Diagnostics.TraceSwitch>является, вы можете назначить различные уровни к нему, чтобы указать типы следов или отладки сообщений приложения выходов.</span><span class="sxs-lookup"><span data-stu-id="b6932-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6932-126">Пример</span><span class="sxs-lookup"><span data-stu-id="b6932-126">Example</span></span>  
 <span data-ttu-id="b6932-127">Ниже приводится, как использовать \*\* \<переключатель>\*\* элементом, <xref:System.Diagnostics.TraceLevel> чтобы установить `Data` переключатель `General` трассировки на уровень и включить переключатель трассировки Boolean.</span><span class="sxs-lookup"><span data-stu-id="b6932-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b6932-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b6932-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="b6932-129">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="b6932-129">Trace and Debug Settings Schema</span></span>](index.md)
