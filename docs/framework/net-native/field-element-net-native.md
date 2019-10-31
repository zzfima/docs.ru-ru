---
title: Элемент <Field> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: 2a63b88c399a999cd00750dee1614352cea10e80
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128419"
---
# <a name="field-element-net-native"></a><span data-ttu-id="160db-102">Элемент > \<поля (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="160db-102">\<Field> Element (.NET Native)</span></span>
<span data-ttu-id="160db-103">Применяет политику отражения среды выполнения к полю.</span><span class="sxs-lookup"><span data-stu-id="160db-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="160db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="160db-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="160db-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="160db-105">Attributes and Elements</span></span>  
 <span data-ttu-id="160db-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="160db-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="160db-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="160db-107">Attributes</span></span>  
  
|<span data-ttu-id="160db-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="160db-108">Attribute</span></span>|<span data-ttu-id="160db-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="160db-109">Attribute type</span></span>|<span data-ttu-id="160db-110">Описание</span><span class="sxs-lookup"><span data-stu-id="160db-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="160db-111">Общее</span><span class="sxs-lookup"><span data-stu-id="160db-111">General</span></span>|<span data-ttu-id="160db-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="160db-112">Required attribute.</span></span> <span data-ttu-id="160db-113">Определяет имя поля.</span><span class="sxs-lookup"><span data-stu-id="160db-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="160db-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="160db-114">Reflection</span></span>|<span data-ttu-id="160db-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="160db-115">Optional attribute.</span></span> <span data-ttu-id="160db-116">Определяет запрос для получения сведений о поле или перечисляет поле, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="160db-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="160db-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="160db-117">Reflection</span></span>|<span data-ttu-id="160db-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="160db-118">Optional attribute.</span></span> <span data-ttu-id="160db-119">Управляет доступом среды выполнения к полю для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="160db-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="160db-120">Эта политика гарантирует, что поле можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="160db-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="160db-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="160db-121">Serialization</span></span>|<span data-ttu-id="160db-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="160db-122">Optional attribute.</span></span> <span data-ttu-id="160db-123">Управляет доступом среды выполнения к полю, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как, например, сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="160db-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="160db-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="160db-124">Name attribute</span></span>  
  
|<span data-ttu-id="160db-125">значения</span><span class="sxs-lookup"><span data-stu-id="160db-125">Value</span></span>|<span data-ttu-id="160db-126">Описание</span><span class="sxs-lookup"><span data-stu-id="160db-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="160db-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="160db-127">*method_name*</span></span>|<span data-ttu-id="160db-128">Имя поля.</span><span class="sxs-lookup"><span data-stu-id="160db-128">The field name.</span></span> <span data-ttu-id="160db-129">Тип поля определяется родительским элементом [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="160db-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="160db-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="160db-130">All other attributes</span></span>  
  
|<span data-ttu-id="160db-131">значения</span><span class="sxs-lookup"><span data-stu-id="160db-131">Value</span></span>|<span data-ttu-id="160db-132">Описание</span><span class="sxs-lookup"><span data-stu-id="160db-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="160db-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="160db-133">*policy_setting*</span></span>|<span data-ttu-id="160db-134">Параметр, применяемый к этому типу политики для поля.</span><span class="sxs-lookup"><span data-stu-id="160db-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="160db-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="160db-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="160db-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="160db-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="160db-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="160db-137">Child Elements</span></span>  
 <span data-ttu-id="160db-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="160db-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="160db-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="160db-139">Parent Elements</span></span>  
  
|<span data-ttu-id="160db-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="160db-140">Element</span></span>|<span data-ttu-id="160db-141">Описание</span><span class="sxs-lookup"><span data-stu-id="160db-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="160db-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="160db-142">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="160db-143">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="160db-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="160db-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="160db-144">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="160db-145">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="160db-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="160db-146">Заметки</span><span class="sxs-lookup"><span data-stu-id="160db-146">Remarks</span></span>  
 <span data-ttu-id="160db-147">Если политика поля не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="160db-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="160db-148">См. также</span><span class="sxs-lookup"><span data-stu-id="160db-148">See also</span></span>

- [<span data-ttu-id="160db-149">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="160db-149">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="160db-150">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="160db-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="160db-151">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="160db-151">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
