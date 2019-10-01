---
title: Элемент <add> для <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: 2edc890049d62913d693ad61d8d814d012c0f482
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697180"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="1bccf-102">Элемент > @no__t 0add для \<switches ></span><span class="sxs-lookup"><span data-stu-id="1bccf-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="1bccf-103">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="1bccf-103">Specifies the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="1bccf-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1bccf-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1bccf-105">&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="1bccf-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="1bccf-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<switches >** ](switches-element.md)</span><span class="sxs-lookup"><span data-stu-id="1bccf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)</span></span>  
<span data-ttu-id="1bccf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="1bccf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bccf-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bccf-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bccf-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1bccf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1bccf-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1bccf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bccf-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1bccf-111">Attributes</span></span>  
  
|<span data-ttu-id="1bccf-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1bccf-112">Attribute</span></span>|<span data-ttu-id="1bccf-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1bccf-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bccf-114">**name**</span><span class="sxs-lookup"><span data-stu-id="1bccf-114">**name**</span></span>|<span data-ttu-id="1bccf-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="1bccf-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="1bccf-116">Указывает имя переключателя.</span><span class="sxs-lookup"><span data-stu-id="1bccf-116">Specifies the name of the switch.</span></span> <span data-ttu-id="1bccf-117">Значение этого атрибута соответствует параметру *DisplayName* , переданному в конструктор переключателя.</span><span class="sxs-lookup"><span data-stu-id="1bccf-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="1bccf-118">**value**</span><span class="sxs-lookup"><span data-stu-id="1bccf-118">**value**</span></span>|<span data-ttu-id="1bccf-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="1bccf-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="1bccf-120">Задает уровень переключателя.</span><span class="sxs-lookup"><span data-stu-id="1bccf-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bccf-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1bccf-121">Child Elements</span></span>  
 <span data-ttu-id="1bccf-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="1bccf-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bccf-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1bccf-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1bccf-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="1bccf-124">Element</span></span>|<span data-ttu-id="1bccf-125">Описание</span><span class="sxs-lookup"><span data-stu-id="1bccf-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1bccf-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1bccf-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="1bccf-127">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="1bccf-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1bccf-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="1bccf-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bccf-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="1bccf-129">Remarks</span></span>  
 <span data-ttu-id="1bccf-130">Уровень переключателя трассировки можно изменить, поместив его в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1bccf-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="1bccf-131">Если параметр имеет значение <xref:System.Diagnostics.BooleanSwitch>, его можно включить и отключить.</span><span class="sxs-lookup"><span data-stu-id="1bccf-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="1bccf-132">Если параметр имеет значение <xref:System.Diagnostics.TraceSwitch>, можно назначить ему разные уровни, чтобы указать типы трассировки или сообщения отладки, выданные приложением.</span><span class="sxs-lookup"><span data-stu-id="1bccf-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bccf-133">Пример</span><span class="sxs-lookup"><span data-stu-id="1bccf-133">Example</span></span>  
 <span data-ttu-id="1bccf-134">В следующем примере показано, как использовать элемент **\<add >** , чтобы задать параметр трассировки `General` на уровне <xref:System.Diagnostics.TraceLevel> и включить логический коммутатор трассировки `Data`.</span><span class="sxs-lookup"><span data-stu-id="1bccf-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1bccf-135">См. также</span><span class="sxs-lookup"><span data-stu-id="1bccf-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="1bccf-136">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="1bccf-136">Trace and Debug Settings Schema</span></span>](index.md)
