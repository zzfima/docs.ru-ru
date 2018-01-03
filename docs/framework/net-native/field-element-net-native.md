---
title: "Элемент &lt;Field&gt; (машинный код .NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ef073004b213ee03ce9655096f612acb5750684
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltfieldgt-element-net-native"></a><span data-ttu-id="ea26d-102">Элемент &lt;Field&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="ea26d-102">&lt;Field&gt; Element (.NET Native)</span></span>
<span data-ttu-id="ea26d-103">Применяет политику отражения среды выполнения к полю.</span><span class="sxs-lookup"><span data-stu-id="ea26d-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea26d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea26d-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea26d-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea26d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ea26d-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea26d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea26d-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea26d-107">Attributes</span></span>  
  
|<span data-ttu-id="ea26d-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea26d-108">Attribute</span></span>|<span data-ttu-id="ea26d-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="ea26d-109">Attribute type</span></span>|<span data-ttu-id="ea26d-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="ea26d-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="ea26d-111">Общие правила</span><span class="sxs-lookup"><span data-stu-id="ea26d-111">General</span></span>|<span data-ttu-id="ea26d-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea26d-112">Required attribute.</span></span> <span data-ttu-id="ea26d-113">Определяет имя поля.</span><span class="sxs-lookup"><span data-stu-id="ea26d-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="ea26d-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="ea26d-114">Reflection</span></span>|<span data-ttu-id="ea26d-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea26d-115">Optional attribute.</span></span> <span data-ttu-id="ea26d-116">Определяет запрос для получения сведений о поле или перечисляет поле, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ea26d-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="ea26d-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="ea26d-117">Reflection</span></span>|<span data-ttu-id="ea26d-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea26d-118">Optional attribute.</span></span> <span data-ttu-id="ea26d-119">Управляет доступом среды выполнения к полю для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="ea26d-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="ea26d-120">Эта политика гарантирует, что поле можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ea26d-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="ea26d-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="ea26d-121">Serialization</span></span>|<span data-ttu-id="ea26d-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea26d-122">Optional attribute.</span></span> <span data-ttu-id="ea26d-123">Управляет доступом среды выполнения к полю, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как, например, сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="ea26d-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="ea26d-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="ea26d-124">Name attribute</span></span>  
  
|<span data-ttu-id="ea26d-125">Значение</span><span class="sxs-lookup"><span data-stu-id="ea26d-125">Value</span></span>|<span data-ttu-id="ea26d-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="ea26d-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ea26d-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="ea26d-127">*method_name*</span></span>|<span data-ttu-id="ea26d-128">Имя поля.</span><span class="sxs-lookup"><span data-stu-id="ea26d-128">The field name.</span></span> <span data-ttu-id="ea26d-129">Тип поля определяется родительским элементом [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) или [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="ea26d-129">The type of the field is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="ea26d-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea26d-130">All other attributes</span></span>  
  
|<span data-ttu-id="ea26d-131">Значение</span><span class="sxs-lookup"><span data-stu-id="ea26d-131">Value</span></span>|<span data-ttu-id="ea26d-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="ea26d-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ea26d-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="ea26d-133">*policy_setting*</span></span>|<span data-ttu-id="ea26d-134">Параметр, применяемый к этому типу политики для поля.</span><span class="sxs-lookup"><span data-stu-id="ea26d-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="ea26d-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="ea26d-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="ea26d-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ea26d-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea26d-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea26d-137">Child Elements</span></span>  
 <span data-ttu-id="ea26d-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea26d-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea26d-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea26d-139">Parent Elements</span></span>  
  
|<span data-ttu-id="ea26d-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea26d-140">Element</span></span>|<span data-ttu-id="ea26d-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="ea26d-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea26d-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="ea26d-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="ea26d-143">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="ea26d-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="ea26d-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="ea26d-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="ea26d-145">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="ea26d-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea26d-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea26d-146">Remarks</span></span>  
 <span data-ttu-id="ea26d-147">Если политика поля не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="ea26d-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea26d-148">См. также</span><span class="sxs-lookup"><span data-stu-id="ea26d-148">See Also</span></span>  
 [<span data-ttu-id="ea26d-149">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ea26d-149">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="ea26d-150">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="ea26d-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="ea26d-151">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ea26d-151">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
