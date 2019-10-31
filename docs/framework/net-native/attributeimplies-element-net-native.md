---
title: Элемент <AttributeImplies> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 94f7813938e2179a2355e6ab2eff22479122d4b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128484"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="549de-102">Элемент \<AttributeImplies > (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="549de-102">\<AttributeImplies> Element (.NET Native)</span></span>
<span data-ttu-id="549de-103">Определяет политики для элементов кода, к которым применяется содержащий атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="549de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="549de-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="549de-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="549de-105">Attributes and Elements</span></span>  
 <span data-ttu-id="549de-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="549de-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="549de-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="549de-107">Attributes</span></span>  
  
|<span data-ttu-id="549de-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="549de-108">Attribute</span></span>|<span data-ttu-id="549de-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="549de-109">Attribute type</span></span>|<span data-ttu-id="549de-110">Описание</span><span class="sxs-lookup"><span data-stu-id="549de-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="549de-111">Отражение</span><span class="sxs-lookup"><span data-stu-id="549de-111">Reflection</span></span>|<span data-ttu-id="549de-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-112">Optional attribute.</span></span> <span data-ttu-id="549de-113">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="549de-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="549de-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="549de-114">Reflection</span></span>|<span data-ttu-id="549de-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-115">Optional attribute.</span></span> <span data-ttu-id="549de-116">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="549de-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="549de-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="549de-117">Reflection</span></span>|<span data-ttu-id="549de-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-118">Optional attribute.</span></span> <span data-ttu-id="549de-119">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="549de-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="549de-120">Сериализация</span><span class="sxs-lookup"><span data-stu-id="549de-120">Serialization</span></span>|<span data-ttu-id="549de-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-121">Optional attribute.</span></span> <span data-ttu-id="549de-122">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="549de-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="549de-123">Сериализация</span><span class="sxs-lookup"><span data-stu-id="549de-123">Serialization</span></span>|<span data-ttu-id="549de-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-124">Optional attribute.</span></span> <span data-ttu-id="549de-125">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="549de-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="549de-126">Сериализация</span><span class="sxs-lookup"><span data-stu-id="549de-126">Serialization</span></span>|<span data-ttu-id="549de-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-127">Optional attribute.</span></span> <span data-ttu-id="549de-128">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="549de-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="549de-129">Сериализация</span><span class="sxs-lookup"><span data-stu-id="549de-129">Serialization</span></span>|<span data-ttu-id="549de-130">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-130">Optional attribute.</span></span> <span data-ttu-id="549de-131">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="549de-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="549de-132">Interop</span><span class="sxs-lookup"><span data-stu-id="549de-132">Interop</span></span>|<span data-ttu-id="549de-133">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-133">Optional attribute.</span></span> <span data-ttu-id="549de-134">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="549de-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="549de-135">Interop</span><span class="sxs-lookup"><span data-stu-id="549de-135">Interop</span></span>|<span data-ttu-id="549de-136">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-136">Optional attribute.</span></span> <span data-ttu-id="549de-137">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="549de-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="549de-138">Interop</span><span class="sxs-lookup"><span data-stu-id="549de-138">Interop</span></span>|<span data-ttu-id="549de-139">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="549de-139">Optional attribute.</span></span> <span data-ttu-id="549de-140">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="549de-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="549de-141">Все атрибуты</span><span class="sxs-lookup"><span data-stu-id="549de-141">All attributes</span></span>  
  
|<span data-ttu-id="549de-142">значения</span><span class="sxs-lookup"><span data-stu-id="549de-142">Value</span></span>|<span data-ttu-id="549de-143">Описание</span><span class="sxs-lookup"><span data-stu-id="549de-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="549de-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="549de-144">*policy_setting*</span></span>|<span data-ttu-id="549de-145">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="549de-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="549de-146">Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="549de-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="549de-147">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="549de-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="549de-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="549de-148">Child Elements</span></span>  
 <span data-ttu-id="549de-149">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="549de-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="549de-150">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="549de-150">Parent Elements</span></span>  
  
|<span data-ttu-id="549de-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="549de-151">Element</span></span>|<span data-ttu-id="549de-152">Описание</span><span class="sxs-lookup"><span data-stu-id="549de-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="549de-153">\<Type></span><span class="sxs-lookup"><span data-stu-id="549de-153">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="549de-154">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="549de-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="549de-155">Заметки</span><span class="sxs-lookup"><span data-stu-id="549de-155">Remarks</span></span>  
 <span data-ttu-id="549de-156">Элемент `<AttributeImplies>` используется в том случае, если его содержащий тип является атрибутом (то есть классом, производным от <xref:System.Attribute?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="549de-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="549de-157">Если атрибут применяется к элементу определенной программы, политика, определенная элементом `<AttributeImplies>`, применяется к этому элементу программы.</span><span class="sxs-lookup"><span data-stu-id="549de-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="549de-158">Атрибуты отражения, сериализации и взаимодействия необязательны, несмотря на то, что по крайней мере один из них должен присутствовать.</span><span class="sxs-lookup"><span data-stu-id="549de-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="549de-159">См. также</span><span class="sxs-lookup"><span data-stu-id="549de-159">See also</span></span>

- [<span data-ttu-id="549de-160">Элемент > типа\<</span><span class="sxs-lookup"><span data-stu-id="549de-160">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="549de-161">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="549de-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="549de-162">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="549de-162">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="549de-163">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="549de-163">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
