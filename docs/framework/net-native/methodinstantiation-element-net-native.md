---
title: Элемент &lt;MethodInstantiation&gt; (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d741e8df8f2b8c6d90a1d867c73495a2ffd1304
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397797"
---
# <a name="ltmethodinstantiationgt-element-net-native"></a><span data-ttu-id="0dc95-102">Элемент &lt;MethodInstantiation&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="0dc95-102">&lt;MethodInstantiation&gt; Element (.NET Native)</span></span>
<span data-ttu-id="0dc95-103">Применяет политику отражения среды выполнения к сконструированному универсальному методу.</span><span class="sxs-lookup"><span data-stu-id="0dc95-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0dc95-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0dc95-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0dc95-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0dc95-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0dc95-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0dc95-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0dc95-107">Attributes</span></span>  
  
|<span data-ttu-id="0dc95-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0dc95-108">Attribute</span></span>|<span data-ttu-id="0dc95-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="0dc95-109">Attribute type</span></span>|<span data-ttu-id="0dc95-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc95-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0dc95-111">Общие правила</span><span class="sxs-lookup"><span data-stu-id="0dc95-111">General</span></span>|<span data-ttu-id="0dc95-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0dc95-112">Required attribute.</span></span> <span data-ttu-id="0dc95-113">Задает имя метода.</span><span class="sxs-lookup"><span data-stu-id="0dc95-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="0dc95-114">Общие</span><span class="sxs-lookup"><span data-stu-id="0dc95-114">General</span></span>|<span data-ttu-id="0dc95-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0dc95-115">Optional attribute.</span></span> <span data-ttu-id="0dc95-116">Определяет именованные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="0dc95-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="0dc95-117">Несколько именованных параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="0dc95-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="0dc95-118">Атрибут `Signature` позволяет различать перегруженные методы.</span><span class="sxs-lookup"><span data-stu-id="0dc95-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="0dc95-119">Общие</span><span class="sxs-lookup"><span data-stu-id="0dc95-119">General</span></span>|<span data-ttu-id="0dc95-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0dc95-120">Required attribute.</span></span> <span data-ttu-id="0dc95-121">Задает аргументы универсального типа.</span><span class="sxs-lookup"><span data-stu-id="0dc95-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="0dc95-122">При наличии нескольких аргументов, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="0dc95-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="0dc95-123">Отражение</span><span class="sxs-lookup"><span data-stu-id="0dc95-123">Reflection</span></span>|<span data-ttu-id="0dc95-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0dc95-124">Optional attribute.</span></span> <span data-ttu-id="0dc95-125">Определяет запрос для получения сведений о методе или перечисляет методы, но не включает динамический вызов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0dc95-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="0dc95-126">Отражение</span><span class="sxs-lookup"><span data-stu-id="0dc95-126">Reflection</span></span>|<span data-ttu-id="0dc95-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0dc95-127">Optional attribute.</span></span> <span data-ttu-id="0dc95-128">Управляет доступом среды выполнения к конструктору или методу для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="0dc95-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="0dc95-129">Эта политика гарантирует, что член может быть вызван динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0dc95-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0dc95-130">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="0dc95-130">Name attribute</span></span>  
  
|<span data-ttu-id="0dc95-131">Значение</span><span class="sxs-lookup"><span data-stu-id="0dc95-131">Value</span></span>|<span data-ttu-id="0dc95-132">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc95-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0dc95-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="0dc95-133">*method_name*</span></span>|<span data-ttu-id="0dc95-134">Имя метода.</span><span class="sxs-lookup"><span data-stu-id="0dc95-134">The method name.</span></span> <span data-ttu-id="0dc95-135">Тип метода определяется родительским элементом [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) или [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="0dc95-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="0dc95-136">Сигнатура атрибута</span><span class="sxs-lookup"><span data-stu-id="0dc95-136">Signature attribute</span></span>  
  
|<span data-ttu-id="0dc95-137">Значение</span><span class="sxs-lookup"><span data-stu-id="0dc95-137">Value</span></span>|<span data-ttu-id="0dc95-138">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc95-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0dc95-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="0dc95-139">*method_signature*</span></span>|<span data-ttu-id="0dc95-140">Определяет именованные параметры метода.</span><span class="sxs-lookup"><span data-stu-id="0dc95-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="0dc95-141">При наличии нескольких параметров, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="0dc95-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="0dc95-142">Атрибут аргументов</span><span class="sxs-lookup"><span data-stu-id="0dc95-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="0dc95-143">Значение</span><span class="sxs-lookup"><span data-stu-id="0dc95-143">Value</span></span>|<span data-ttu-id="0dc95-144">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc95-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0dc95-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="0dc95-145">*method_arguments*</span></span>|<span data-ttu-id="0dc95-146">Задает аргументы универсального типа.</span><span class="sxs-lookup"><span data-stu-id="0dc95-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="0dc95-147">При наличии нескольких аргументов, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="0dc95-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="0dc95-148">Каждый аргумент должен содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="0dc95-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0dc95-149">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="0dc95-149">All other attributes</span></span>  
  
|<span data-ttu-id="0dc95-150">Значение</span><span class="sxs-lookup"><span data-stu-id="0dc95-150">Value</span></span>|<span data-ttu-id="0dc95-151">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc95-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0dc95-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0dc95-152">*policy_setting*</span></span>|<span data-ttu-id="0dc95-153">Параметр, применяемый к этому типу политики для метода.</span><span class="sxs-lookup"><span data-stu-id="0dc95-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="0dc95-154">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="0dc95-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="0dc95-155">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0dc95-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0dc95-156">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0dc95-156">Child Elements</span></span>  
 <span data-ttu-id="0dc95-157">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0dc95-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0dc95-158">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0dc95-158">Parent Elements</span></span>  
  
|<span data-ttu-id="0dc95-159">Элемент</span><span class="sxs-lookup"><span data-stu-id="0dc95-159">Element</span></span>|<span data-ttu-id="0dc95-160">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc95-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0dc95-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="0dc95-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="0dc95-162">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="0dc95-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="0dc95-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="0dc95-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="0dc95-164">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="0dc95-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0dc95-165">Примечания</span><span class="sxs-lookup"><span data-stu-id="0dc95-165">Remarks</span></span>  
 <span data-ttu-id="0dc95-166">Элемент `<MethodInstantiation>`  переопределяет политику отражения среды выполнения его соответствующего открытого универсального метода.</span><span class="sxs-lookup"><span data-stu-id="0dc95-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc95-167">См. также</span><span class="sxs-lookup"><span data-stu-id="0dc95-167">See Also</span></span>  
 [<span data-ttu-id="0dc95-168">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="0dc95-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="0dc95-169">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0dc95-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="0dc95-170">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0dc95-170">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="0dc95-171">Элемент \<Method></span><span class="sxs-lookup"><span data-stu-id="0dc95-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
