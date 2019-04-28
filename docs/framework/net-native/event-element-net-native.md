---
title: <Event> Элемент (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89e8ddf9ea72db63c72bfb5393709b4c20de2a14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868612"
---
# <a name="event-element-net-native"></a><span data-ttu-id="867ff-102">\<Событие > элемент (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="867ff-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="867ff-103">Применяет политику отражения среды выполнения к событию.</span><span class="sxs-lookup"><span data-stu-id="867ff-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="867ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="867ff-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="867ff-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="867ff-105">Attributes and Elements</span></span>  
 <span data-ttu-id="867ff-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="867ff-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="867ff-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="867ff-107">Attributes</span></span>  
  
|<span data-ttu-id="867ff-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="867ff-108">Attribute</span></span>|<span data-ttu-id="867ff-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="867ff-109">Attribute type</span></span>|<span data-ttu-id="867ff-110">Описание</span><span class="sxs-lookup"><span data-stu-id="867ff-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="867ff-111">Общие</span><span class="sxs-lookup"><span data-stu-id="867ff-111">General</span></span>|<span data-ttu-id="867ff-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="867ff-112">Required attribute.</span></span> <span data-ttu-id="867ff-113">Задает имя события.</span><span class="sxs-lookup"><span data-stu-id="867ff-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="867ff-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="867ff-114">Reflection</span></span>|<span data-ttu-id="867ff-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="867ff-115">Optional attribute.</span></span> <span data-ttu-id="867ff-116">Определяет запрос для получения сведений о событиях или перечисляет события, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="867ff-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="867ff-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="867ff-117">Reflection</span></span>|<span data-ttu-id="867ff-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="867ff-118">Optional attribute.</span></span> <span data-ttu-id="867ff-119">Управляет доступом среды выполнения к событию для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="867ff-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="867ff-120">Эта политика гарантирует, что события могут обрабатываться динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="867ff-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="867ff-121">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="867ff-121">Name attribute</span></span>  
  
|<span data-ttu-id="867ff-122">Значение</span><span class="sxs-lookup"><span data-stu-id="867ff-122">Value</span></span>|<span data-ttu-id="867ff-123">Описание</span><span class="sxs-lookup"><span data-stu-id="867ff-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="867ff-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="867ff-124">*method_name*</span></span>|<span data-ttu-id="867ff-125">Имя события.</span><span class="sxs-lookup"><span data-stu-id="867ff-125">The event name.</span></span> <span data-ttu-id="867ff-126">Тип события определяется родительским элементом [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) или [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="867ff-126">The type of the event is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="867ff-127">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="867ff-127">All other attributes</span></span>  
  
|<span data-ttu-id="867ff-128">Значение</span><span class="sxs-lookup"><span data-stu-id="867ff-128">Value</span></span>|<span data-ttu-id="867ff-129">Описание</span><span class="sxs-lookup"><span data-stu-id="867ff-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="867ff-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="867ff-130">*policy_setting*</span></span>|<span data-ttu-id="867ff-131">Параметр, применяемый к этому типу политики для события.</span><span class="sxs-lookup"><span data-stu-id="867ff-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="867ff-132">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="867ff-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="867ff-133">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="867ff-133">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="867ff-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="867ff-134">Child Elements</span></span>  
 <span data-ttu-id="867ff-135">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="867ff-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="867ff-136">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="867ff-136">Parent Elements</span></span>  
  
|<span data-ttu-id="867ff-137">Элемент</span><span class="sxs-lookup"><span data-stu-id="867ff-137">Element</span></span>|<span data-ttu-id="867ff-138">Описание</span><span class="sxs-lookup"><span data-stu-id="867ff-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="867ff-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="867ff-139">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="867ff-140">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="867ff-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="867ff-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="867ff-141">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="867ff-142">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="867ff-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="867ff-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="867ff-143">Remarks</span></span>  
 <span data-ttu-id="867ff-144">Если политика события не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="867ff-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867ff-145">См. также</span><span class="sxs-lookup"><span data-stu-id="867ff-145">See also</span></span>

- [<span data-ttu-id="867ff-146">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="867ff-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="867ff-147">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="867ff-147">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="867ff-148">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="867ff-148">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
