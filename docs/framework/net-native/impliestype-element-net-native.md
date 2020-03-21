---
title: <ImpliesType>Элемент (.NET Родной)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 57f4208233cd5e8544b4f1c254e3b0e0eaacd508
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181006"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="76d33-102">\<ПодразумеваетТип> элемент (.NET Родной)</span><span class="sxs-lookup"><span data-stu-id="76d33-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="76d33-103">Применяет политику к типу, если политика была применена к содержащему типу или методу.</span><span class="sxs-lookup"><span data-stu-id="76d33-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76d33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76d33-104">Syntax</span></span>  
  
```xml
<ImpliesType Name="type_name"  
             Activate="policy_type"  
             Browse="policy_type"  
             Dynamic="policy_type"  
             Serialize="policy_type"
             DataContractSerializer="policy_setting"  
             DataContractJsonSerializer="policy_setting"  
             XmlSerializer="policy_setting"  
             MarshalObject="policy_setting"  
             MarshalDelegate="policy_setting"  
             MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76d33-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="76d33-105">Attributes and Elements</span></span>  
 <span data-ttu-id="76d33-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="76d33-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76d33-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="76d33-107">Attributes</span></span>  
  
|<span data-ttu-id="76d33-108">attribute</span><span class="sxs-lookup"><span data-stu-id="76d33-108">Attribute</span></span>|<span data-ttu-id="76d33-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="76d33-109">Attribute type</span></span>|<span data-ttu-id="76d33-110">Описание</span><span class="sxs-lookup"><span data-stu-id="76d33-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="76d33-111">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="76d33-111">General</span></span>|<span data-ttu-id="76d33-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-112">Required attribute.</span></span> <span data-ttu-id="76d33-113">Указывает имя типа.</span><span class="sxs-lookup"><span data-stu-id="76d33-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="76d33-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="76d33-114">Reflection</span></span>|<span data-ttu-id="76d33-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-115">Optional attribute.</span></span> <span data-ttu-id="76d33-116">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="76d33-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="76d33-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="76d33-117">Reflection</span></span>|<span data-ttu-id="76d33-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-118">Optional attribute.</span></span> <span data-ttu-id="76d33-119">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="76d33-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="76d33-120">Отражение</span><span class="sxs-lookup"><span data-stu-id="76d33-120">Reflection</span></span>|<span data-ttu-id="76d33-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-121">Optional attribute.</span></span> <span data-ttu-id="76d33-122">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="76d33-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="76d33-123">Сериализация</span><span class="sxs-lookup"><span data-stu-id="76d33-123">Serialization</span></span>|<span data-ttu-id="76d33-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-124">Optional attribute.</span></span> <span data-ttu-id="76d33-125">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="76d33-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="76d33-126">Сериализация</span><span class="sxs-lookup"><span data-stu-id="76d33-126">Serialization</span></span>|<span data-ttu-id="76d33-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-127">Optional attribute.</span></span> <span data-ttu-id="76d33-128">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76d33-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="76d33-129">Сериализация</span><span class="sxs-lookup"><span data-stu-id="76d33-129">Serialization</span></span>|<span data-ttu-id="76d33-130">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-130">Optional attribute.</span></span> <span data-ttu-id="76d33-131">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76d33-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="76d33-132">Сериализация</span><span class="sxs-lookup"><span data-stu-id="76d33-132">Serialization</span></span>|<span data-ttu-id="76d33-133">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-133">Optional attribute.</span></span> <span data-ttu-id="76d33-134">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76d33-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="76d33-135">Interop</span><span class="sxs-lookup"><span data-stu-id="76d33-135">Interop</span></span>|<span data-ttu-id="76d33-136">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-136">Optional attribute.</span></span> <span data-ttu-id="76d33-137">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="76d33-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="76d33-138">Interop</span><span class="sxs-lookup"><span data-stu-id="76d33-138">Interop</span></span>|<span data-ttu-id="76d33-139">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-139">Optional attribute.</span></span> <span data-ttu-id="76d33-140">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="76d33-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="76d33-141">Interop</span><span class="sxs-lookup"><span data-stu-id="76d33-141">Interop</span></span>|<span data-ttu-id="76d33-142">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d33-142">Optional attribute.</span></span> <span data-ttu-id="76d33-143">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="76d33-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="76d33-144">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="76d33-144">Name attribute</span></span>  
  
|<span data-ttu-id="76d33-145">Значение</span><span class="sxs-lookup"><span data-stu-id="76d33-145">Value</span></span>|<span data-ttu-id="76d33-146">Описание</span><span class="sxs-lookup"><span data-stu-id="76d33-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="76d33-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="76d33-147">*type_name*</span></span>|<span data-ttu-id="76d33-148">Имя типа.</span><span class="sxs-lookup"><span data-stu-id="76d33-148">The type name.</span></span> <span data-ttu-id="76d33-149">Если тип, представленный этим элементом `<ImpliesType>`, находится в том же пространстве имен, что и содержащий его элемент `<Type>`, атрибут *type_name* может содержать имя типа без пространства имен.</span><span class="sxs-lookup"><span data-stu-id="76d33-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="76d33-150">В противном случае атрибут *type_name* должен содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="76d33-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="76d33-151">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="76d33-151">All other attributes</span></span>  
  
|<span data-ttu-id="76d33-152">Значение</span><span class="sxs-lookup"><span data-stu-id="76d33-152">Value</span></span>|<span data-ttu-id="76d33-153">Описание</span><span class="sxs-lookup"><span data-stu-id="76d33-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="76d33-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="76d33-154">*policy_setting*</span></span>|<span data-ttu-id="76d33-155">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="76d33-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="76d33-156">Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="76d33-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="76d33-157">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="76d33-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76d33-158">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="76d33-158">Child Elements</span></span>  
 <span data-ttu-id="76d33-159">Нет.</span><span class="sxs-lookup"><span data-stu-id="76d33-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76d33-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="76d33-160">Parent Elements</span></span>  
  
|<span data-ttu-id="76d33-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="76d33-161">Element</span></span>|<span data-ttu-id="76d33-162">Описание</span><span class="sxs-lookup"><span data-stu-id="76d33-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76d33-163">\<Тип></span><span class="sxs-lookup"><span data-stu-id="76d33-163">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="76d33-164">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="76d33-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="76d33-165">\<>typeInstantiation</span><span class="sxs-lookup"><span data-stu-id="76d33-165">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="76d33-166">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="76d33-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="76d33-167">\<Метод></span><span class="sxs-lookup"><span data-stu-id="76d33-167">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="76d33-168">Применяет политику отражения к методу.</span><span class="sxs-lookup"><span data-stu-id="76d33-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76d33-169">Remarks</span><span class="sxs-lookup"><span data-stu-id="76d33-169">Remarks</span></span>  
 <span data-ttu-id="76d33-170">Элемент `<ImpliesType>` в основном предназначен для использования в библиотеках.</span><span class="sxs-lookup"><span data-stu-id="76d33-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="76d33-171">Он используется в следующем сценарии:</span><span class="sxs-lookup"><span data-stu-id="76d33-171">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="76d33-172">Если процедура должна отражаться на одном типе, она обязательно должна отражаться на втором типе</span><span class="sxs-lookup"><span data-stu-id="76d33-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="76d33-173">В противном случае метаданные для корректной реализации второго типа недоступны, так как статический анализ не указывает, что это необходимо.</span><span class="sxs-lookup"><span data-stu-id="76d33-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="76d33-174">Чаще всего двумя типами являются универсальные экземпляры общих аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="76d33-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="76d33-175">Элемент `<ImpliesType>` был определен исходя из предположения, что необходимость отражения в тип, заданный родительским элементом, предполагает необходимость отражения в тип, заданный элементом `<ImpliesType>`.</span><span class="sxs-lookup"><span data-stu-id="76d33-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="76d33-176">Например, для двух типов применяются следующие директивы отражения `Explicit<T>` и `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="76d33-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="76d33-177">Эта директива не действует, пока экземпляр `Explicit` не определил параметр политики `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="76d33-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="76d33-178">Например, если это так, для `Explicit<Int32>`, `Implicit<Int32>` создается экземпляр с открытыми корневыми членами, а их метаданные становятся доступными для динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="76d33-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="76d33-179">Ниже приведен реальный пример, который применяется по крайней мере к одному сериализатору.</span><span class="sxs-lookup"><span data-stu-id="76d33-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="76d33-180">Директивы фиксируют требование, которое отражается на чем-то `IList<`набранном как *что-то,* `>` также включает в себя отражение соответствующего `List<` *типа,* `>` не требуя аннотации к приложению.</span><span class="sxs-lookup"><span data-stu-id="76d33-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="76d33-181">Элемент `<ImpliesType>` может также отображаться в элементе `<Method>`, так как в некоторых случаях создание экземпляров универсального метода подразумевает отражение на экземпляре типа.</span><span class="sxs-lookup"><span data-stu-id="76d33-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="76d33-182">Например, представьте универсальный метод `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)`, к которому заданная библиотека будет обращаться динамически вместе со связанными типами <xref:System.Collections.Generic.List%601> и <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="76d33-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="76d33-183">Это можно выразить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="76d33-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76d33-184">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="76d33-184">See also</span></span>

- [<span data-ttu-id="76d33-185">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="76d33-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="76d33-186">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="76d33-186">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="76d33-187">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="76d33-187">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
