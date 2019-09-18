---
title: <Field>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6dfb6a07f9733ab1a01a1ce9917c6a4bb4ce793b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049776"
---
# <a name="field-element-net-native"></a><span data-ttu-id="33247-102">\<Элемент > поля (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="33247-102">\<Field> Element (.NET Native)</span></span>
<span data-ttu-id="33247-103">Применяет политику отражения среды выполнения к полю.</span><span class="sxs-lookup"><span data-stu-id="33247-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33247-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33247-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33247-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33247-105">Attributes and Elements</span></span>  
 <span data-ttu-id="33247-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="33247-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33247-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33247-107">Attributes</span></span>  
  
|<span data-ttu-id="33247-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="33247-108">Attribute</span></span>|<span data-ttu-id="33247-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="33247-109">Attribute type</span></span>|<span data-ttu-id="33247-110">Описание</span><span class="sxs-lookup"><span data-stu-id="33247-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="33247-111">Общее</span><span class="sxs-lookup"><span data-stu-id="33247-111">General</span></span>|<span data-ttu-id="33247-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33247-112">Required attribute.</span></span> <span data-ttu-id="33247-113">Определяет имя поля.</span><span class="sxs-lookup"><span data-stu-id="33247-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="33247-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="33247-114">Reflection</span></span>|<span data-ttu-id="33247-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33247-115">Optional attribute.</span></span> <span data-ttu-id="33247-116">Определяет запрос для получения сведений о поле или перечисляет поле, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="33247-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="33247-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="33247-117">Reflection</span></span>|<span data-ttu-id="33247-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33247-118">Optional attribute.</span></span> <span data-ttu-id="33247-119">Управляет доступом среды выполнения к полю для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="33247-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="33247-120">Эта политика гарантирует, что поле можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="33247-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="33247-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="33247-121">Serialization</span></span>|<span data-ttu-id="33247-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33247-122">Optional attribute.</span></span> <span data-ttu-id="33247-123">Управляет доступом среды выполнения к полю, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как, например, сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="33247-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="33247-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="33247-124">Name attribute</span></span>  
  
|<span data-ttu-id="33247-125">Значение</span><span class="sxs-lookup"><span data-stu-id="33247-125">Value</span></span>|<span data-ttu-id="33247-126">Описание</span><span class="sxs-lookup"><span data-stu-id="33247-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33247-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="33247-127">*method_name*</span></span>|<span data-ttu-id="33247-128">Имя поля.</span><span class="sxs-lookup"><span data-stu-id="33247-128">The field name.</span></span> <span data-ttu-id="33247-129">Тип поля определяется родительским элементом [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="33247-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="33247-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="33247-130">All other attributes</span></span>  
  
|<span data-ttu-id="33247-131">Значение</span><span class="sxs-lookup"><span data-stu-id="33247-131">Value</span></span>|<span data-ttu-id="33247-132">Описание</span><span class="sxs-lookup"><span data-stu-id="33247-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33247-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="33247-133">*policy_setting*</span></span>|<span data-ttu-id="33247-134">Параметр, применяемый к этому типу политики для поля.</span><span class="sxs-lookup"><span data-stu-id="33247-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="33247-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="33247-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="33247-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="33247-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33247-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33247-137">Child Elements</span></span>  
 <span data-ttu-id="33247-138">Нет.</span><span class="sxs-lookup"><span data-stu-id="33247-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33247-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33247-139">Parent Elements</span></span>  
  
|<span data-ttu-id="33247-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="33247-140">Element</span></span>|<span data-ttu-id="33247-141">Описание</span><span class="sxs-lookup"><span data-stu-id="33247-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33247-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="33247-142">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="33247-143">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="33247-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="33247-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="33247-144">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="33247-145">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="33247-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33247-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="33247-146">Remarks</span></span>  
 <span data-ttu-id="33247-147">Если политика поля не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="33247-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33247-148">См. также</span><span class="sxs-lookup"><span data-stu-id="33247-148">See also</span></span>

- [<span data-ttu-id="33247-149">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="33247-149">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="33247-150">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="33247-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="33247-151">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="33247-151">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
