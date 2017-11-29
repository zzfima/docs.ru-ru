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
ms.openlocfilehash: 9a3a928185146ac90ec4c3a905bf4f0e69e0e8d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltfieldgt-element-net-native"></a><span data-ttu-id="2096e-102">Элемент &lt;Field&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="2096e-102">&lt;Field&gt; Element (.NET Native)</span></span>
<span data-ttu-id="2096e-103">Применяет политику отражения среды выполнения к полю.</span><span class="sxs-lookup"><span data-stu-id="2096e-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2096e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2096e-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2096e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2096e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2096e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2096e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2096e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2096e-107">Attributes</span></span>  
  
|<span data-ttu-id="2096e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2096e-108">Attribute</span></span>|<span data-ttu-id="2096e-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="2096e-109">Attribute type</span></span>|<span data-ttu-id="2096e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2096e-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="2096e-111">Общие правила</span><span class="sxs-lookup"><span data-stu-id="2096e-111">General</span></span>|<span data-ttu-id="2096e-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2096e-112">Required attribute.</span></span> <span data-ttu-id="2096e-113">Определяет имя поля.</span><span class="sxs-lookup"><span data-stu-id="2096e-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="2096e-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="2096e-114">Reflection</span></span>|<span data-ttu-id="2096e-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2096e-115">Optional attribute.</span></span> <span data-ttu-id="2096e-116">Определяет запрос для получения сведений о поле или перечисляет поле, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2096e-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="2096e-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="2096e-117">Reflection</span></span>|<span data-ttu-id="2096e-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2096e-118">Optional attribute.</span></span> <span data-ttu-id="2096e-119">Управляет доступом среды выполнения к полю для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="2096e-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="2096e-120">Эта политика гарантирует, что поле можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2096e-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="2096e-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="2096e-121">Serialization</span></span>|<span data-ttu-id="2096e-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2096e-122">Optional attribute.</span></span> <span data-ttu-id="2096e-123">Управляет доступом среды выполнения к полю, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как, например, сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="2096e-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="2096e-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="2096e-124">Name attribute</span></span>  
  
|<span data-ttu-id="2096e-125">Значение</span><span class="sxs-lookup"><span data-stu-id="2096e-125">Value</span></span>|<span data-ttu-id="2096e-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2096e-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2096e-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="2096e-127">*method_name*</span></span>|<span data-ttu-id="2096e-128">Имя поля.</span><span class="sxs-lookup"><span data-stu-id="2096e-128">The field name.</span></span> <span data-ttu-id="2096e-129">Тип поля определяется родительским элементом [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) или [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="2096e-129">The type of the field is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="2096e-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="2096e-130">All other attributes</span></span>  
  
|<span data-ttu-id="2096e-131">Значение</span><span class="sxs-lookup"><span data-stu-id="2096e-131">Value</span></span>|<span data-ttu-id="2096e-132">Описание</span><span class="sxs-lookup"><span data-stu-id="2096e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2096e-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="2096e-133">*policy_setting*</span></span>|<span data-ttu-id="2096e-134">Параметр, применяемый к этому типу политики для поля.</span><span class="sxs-lookup"><span data-stu-id="2096e-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="2096e-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="2096e-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="2096e-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2096e-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2096e-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2096e-137">Child Elements</span></span>  
 <span data-ttu-id="2096e-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2096e-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2096e-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2096e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="2096e-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="2096e-140">Element</span></span>|<span data-ttu-id="2096e-141">Описание</span><span class="sxs-lookup"><span data-stu-id="2096e-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2096e-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="2096e-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="2096e-143">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="2096e-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="2096e-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="2096e-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="2096e-145">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="2096e-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2096e-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="2096e-146">Remarks</span></span>  
 <span data-ttu-id="2096e-147">Если политика поля не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="2096e-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2096e-148">См. также</span><span class="sxs-lookup"><span data-stu-id="2096e-148">See Also</span></span>  
 [<span data-ttu-id="2096e-149">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="2096e-149">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="2096e-150">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="2096e-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="2096e-151">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="2096e-151">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
