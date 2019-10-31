---
title: Элемент <Parameter> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: c6dfc347d44a794ee8496c45ca879f9daab12b22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128196"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="71e76-102">Элемент > параметра \<(.NET Native)</span><span class="sxs-lookup"><span data-stu-id="71e76-102">\<Parameter> Element (.NET Native)</span></span>
<span data-ttu-id="71e76-103">Применяет политику отражения к типу аргумента, переданного методу.</span><span class="sxs-lookup"><span data-stu-id="71e76-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e76-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71e76-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71e76-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="71e76-105">Attributes and Elements</span></span>  
 <span data-ttu-id="71e76-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="71e76-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71e76-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="71e76-107">Attributes</span></span>  
  
|<span data-ttu-id="71e76-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="71e76-108">Attribute</span></span>|<span data-ttu-id="71e76-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="71e76-109">Attribute type</span></span>|<span data-ttu-id="71e76-110">Описание</span><span class="sxs-lookup"><span data-stu-id="71e76-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="71e76-111">Общее</span><span class="sxs-lookup"><span data-stu-id="71e76-111">General</span></span>|<span data-ttu-id="71e76-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-112">Required attribute.</span></span> <span data-ttu-id="71e76-113">Имя параметра.</span><span class="sxs-lookup"><span data-stu-id="71e76-113">The parameter name.</span></span> <span data-ttu-id="71e76-114">Например, сигнатура метода `String.CompareTo(Object value)`, значение `Name` — атрибут «value».</span><span class="sxs-lookup"><span data-stu-id="71e76-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="71e76-115">Отражение</span><span class="sxs-lookup"><span data-stu-id="71e76-115">Reflection</span></span>|<span data-ttu-id="71e76-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-116">Optional attribute.</span></span> <span data-ttu-id="71e76-117">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="71e76-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="71e76-118">Отражение</span><span class="sxs-lookup"><span data-stu-id="71e76-118">Reflection</span></span>|<span data-ttu-id="71e76-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-119">Optional attribute.</span></span> <span data-ttu-id="71e76-120">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="71e76-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="71e76-121">Отражение</span><span class="sxs-lookup"><span data-stu-id="71e76-121">Reflection</span></span>|<span data-ttu-id="71e76-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-122">Optional attribute.</span></span> <span data-ttu-id="71e76-123">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="71e76-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="71e76-124">Сериализация</span><span class="sxs-lookup"><span data-stu-id="71e76-124">Serialization</span></span>|<span data-ttu-id="71e76-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-125">Optional attribute.</span></span> <span data-ttu-id="71e76-126">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="71e76-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="71e76-127">Сериализация</span><span class="sxs-lookup"><span data-stu-id="71e76-127">Serialization</span></span>|<span data-ttu-id="71e76-128">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-128">Optional attribute.</span></span> <span data-ttu-id="71e76-129">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="71e76-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="71e76-130">Сериализация</span><span class="sxs-lookup"><span data-stu-id="71e76-130">Serialization</span></span>|<span data-ttu-id="71e76-131">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-131">Optional attribute.</span></span> <span data-ttu-id="71e76-132">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="71e76-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="71e76-133">Сериализация</span><span class="sxs-lookup"><span data-stu-id="71e76-133">Serialization</span></span>|<span data-ttu-id="71e76-134">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-134">Optional attribute.</span></span> <span data-ttu-id="71e76-135">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="71e76-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="71e76-136">Interop</span><span class="sxs-lookup"><span data-stu-id="71e76-136">Interop</span></span>|<span data-ttu-id="71e76-137">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-137">Optional attribute.</span></span> <span data-ttu-id="71e76-138">Определяет политику для маршалинга ссылочных типов в WinRT и COM.</span><span class="sxs-lookup"><span data-stu-id="71e76-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="71e76-139">Interop</span><span class="sxs-lookup"><span data-stu-id="71e76-139">Interop</span></span>|<span data-ttu-id="71e76-140">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-140">Optional attribute.</span></span> <span data-ttu-id="71e76-141">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="71e76-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="71e76-142">Interop</span><span class="sxs-lookup"><span data-stu-id="71e76-142">Interop</span></span>|<span data-ttu-id="71e76-143">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="71e76-143">Optional attribute.</span></span> <span data-ttu-id="71e76-144">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="71e76-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="71e76-145">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="71e76-145">Name attribute</span></span>  
  
|<span data-ttu-id="71e76-146">значения</span><span class="sxs-lookup"><span data-stu-id="71e76-146">Value</span></span>|<span data-ttu-id="71e76-147">Описание</span><span class="sxs-lookup"><span data-stu-id="71e76-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71e76-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="71e76-148">*parameter_name*</span></span>|<span data-ttu-id="71e76-149">Имя параметра метода, к которому применяется политика.</span><span class="sxs-lookup"><span data-stu-id="71e76-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="71e76-150">Например, сигнатура метода `String.CompareTo(Object value)`, значение `Name` — атрибут «value».</span><span class="sxs-lookup"><span data-stu-id="71e76-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="71e76-151">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="71e76-151">All other attributes</span></span>  
  
|<span data-ttu-id="71e76-152">значения</span><span class="sxs-lookup"><span data-stu-id="71e76-152">Value</span></span>|<span data-ttu-id="71e76-153">Описание</span><span class="sxs-lookup"><span data-stu-id="71e76-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71e76-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="71e76-154">*policy_setting*</span></span>|<span data-ttu-id="71e76-155">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="71e76-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="71e76-156">Допустимые значения: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="71e76-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="71e76-157">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="71e76-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71e76-158">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="71e76-158">Child Elements</span></span>  
 <span data-ttu-id="71e76-159">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="71e76-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71e76-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="71e76-160">Parent Elements</span></span>  
  
|<span data-ttu-id="71e76-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="71e76-161">Element</span></span>|<span data-ttu-id="71e76-162">Описание</span><span class="sxs-lookup"><span data-stu-id="71e76-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71e76-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="71e76-163">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="71e76-164">Применяет политику отражения среды выполнения к конструктору или методу.</span><span class="sxs-lookup"><span data-stu-id="71e76-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71e76-165">Заметки</span><span class="sxs-lookup"><span data-stu-id="71e76-165">Remarks</span></span>  
 <span data-ttu-id="71e76-166">Элемент `<Parameter>` является дочерним по отношению к элементу [\<Method>](method-element-net-native.md) и используется для применения политики к конкретному параметру метода.</span><span class="sxs-lookup"><span data-stu-id="71e76-166">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="71e76-167">Конкретный параметр метода указывается по имени, а не по типу.</span><span class="sxs-lookup"><span data-stu-id="71e76-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="71e76-168">По крайней мере один атрибут, который представляет тип политики, такие как `Activate` или `Dynamic`, должен присутствовать.</span><span class="sxs-lookup"><span data-stu-id="71e76-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e76-169">См. также</span><span class="sxs-lookup"><span data-stu-id="71e76-169">See also</span></span>

- [<span data-ttu-id="71e76-170">Элемент \<Method></span><span class="sxs-lookup"><span data-stu-id="71e76-170">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="71e76-171">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="71e76-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="71e76-172">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="71e76-172">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="71e76-173">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="71e76-173">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
