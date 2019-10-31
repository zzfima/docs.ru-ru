---
title: Элемент <MethodInstantiation> (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: f19bd3c20088431bcbbafac298398b82a664bee9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128328"
---
# <a name="methodinstantiation-element-net-native"></a><span data-ttu-id="a8a0e-102">Элемент \<MethodInstantiation > (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="a8a0e-102">\<MethodInstantiation> Element (.NET Native)</span></span>
<span data-ttu-id="a8a0e-103">Применяет политику отражения среды выполнения к сконструированному универсальному методу.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a0e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8a0e-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8a0e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8a0e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a8a0e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8a0e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8a0e-107">Attributes</span></span>  
  
|<span data-ttu-id="a8a0e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a8a0e-108">Attribute</span></span>|<span data-ttu-id="a8a0e-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="a8a0e-109">Attribute type</span></span>|<span data-ttu-id="a8a0e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a8a0e-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="a8a0e-111">Общее</span><span class="sxs-lookup"><span data-stu-id="a8a0e-111">General</span></span>|<span data-ttu-id="a8a0e-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-112">Required attribute.</span></span> <span data-ttu-id="a8a0e-113">Задает имя метода.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="a8a0e-114">Общее</span><span class="sxs-lookup"><span data-stu-id="a8a0e-114">General</span></span>|<span data-ttu-id="a8a0e-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-115">Optional attribute.</span></span> <span data-ttu-id="a8a0e-116">Определяет именованные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="a8a0e-117">Несколько именованных параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="a8a0e-118">Атрибут `Signature` позволяет различать перегруженные методы.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="a8a0e-119">Общее</span><span class="sxs-lookup"><span data-stu-id="a8a0e-119">General</span></span>|<span data-ttu-id="a8a0e-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-120">Required attribute.</span></span> <span data-ttu-id="a8a0e-121">Задает аргументы универсального типа.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="a8a0e-122">При наличии нескольких аргументов, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="a8a0e-123">Отражение</span><span class="sxs-lookup"><span data-stu-id="a8a0e-123">Reflection</span></span>|<span data-ttu-id="a8a0e-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-124">Optional attribute.</span></span> <span data-ttu-id="a8a0e-125">Определяет запрос для получения сведений о методе или перечисляет методы, но не включает динамический вызов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="a8a0e-126">Отражение</span><span class="sxs-lookup"><span data-stu-id="a8a0e-126">Reflection</span></span>|<span data-ttu-id="a8a0e-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-127">Optional attribute.</span></span> <span data-ttu-id="a8a0e-128">Управляет доступом среды выполнения к конструктору или методу для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="a8a0e-129">Эта политика гарантирует, что член может быть вызван динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="a8a0e-130">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="a8a0e-130">Name attribute</span></span>  
  
|<span data-ttu-id="a8a0e-131">значения</span><span class="sxs-lookup"><span data-stu-id="a8a0e-131">Value</span></span>|<span data-ttu-id="a8a0e-132">Описание</span><span class="sxs-lookup"><span data-stu-id="a8a0e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a8a0e-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="a8a0e-133">*method_name*</span></span>|<span data-ttu-id="a8a0e-134">Имя метода.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-134">The method name.</span></span> <span data-ttu-id="a8a0e-135">Тип метода определяется родительским элементом [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a8a0e-135">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="a8a0e-136">Сигнатура атрибута</span><span class="sxs-lookup"><span data-stu-id="a8a0e-136">Signature attribute</span></span>  
  
|<span data-ttu-id="a8a0e-137">значения</span><span class="sxs-lookup"><span data-stu-id="a8a0e-137">Value</span></span>|<span data-ttu-id="a8a0e-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a8a0e-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a8a0e-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="a8a0e-139">*method_signature*</span></span>|<span data-ttu-id="a8a0e-140">Определяет именованные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="a8a0e-141">При наличии нескольких параметров, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="a8a0e-142">Атрибут аргументов</span><span class="sxs-lookup"><span data-stu-id="a8a0e-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="a8a0e-143">значения</span><span class="sxs-lookup"><span data-stu-id="a8a0e-143">Value</span></span>|<span data-ttu-id="a8a0e-144">Описание</span><span class="sxs-lookup"><span data-stu-id="a8a0e-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a8a0e-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="a8a0e-145">*method_arguments*</span></span>|<span data-ttu-id="a8a0e-146">Задает аргументы универсального типа.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="a8a0e-147">При наличии нескольких аргументов, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="a8a0e-148">Каждый аргумент должен содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="a8a0e-149">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8a0e-149">All other attributes</span></span>  
  
|<span data-ttu-id="a8a0e-150">значения</span><span class="sxs-lookup"><span data-stu-id="a8a0e-150">Value</span></span>|<span data-ttu-id="a8a0e-151">Описание</span><span class="sxs-lookup"><span data-stu-id="a8a0e-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a8a0e-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="a8a0e-152">*policy_setting*</span></span>|<span data-ttu-id="a8a0e-153">Параметр, применяемый к этому типу политики для метода.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="a8a0e-154">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="a8a0e-155">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a8a0e-155">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8a0e-156">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8a0e-156">Child Elements</span></span>  
 <span data-ttu-id="a8a0e-157">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8a0e-158">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8a0e-158">Parent Elements</span></span>  
  
|<span data-ttu-id="a8a0e-159">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8a0e-159">Element</span></span>|<span data-ttu-id="a8a0e-160">Описание</span><span class="sxs-lookup"><span data-stu-id="a8a0e-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8a0e-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="a8a0e-161">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="a8a0e-162">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="a8a0e-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="a8a0e-163">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="a8a0e-164">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8a0e-165">Заметки</span><span class="sxs-lookup"><span data-stu-id="a8a0e-165">Remarks</span></span>  
 <span data-ttu-id="a8a0e-166">Элемент `<MethodInstantiation>`  переопределяет политику отражения среды выполнения его соответствующего открытого универсального метода.</span><span class="sxs-lookup"><span data-stu-id="a8a0e-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a0e-167">См. также</span><span class="sxs-lookup"><span data-stu-id="a8a0e-167">See also</span></span>

- [<span data-ttu-id="a8a0e-168">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="a8a0e-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="a8a0e-169">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a8a0e-169">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="a8a0e-170">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a8a0e-170">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="a8a0e-171">Элемент \<Method></span><span class="sxs-lookup"><span data-stu-id="a8a0e-171">\<Method> Element</span></span>](method-element-net-native.md)
