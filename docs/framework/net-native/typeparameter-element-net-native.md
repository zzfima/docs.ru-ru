---
title: <TypeParameter>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0de00b9313b60b3a527dd0380ae90d82731a8c02
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049066"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="81052-102">\<Элемент > typeparameter находится вне (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="81052-102">\<TypeParameter> Element (.NET Native)</span></span>
<span data-ttu-id="81052-103">Применяет политику к типу, представленному аргументом типа , переданным методу.</span><span class="sxs-lookup"><span data-stu-id="81052-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81052-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81052-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81052-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="81052-105">Attributes and Elements</span></span>  
 <span data-ttu-id="81052-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="81052-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81052-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="81052-107">Attributes</span></span>  
  
|<span data-ttu-id="81052-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="81052-108">Attribute</span></span>|<span data-ttu-id="81052-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="81052-109">Attribute type</span></span>|<span data-ttu-id="81052-110">Описание</span><span class="sxs-lookup"><span data-stu-id="81052-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="81052-111">Общее</span><span class="sxs-lookup"><span data-stu-id="81052-111">General</span></span>|<span data-ttu-id="81052-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-112">Required attribute.</span></span> <span data-ttu-id="81052-113">Имя типа параметра типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="81052-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="81052-114">Например, для сигнатуры метода `Type.GetInterfaceMap(Type interfaceType)`, значение атрибута `Name` — "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="81052-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="81052-115">Отражение</span><span class="sxs-lookup"><span data-stu-id="81052-115">Reflection</span></span>|<span data-ttu-id="81052-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-116">Optional attribute.</span></span> <span data-ttu-id="81052-117">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="81052-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="81052-118">Отражение</span><span class="sxs-lookup"><span data-stu-id="81052-118">Reflection</span></span>|<span data-ttu-id="81052-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-119">Optional attribute.</span></span> <span data-ttu-id="81052-120">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="81052-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="81052-121">Отражение</span><span class="sxs-lookup"><span data-stu-id="81052-121">Reflection</span></span>|<span data-ttu-id="81052-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-122">Optional attribute.</span></span> <span data-ttu-id="81052-123">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="81052-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="81052-124">Сериализация</span><span class="sxs-lookup"><span data-stu-id="81052-124">Serialization</span></span>|<span data-ttu-id="81052-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-125">Optional attribute.</span></span> <span data-ttu-id="81052-126">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="81052-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="81052-127">Сериализация</span><span class="sxs-lookup"><span data-stu-id="81052-127">Serialization</span></span>|<span data-ttu-id="81052-128">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-128">Optional attribute.</span></span> <span data-ttu-id="81052-129">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="81052-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="81052-130">Сериализация</span><span class="sxs-lookup"><span data-stu-id="81052-130">Serialization</span></span>|<span data-ttu-id="81052-131">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-131">Optional attribute.</span></span> <span data-ttu-id="81052-132">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="81052-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="81052-133">Сериализация</span><span class="sxs-lookup"><span data-stu-id="81052-133">Serialization</span></span>|<span data-ttu-id="81052-134">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-134">Optional attribute.</span></span> <span data-ttu-id="81052-135">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="81052-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="81052-136">Interop</span><span class="sxs-lookup"><span data-stu-id="81052-136">Interop</span></span>|<span data-ttu-id="81052-137">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-137">Optional attribute.</span></span> <span data-ttu-id="81052-138">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="81052-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="81052-139">Interop</span><span class="sxs-lookup"><span data-stu-id="81052-139">Interop</span></span>|<span data-ttu-id="81052-140">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-140">Optional attribute.</span></span> <span data-ttu-id="81052-141">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="81052-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="81052-142">Interop</span><span class="sxs-lookup"><span data-stu-id="81052-142">Interop</span></span>|<span data-ttu-id="81052-143">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="81052-143">Optional attribute.</span></span> <span data-ttu-id="81052-144">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="81052-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="81052-145">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="81052-145">Name attribute</span></span>  
  
|<span data-ttu-id="81052-146">Значение</span><span class="sxs-lookup"><span data-stu-id="81052-146">Value</span></span>|<span data-ttu-id="81052-147">Описание</span><span class="sxs-lookup"><span data-stu-id="81052-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="81052-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="81052-148">*parameter_name*</span></span>|<span data-ttu-id="81052-149">Имя типа параметра типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="81052-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="81052-150">Например, для сигнатуры метода `Type.GetInterfaceMap(Type interfaceType)`, значение атрибута `Name` — "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="81052-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="81052-151">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="81052-151">All other attributes</span></span>  
  
|<span data-ttu-id="81052-152">Значение</span><span class="sxs-lookup"><span data-stu-id="81052-152">Value</span></span>|<span data-ttu-id="81052-153">Описание</span><span class="sxs-lookup"><span data-stu-id="81052-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="81052-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="81052-154">*policy_setting*</span></span>|<span data-ttu-id="81052-155">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="81052-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="81052-156">Допустимые значения: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="81052-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="81052-157">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="81052-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81052-158">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="81052-158">Child Elements</span></span>  
 <span data-ttu-id="81052-159">Нет.</span><span class="sxs-lookup"><span data-stu-id="81052-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81052-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="81052-160">Parent Elements</span></span>  
  
|<span data-ttu-id="81052-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="81052-161">Element</span></span>|<span data-ttu-id="81052-162">Описание</span><span class="sxs-lookup"><span data-stu-id="81052-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81052-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="81052-163">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="81052-164">Применяет политику отражения среды выполнения к конструктору или методу.</span><span class="sxs-lookup"><span data-stu-id="81052-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81052-165">Примечания</span><span class="sxs-lookup"><span data-stu-id="81052-165">Remarks</span></span>  
 <span data-ttu-id="81052-166">Элемент `<TypeParameter>` аналогичен элементу [\<Parameter>](parameter-element-net-native.md), за исключением того, что он может применяться только для параметров типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="81052-166">The `<TypeParameter>` element is similar to the [\<Parameter>](parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="81052-167">Применяет политику, независимо от представленного типа во время выполнения по аргументу типа, указанному атрибутом `Name`.</span><span class="sxs-lookup"><span data-stu-id="81052-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="81052-168">Например, сериализатор NewtonSoft JSON включает статический метод `JsonConvert.DeserializeObject(String value, Type type)`.</span><span class="sxs-lookup"><span data-stu-id="81052-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="81052-169">Следующие директивы отражения:</span><span class="sxs-lookup"><span data-stu-id="81052-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="81052-170">определяют, что метаданные для типа среды выполнения, представленные аргументом `type`, должны быть доступны для сериализации.</span><span class="sxs-lookup"><span data-stu-id="81052-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="81052-171">Если применить эти директивы среды выполнения к проекту, который включает следующий исходный код:</span><span class="sxs-lookup"><span data-stu-id="81052-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="81052-172">директивы отражения делают метаданные для типа `StockQuote` доступными для сериализатора NewtonSoft JSON во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="81052-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81052-173">См. также</span><span class="sxs-lookup"><span data-stu-id="81052-173">See also</span></span>

- [<span data-ttu-id="81052-174">Элемент \<Method></span><span class="sxs-lookup"><span data-stu-id="81052-174">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="81052-175">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="81052-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="81052-176">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="81052-176">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="81052-177">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="81052-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
