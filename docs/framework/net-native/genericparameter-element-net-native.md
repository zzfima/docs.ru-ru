---
title: Элемент &lt;GenericParameter&gt; (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd0d9851f62381a16f628607c326c6690492628b
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347855"
---
# <a name="ltgenericparametergt-element-net-native"></a><span data-ttu-id="4df77-102">Элемент &lt;GenericParameter&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="4df77-102">&lt;GenericParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="4df77-103">Применяет политику к параметру типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="4df77-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4df77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4df77-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4df77-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4df77-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4df77-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4df77-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4df77-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4df77-107">Attributes</span></span>  
  
|<span data-ttu-id="4df77-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4df77-108">Attribute</span></span>|<span data-ttu-id="4df77-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="4df77-109">Attribute type</span></span>|<span data-ttu-id="4df77-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4df77-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="4df77-111">Общие правила</span><span class="sxs-lookup"><span data-stu-id="4df77-111">General</span></span>|<span data-ttu-id="4df77-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-112">Required attribute.</span></span> <span data-ttu-id="4df77-113">Имя универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="4df77-113">The name of the generic parameter.</span></span> <span data-ttu-id="4df77-114">Например, для универсального делегата <xref:System.Func%603>, значение атрибута `Name` равно «TResult» для применения политики среды выполнения к возвращаемому значению делегата.</span><span class="sxs-lookup"><span data-stu-id="4df77-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="4df77-115">Отражение</span><span class="sxs-lookup"><span data-stu-id="4df77-115">Reflection</span></span>|<span data-ttu-id="4df77-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-116">Optional attribute.</span></span> <span data-ttu-id="4df77-117">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4df77-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="4df77-118">Отражение</span><span class="sxs-lookup"><span data-stu-id="4df77-118">Reflection</span></span>|<span data-ttu-id="4df77-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-119">Optional attribute.</span></span> <span data-ttu-id="4df77-120">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4df77-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="4df77-121">Отражение</span><span class="sxs-lookup"><span data-stu-id="4df77-121">Reflection</span></span>|<span data-ttu-id="4df77-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-122">Optional attribute.</span></span> <span data-ttu-id="4df77-123">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="4df77-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="4df77-124">Сериализация</span><span class="sxs-lookup"><span data-stu-id="4df77-124">Serialization</span></span>|<span data-ttu-id="4df77-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-125">Optional attribute.</span></span> <span data-ttu-id="4df77-126">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="4df77-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="4df77-127">Сериализация</span><span class="sxs-lookup"><span data-stu-id="4df77-127">Serialization</span></span>|<span data-ttu-id="4df77-128">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-128">Optional attribute.</span></span> <span data-ttu-id="4df77-129">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4df77-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="4df77-130">Сериализация</span><span class="sxs-lookup"><span data-stu-id="4df77-130">Serialization</span></span>|<span data-ttu-id="4df77-131">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-131">Optional attribute.</span></span> <span data-ttu-id="4df77-132">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4df77-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="4df77-133">Сериализация</span><span class="sxs-lookup"><span data-stu-id="4df77-133">Serialization</span></span>|<span data-ttu-id="4df77-134">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-134">Optional attribute.</span></span> <span data-ttu-id="4df77-135">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4df77-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="4df77-136">Interop</span><span class="sxs-lookup"><span data-stu-id="4df77-136">Interop</span></span>|<span data-ttu-id="4df77-137">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-137">Optional attribute.</span></span> <span data-ttu-id="4df77-138">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="4df77-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="4df77-139">Interop</span><span class="sxs-lookup"><span data-stu-id="4df77-139">Interop</span></span>|<span data-ttu-id="4df77-140">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-140">Optional attribute.</span></span> <span data-ttu-id="4df77-141">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="4df77-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="4df77-142">Interop</span><span class="sxs-lookup"><span data-stu-id="4df77-142">Interop</span></span>|<span data-ttu-id="4df77-143">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-143">Optional attribute.</span></span> <span data-ttu-id="4df77-144">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="4df77-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="4df77-145">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="4df77-145">Name attribute</span></span>  
  
|<span data-ttu-id="4df77-146">Значение</span><span class="sxs-lookup"><span data-stu-id="4df77-146">Value</span></span>|<span data-ttu-id="4df77-147">Описание</span><span class="sxs-lookup"><span data-stu-id="4df77-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4df77-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="4df77-148">*generic_parameter_name*</span></span>|<span data-ttu-id="4df77-149">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4df77-149">Required attribute.</span></span> <span data-ttu-id="4df77-150">Имя универсального параметра типа.</span><span class="sxs-lookup"><span data-stu-id="4df77-150">The name of the generic type parameter.</span></span> <span data-ttu-id="4df77-151">Например, для универсального делегата <xref:System.Func%603> значение *generic_parameter_name*, равное "TResult", применяет политику среды выполнения к возвращаемому значению делегата.</span><span class="sxs-lookup"><span data-stu-id="4df77-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="4df77-152">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="4df77-152">All other attributes</span></span>  
  
|<span data-ttu-id="4df77-153">Значение</span><span class="sxs-lookup"><span data-stu-id="4df77-153">Value</span></span>|<span data-ttu-id="4df77-154">Описание</span><span class="sxs-lookup"><span data-stu-id="4df77-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4df77-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="4df77-155">*policy_setting*</span></span>|<span data-ttu-id="4df77-156">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="4df77-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="4df77-157">Допустимые значения: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="4df77-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="4df77-158">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4df77-158">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4df77-159">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4df77-159">Child Elements</span></span>  
 <span data-ttu-id="4df77-160">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4df77-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4df77-161">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4df77-161">Parent Elements</span></span>  
  
|<span data-ttu-id="4df77-162">Элемент</span><span class="sxs-lookup"><span data-stu-id="4df77-162">Element</span></span>|<span data-ttu-id="4df77-163">Описание</span><span class="sxs-lookup"><span data-stu-id="4df77-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4df77-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="4df77-164">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="4df77-165">Применяет политику отражения среды выполнения к конструктору или методу.</span><span class="sxs-lookup"><span data-stu-id="4df77-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="4df77-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="4df77-166">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="4df77-167">Применяет политику отражения среды выполнения для конкретного типа, например, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4df77-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4df77-168">Примечания</span><span class="sxs-lookup"><span data-stu-id="4df77-168">Remarks</span></span>  
 <span data-ttu-id="4df77-169">Элемент `<GenericParameter>` является дочерним для элемента [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) или [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) и используется для применения политики к определенному параметру универсального типа, который задается его именем в сигнатуре универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="4df77-169">The `<GenericParameter>` element is a child of either the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="4df77-170">Элемент `<GenericParameter>` особенно полезен при использовании сериализаторов.</span><span class="sxs-lookup"><span data-stu-id="4df77-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="4df77-171">В следующем примере используется элемент `<GenericParameter>`, который позволяет применить политику к типу `T` в вызовах к перегрузкам метода [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) сериализатора NewtonSoft JSON.</span><span class="sxs-lookup"><span data-stu-id="4df77-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4df77-172">См. также</span><span class="sxs-lookup"><span data-stu-id="4df77-172">See Also</span></span>  
 [<span data-ttu-id="4df77-173">Элемент \<Method></span><span class="sxs-lookup"><span data-stu-id="4df77-173">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="4df77-174">\<Тип > элемент</span><span class="sxs-lookup"><span data-stu-id="4df77-174">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="4df77-175">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="4df77-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="4df77-176">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4df77-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="4df77-177">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4df77-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
