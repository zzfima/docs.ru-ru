---
title: "Элемент &lt;AttributeImplies&gt; (машинный код .NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec2bc90283aa39b8258ad14777cda7180c043c69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltattributeimpliesgt-element-net-native"></a><span data-ttu-id="d5e12-102">Элемент &lt;AttributeImplies&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="d5e12-102">&lt;AttributeImplies&gt; Element (.NET Native)</span></span>
<span data-ttu-id="d5e12-103">Определяет политики для элементов кода, к которым применяется содержащий атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e12-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5e12-104">Syntax</span></span>  
  
```xml  
<AttributeImplies Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5e12-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5e12-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d5e12-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5e12-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5e12-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5e12-107">Attributes</span></span>  
  
|<span data-ttu-id="d5e12-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d5e12-108">Attribute</span></span>|<span data-ttu-id="d5e12-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="d5e12-109">Attribute type</span></span>|<span data-ttu-id="d5e12-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d5e12-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="d5e12-111">Отражение</span><span class="sxs-lookup"><span data-stu-id="d5e12-111">Reflection</span></span>|<span data-ttu-id="d5e12-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-112">Optional attribute.</span></span> <span data-ttu-id="d5e12-113">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d5e12-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="d5e12-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="d5e12-114">Reflection</span></span>|<span data-ttu-id="d5e12-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-115">Optional attribute.</span></span> <span data-ttu-id="d5e12-116">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5e12-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="d5e12-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="d5e12-117">Reflection</span></span>|<span data-ttu-id="d5e12-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-118">Optional attribute.</span></span> <span data-ttu-id="d5e12-119">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="d5e12-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="d5e12-120">Сериализация</span><span class="sxs-lookup"><span data-stu-id="d5e12-120">Serialization</span></span>|<span data-ttu-id="d5e12-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-121">Optional attribute.</span></span> <span data-ttu-id="d5e12-122">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="d5e12-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="d5e12-123">Сериализация</span><span class="sxs-lookup"><span data-stu-id="d5e12-123">Serialization</span></span>|<span data-ttu-id="d5e12-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-124">Optional attribute.</span></span> <span data-ttu-id="d5e12-125">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5e12-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="d5e12-126">Сериализация</span><span class="sxs-lookup"><span data-stu-id="d5e12-126">Serialization</span></span>|<span data-ttu-id="d5e12-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-127">Optional attribute.</span></span> <span data-ttu-id="d5e12-128">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5e12-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="d5e12-129">Сериализация</span><span class="sxs-lookup"><span data-stu-id="d5e12-129">Serialization</span></span>|<span data-ttu-id="d5e12-130">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-130">Optional attribute.</span></span> <span data-ttu-id="d5e12-131">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5e12-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="d5e12-132">Interop</span><span class="sxs-lookup"><span data-stu-id="d5e12-132">Interop</span></span>|<span data-ttu-id="d5e12-133">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-133">Optional attribute.</span></span> <span data-ttu-id="d5e12-134">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="d5e12-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="d5e12-135">Interop</span><span class="sxs-lookup"><span data-stu-id="d5e12-135">Interop</span></span>|<span data-ttu-id="d5e12-136">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-136">Optional attribute.</span></span> <span data-ttu-id="d5e12-137">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="d5e12-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="d5e12-138">Interop</span><span class="sxs-lookup"><span data-stu-id="d5e12-138">Interop</span></span>|<span data-ttu-id="d5e12-139">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d5e12-139">Optional attribute.</span></span> <span data-ttu-id="d5e12-140">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="d5e12-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="d5e12-141">Все атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5e12-141">All attributes</span></span>  
  
|<span data-ttu-id="d5e12-142">Значение</span><span class="sxs-lookup"><span data-stu-id="d5e12-142">Value</span></span>|<span data-ttu-id="d5e12-143">Описание</span><span class="sxs-lookup"><span data-stu-id="d5e12-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d5e12-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="d5e12-144">*policy_setting*</span></span>|<span data-ttu-id="d5e12-145">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="d5e12-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="d5e12-146">Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="d5e12-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="d5e12-147">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d5e12-147">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5e12-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5e12-148">Child Elements</span></span>  
 <span data-ttu-id="d5e12-149">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5e12-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5e12-150">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5e12-150">Parent Elements</span></span>  
  
|<span data-ttu-id="d5e12-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5e12-151">Element</span></span>|<span data-ttu-id="d5e12-152">Описание</span><span class="sxs-lookup"><span data-stu-id="d5e12-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5e12-153">\<Type></span><span class="sxs-lookup"><span data-stu-id="d5e12-153">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="d5e12-154">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="d5e12-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5e12-155">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5e12-155">Remarks</span></span>  
 <span data-ttu-id="d5e12-156">Элемент `<AttributeImplies>` используется в том случае, если его содержащий тип является атрибутом (то есть классом, производным от <xref:System.Attribute?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="d5e12-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="d5e12-157">Если атрибут применяется к элементу определенной программы, политика, определенная элементом `<AttributeImplies>`, применяется к этому элементу программы.</span><span class="sxs-lookup"><span data-stu-id="d5e12-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="d5e12-158">Атрибуты отражения, сериализации и взаимодействия необязательны, несмотря на то, что по крайней мере один из них должен присутствовать.</span><span class="sxs-lookup"><span data-stu-id="d5e12-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e12-159">См. также</span><span class="sxs-lookup"><span data-stu-id="d5e12-159">See Also</span></span>  
 [<span data-ttu-id="d5e12-160">\<Тип > элемент</span><span class="sxs-lookup"><span data-stu-id="d5e12-160">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="d5e12-161">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="d5e12-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="d5e12-162">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d5e12-162">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="d5e12-163">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d5e12-163">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
