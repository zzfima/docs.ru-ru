---
title: <GenericParameter>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2898d804f7a351045b2fbce42042f9fd322ebb0a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049744"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="ea7b8-102">\<Элемент > GenericParameter (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="ea7b8-102">\<GenericParameter> Element (.NET Native)</span></span>
<span data-ttu-id="ea7b8-103">Применяет политику к параметру типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea7b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea7b8-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea7b8-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea7b8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ea7b8-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea7b8-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea7b8-107">Attributes</span></span>  
  
|<span data-ttu-id="ea7b8-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea7b8-108">Attribute</span></span>|<span data-ttu-id="ea7b8-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="ea7b8-109">Attribute type</span></span>|<span data-ttu-id="ea7b8-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ea7b8-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="ea7b8-111">Общее</span><span class="sxs-lookup"><span data-stu-id="ea7b8-111">General</span></span>|<span data-ttu-id="ea7b8-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-112">Required attribute.</span></span> <span data-ttu-id="ea7b8-113">Имя универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-113">The name of the generic parameter.</span></span> <span data-ttu-id="ea7b8-114">Например, для универсального делегата <xref:System.Func%603>, значение атрибута `Name` равно «TResult» для применения политики среды выполнения к возвращаемому значению делегата.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="ea7b8-115">Отражение</span><span class="sxs-lookup"><span data-stu-id="ea7b8-115">Reflection</span></span>|<span data-ttu-id="ea7b8-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-116">Optional attribute.</span></span> <span data-ttu-id="ea7b8-117">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="ea7b8-118">Отражение</span><span class="sxs-lookup"><span data-stu-id="ea7b8-118">Reflection</span></span>|<span data-ttu-id="ea7b8-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-119">Optional attribute.</span></span> <span data-ttu-id="ea7b8-120">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="ea7b8-121">Отражение</span><span class="sxs-lookup"><span data-stu-id="ea7b8-121">Reflection</span></span>|<span data-ttu-id="ea7b8-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-122">Optional attribute.</span></span> <span data-ttu-id="ea7b8-123">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="ea7b8-124">Сериализация</span><span class="sxs-lookup"><span data-stu-id="ea7b8-124">Serialization</span></span>|<span data-ttu-id="ea7b8-125">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-125">Optional attribute.</span></span> <span data-ttu-id="ea7b8-126">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="ea7b8-127">Сериализация</span><span class="sxs-lookup"><span data-stu-id="ea7b8-127">Serialization</span></span>|<span data-ttu-id="ea7b8-128">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-128">Optional attribute.</span></span> <span data-ttu-id="ea7b8-129">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="ea7b8-130">Сериализация</span><span class="sxs-lookup"><span data-stu-id="ea7b8-130">Serialization</span></span>|<span data-ttu-id="ea7b8-131">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-131">Optional attribute.</span></span> <span data-ttu-id="ea7b8-132">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="ea7b8-133">Сериализация</span><span class="sxs-lookup"><span data-stu-id="ea7b8-133">Serialization</span></span>|<span data-ttu-id="ea7b8-134">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-134">Optional attribute.</span></span> <span data-ttu-id="ea7b8-135">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="ea7b8-136">Interop</span><span class="sxs-lookup"><span data-stu-id="ea7b8-136">Interop</span></span>|<span data-ttu-id="ea7b8-137">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-137">Optional attribute.</span></span> <span data-ttu-id="ea7b8-138">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="ea7b8-139">Interop</span><span class="sxs-lookup"><span data-stu-id="ea7b8-139">Interop</span></span>|<span data-ttu-id="ea7b8-140">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-140">Optional attribute.</span></span> <span data-ttu-id="ea7b8-141">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="ea7b8-142">Interop</span><span class="sxs-lookup"><span data-stu-id="ea7b8-142">Interop</span></span>|<span data-ttu-id="ea7b8-143">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-143">Optional attribute.</span></span> <span data-ttu-id="ea7b8-144">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="ea7b8-145">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="ea7b8-145">Name attribute</span></span>  
  
|<span data-ttu-id="ea7b8-146">Значение</span><span class="sxs-lookup"><span data-stu-id="ea7b8-146">Value</span></span>|<span data-ttu-id="ea7b8-147">Описание</span><span class="sxs-lookup"><span data-stu-id="ea7b8-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ea7b8-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="ea7b8-148">*generic_parameter_name*</span></span>|<span data-ttu-id="ea7b8-149">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-149">Required attribute.</span></span> <span data-ttu-id="ea7b8-150">Имя универсального параметра типа.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-150">The name of the generic type parameter.</span></span> <span data-ttu-id="ea7b8-151">Например, для универсального делегата <xref:System.Func%603> значение *generic_parameter_name*, равное "TResult", применяет политику среды выполнения к возвращаемому значению делегата.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="ea7b8-152">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea7b8-152">All other attributes</span></span>  
  
|<span data-ttu-id="ea7b8-153">Значение</span><span class="sxs-lookup"><span data-stu-id="ea7b8-153">Value</span></span>|<span data-ttu-id="ea7b8-154">Описание</span><span class="sxs-lookup"><span data-stu-id="ea7b8-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ea7b8-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="ea7b8-155">*policy_setting*</span></span>|<span data-ttu-id="ea7b8-156">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="ea7b8-157">Допустимые значения: `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="ea7b8-158">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ea7b8-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea7b8-159">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea7b8-159">Child Elements</span></span>  
 <span data-ttu-id="ea7b8-160">Нет.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea7b8-161">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea7b8-161">Parent Elements</span></span>  
  
|<span data-ttu-id="ea7b8-162">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea7b8-162">Element</span></span>|<span data-ttu-id="ea7b8-163">Описание</span><span class="sxs-lookup"><span data-stu-id="ea7b8-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea7b8-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="ea7b8-164">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="ea7b8-165">Применяет политику отражения среды выполнения к конструктору или методу.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="ea7b8-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="ea7b8-166">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="ea7b8-167">Применяет политику отражения среды выполнения для конкретного типа, например, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea7b8-168">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea7b8-168">Remarks</span></span>  
 <span data-ttu-id="ea7b8-169">Элемент `<GenericParameter>` является дочерним для элемента [\<Method>](method-element-net-native.md) или [\<Type>](type-element-net-native.md) и используется для применения политики к определенному параметру универсального типа, который задается его именем в сигнатуре универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-169">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="ea7b8-170">Элемент `<GenericParameter>` особенно полезен при использовании сериализаторов.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="ea7b8-171">В следующем примере используется элемент `<GenericParameter>`, который позволяет применить политику к типу `T` в вызовах к перегрузкам метода [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) сериализатора NewtonSoft JSON.</span><span class="sxs-lookup"><span data-stu-id="ea7b8-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea7b8-172">См. также</span><span class="sxs-lookup"><span data-stu-id="ea7b8-172">See also</span></span>

- [<span data-ttu-id="ea7b8-173">Элемент \<Method></span><span class="sxs-lookup"><span data-stu-id="ea7b8-173">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="ea7b8-174">\<Элемент > типа</span><span class="sxs-lookup"><span data-stu-id="ea7b8-174">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="ea7b8-175">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="ea7b8-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="ea7b8-176">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ea7b8-176">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="ea7b8-177">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ea7b8-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
