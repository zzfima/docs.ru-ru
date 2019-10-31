---
title: Элемент <Event> (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 6966caede63faafa718b760be879f6bc6cbd3ab9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128496"
---
# <a name="event-element-net-native"></a><span data-ttu-id="657c8-102">Элемент > события \<(.NET Native)</span><span class="sxs-lookup"><span data-stu-id="657c8-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="657c8-103">Применяет политику отражения среды выполнения к событию.</span><span class="sxs-lookup"><span data-stu-id="657c8-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="657c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="657c8-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="657c8-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="657c8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="657c8-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="657c8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="657c8-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="657c8-107">Attributes</span></span>  
  
|<span data-ttu-id="657c8-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="657c8-108">Attribute</span></span>|<span data-ttu-id="657c8-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="657c8-109">Attribute type</span></span>|<span data-ttu-id="657c8-110">Описание</span><span class="sxs-lookup"><span data-stu-id="657c8-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="657c8-111">Общее</span><span class="sxs-lookup"><span data-stu-id="657c8-111">General</span></span>|<span data-ttu-id="657c8-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="657c8-112">Required attribute.</span></span> <span data-ttu-id="657c8-113">Задает имя события.</span><span class="sxs-lookup"><span data-stu-id="657c8-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="657c8-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="657c8-114">Reflection</span></span>|<span data-ttu-id="657c8-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="657c8-115">Optional attribute.</span></span> <span data-ttu-id="657c8-116">Определяет запрос для получения сведений о событиях или перечисляет события, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="657c8-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="657c8-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="657c8-117">Reflection</span></span>|<span data-ttu-id="657c8-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="657c8-118">Optional attribute.</span></span> <span data-ttu-id="657c8-119">Управляет доступом среды выполнения к событию для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="657c8-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="657c8-120">Эта политика гарантирует, что события могут обрабатываться динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="657c8-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="657c8-121">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="657c8-121">Name attribute</span></span>  
  
|<span data-ttu-id="657c8-122">значения</span><span class="sxs-lookup"><span data-stu-id="657c8-122">Value</span></span>|<span data-ttu-id="657c8-123">Описание</span><span class="sxs-lookup"><span data-stu-id="657c8-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="657c8-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="657c8-124">*method_name*</span></span>|<span data-ttu-id="657c8-125">Имя события.</span><span class="sxs-lookup"><span data-stu-id="657c8-125">The event name.</span></span> <span data-ttu-id="657c8-126">Тип события определяется родительским элементом [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="657c8-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="657c8-127">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="657c8-127">All other attributes</span></span>  
  
|<span data-ttu-id="657c8-128">значения</span><span class="sxs-lookup"><span data-stu-id="657c8-128">Value</span></span>|<span data-ttu-id="657c8-129">Описание</span><span class="sxs-lookup"><span data-stu-id="657c8-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="657c8-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="657c8-130">*policy_setting*</span></span>|<span data-ttu-id="657c8-131">Параметр, применяемый к этому типу политики для события.</span><span class="sxs-lookup"><span data-stu-id="657c8-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="657c8-132">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="657c8-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="657c8-133">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="657c8-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="657c8-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="657c8-134">Child Elements</span></span>  
 <span data-ttu-id="657c8-135">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="657c8-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="657c8-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="657c8-136">Parent Elements</span></span>  
  
|<span data-ttu-id="657c8-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="657c8-137">Element</span></span>|<span data-ttu-id="657c8-138">Описание</span><span class="sxs-lookup"><span data-stu-id="657c8-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="657c8-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="657c8-139">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="657c8-140">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="657c8-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="657c8-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="657c8-141">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="657c8-142">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="657c8-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="657c8-143">Заметки</span><span class="sxs-lookup"><span data-stu-id="657c8-143">Remarks</span></span>  
 <span data-ttu-id="657c8-144">Если политика события не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="657c8-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657c8-145">См. также</span><span class="sxs-lookup"><span data-stu-id="657c8-145">See also</span></span>

- [<span data-ttu-id="657c8-146">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="657c8-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="657c8-147">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="657c8-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="657c8-148">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="657c8-148">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
