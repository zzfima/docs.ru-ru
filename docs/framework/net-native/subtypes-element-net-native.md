---
title: <Subtypes>Элемент (.NET Родной)
ms.date: 03/30/2017
ms.assetid: fb854070-248b-46cf-9dab-c322e2b4d624
ms.openlocfilehash: bb719449f3769c5dbbde6d05efdb865c18bb4ab2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180935"
---
# <a name="subtypes-element-net-native"></a><span data-ttu-id="c8b41-102">\<Подтипы> элемент (.NET Родной)</span><span class="sxs-lookup"><span data-stu-id="c8b41-102">\<Subtypes> Element (.NET Native)</span></span>
<span data-ttu-id="c8b41-103">Применяет политику среды выполнения для всех классов, унаследованных из содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="c8b41-103">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b41-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8b41-104">Syntax</span></span>  
  
```xml  
<Subtypes Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8b41-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c8b41-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c8b41-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c8b41-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8b41-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8b41-107">Attributes</span></span>  
  
|<span data-ttu-id="c8b41-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c8b41-108">Attribute</span></span>|<span data-ttu-id="c8b41-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="c8b41-109">Attribute type</span></span>|<span data-ttu-id="c8b41-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c8b41-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="c8b41-111">Отражение</span><span class="sxs-lookup"><span data-stu-id="c8b41-111">Reflection</span></span>|<span data-ttu-id="c8b41-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-112">Optional attribute.</span></span> <span data-ttu-id="c8b41-113">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="c8b41-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="c8b41-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="c8b41-114">Reflection</span></span>|<span data-ttu-id="c8b41-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-115">Optional attribute.</span></span> <span data-ttu-id="c8b41-116">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c8b41-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="c8b41-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="c8b41-117">Reflection</span></span>|<span data-ttu-id="c8b41-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-118">Optional attribute.</span></span> <span data-ttu-id="c8b41-119">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="c8b41-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="c8b41-120">Сериализация</span><span class="sxs-lookup"><span data-stu-id="c8b41-120">Serialization</span></span>|<span data-ttu-id="c8b41-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-121">Optional attribute.</span></span> <span data-ttu-id="c8b41-122">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="c8b41-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="c8b41-123">Сериализация</span><span class="sxs-lookup"><span data-stu-id="c8b41-123">Serialization</span></span>|<span data-ttu-id="c8b41-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-124">Optional attribute.</span></span> <span data-ttu-id="c8b41-125">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c8b41-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="c8b41-126">Сериализация</span><span class="sxs-lookup"><span data-stu-id="c8b41-126">Serialization</span></span>|<span data-ttu-id="c8b41-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-127">Optional attribute.</span></span> <span data-ttu-id="c8b41-128">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c8b41-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="c8b41-129">Сериализация</span><span class="sxs-lookup"><span data-stu-id="c8b41-129">Serialization</span></span>|<span data-ttu-id="c8b41-130">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-130">Optional attribute.</span></span> <span data-ttu-id="c8b41-131">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c8b41-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="c8b41-132">Interop</span><span class="sxs-lookup"><span data-stu-id="c8b41-132">Interop</span></span>|<span data-ttu-id="c8b41-133">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-133">Optional attribute.</span></span> <span data-ttu-id="c8b41-134">Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.</span><span class="sxs-lookup"><span data-stu-id="c8b41-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="c8b41-135">Interop</span><span class="sxs-lookup"><span data-stu-id="c8b41-135">Interop</span></span>|<span data-ttu-id="c8b41-136">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-136">Optional attribute.</span></span> <span data-ttu-id="c8b41-137">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="c8b41-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="c8b41-138">Interop</span><span class="sxs-lookup"><span data-stu-id="c8b41-138">Interop</span></span>|<span data-ttu-id="c8b41-139">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8b41-139">Optional attribute.</span></span> <span data-ttu-id="c8b41-140">Определяет политики для маршалинга типов значений в машинный код.</span><span class="sxs-lookup"><span data-stu-id="c8b41-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="c8b41-141">Все атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8b41-141">All attributes</span></span>  
  
|<span data-ttu-id="c8b41-142">Значение</span><span class="sxs-lookup"><span data-stu-id="c8b41-142">Value</span></span>|<span data-ttu-id="c8b41-143">Описание</span><span class="sxs-lookup"><span data-stu-id="c8b41-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c8b41-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="c8b41-144">*policy_setting*</span></span>|<span data-ttu-id="c8b41-145">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="c8b41-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="c8b41-146">Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`.</span><span class="sxs-lookup"><span data-stu-id="c8b41-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="c8b41-147">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c8b41-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8b41-148">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8b41-148">Child Elements</span></span>  
 <span data-ttu-id="c8b41-149">Нет.</span><span class="sxs-lookup"><span data-stu-id="c8b41-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8b41-150">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c8b41-150">Parent Elements</span></span>  
  
|<span data-ttu-id="c8b41-151">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8b41-151">Element</span></span>|<span data-ttu-id="c8b41-152">Описание</span><span class="sxs-lookup"><span data-stu-id="c8b41-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8b41-153">\<Тип></span><span class="sxs-lookup"><span data-stu-id="c8b41-153">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="c8b41-154">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="c8b41-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8b41-155">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8b41-155">Remarks</span></span>  
 <span data-ttu-id="c8b41-156">Элемент `<Subtypes>` применяет политику ко всем подтипам его содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="c8b41-156">The `<Subtypes>` element applies policy to all the subtypes of its containing type.</span></span> <span data-ttu-id="c8b41-157">Используется для применения различных политик для производных типов и их базовых классов.</span><span class="sxs-lookup"><span data-stu-id="c8b41-157">You use it when you want to apply different policies to derived types and their base classes.</span></span>  
  
 <span data-ttu-id="c8b41-158">Атрибуты отражения, сериализации и взаимодействия необязательны, несмотря на то, что по крайней мере один из них должен присутствовать.</span><span class="sxs-lookup"><span data-stu-id="c8b41-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8b41-159">Пример</span><span class="sxs-lookup"><span data-stu-id="c8b41-159">Example</span></span>  
 <span data-ttu-id="c8b41-160">В следующем примере определяется класс с именем `BaseClass` и подкласс с именем `Derived1`.</span><span class="sxs-lookup"><span data-stu-id="c8b41-160">The following example defines a class named `BaseClass` and a subclass named `Derived1`.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#4)]  
  
 <span data-ttu-id="c8b41-161">Как показано в следующем коде, файл директив среды выполнения явно задает политики `Dynamic` и `Activate` для `BaseClass` в `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="c8b41-161">As shown in the following code, the runtime directives file explicitly sets the `Dynamic` and `Activate` policies for `BaseClass` to `Excluded`.</span></span> <span data-ttu-id="c8b41-162">Из-за этого, объекты типа `BaseClass` не могут использоваться для динамического создания экземпляров или создания путем вызовов конструктора класса `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="c8b41-162">Because of this, objects of type `BaseClass` cannot be instantiated dynamically or by calls to the `BaseClass` class constructor.</span></span> <span data-ttu-id="c8b41-163">Тем не менее, элемент `<Subtypes>` допускает использование классов, производных от `BaseClass`, для динамического создания экземпляров, а также для создания с помощью вызовов их конструкторов класса.</span><span class="sxs-lookup"><span data-stu-id="c8b41-163">However, the `<Subtypes>` element allows classes derived from `BaseClass` to be instantiated dynamically and through calls to their class constructors.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
   <Assembly Name="*Application*" Dynamic="Required All" />  
     <Type Name="Examples.Libraries.BaseClass" Activate ="Excluded" Dynamic="Excluded" >  
        <Subtypes Activate="Public" Dynamic ="Public"/>  
     </Type>  
  </Application>  
</Directives>  
```  
  
 <span data-ttu-id="c8b41-164">Благодаря директиве `<Subtypes>`, следующий код, динамически создающий экземпляр `Derived1` экземпляр путем вызова метода <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType>, выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="c8b41-164">Because of the `<Subtypes>` directive, the following code that instantiates a `Derived1` instance dynamically by calling the <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType> method executes successfully.</span></span>  <span data-ttu-id="c8b41-165">Здесь переменная блока представляет объект <xref:System.Windows.Controls.TextBlock> в пустом приложении для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="c8b41-165">The block variable here is a <xref:System.Windows.Controls.TextBlock> object in a blank Windows Store app.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c8b41-166">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c8b41-166">See also</span></span>

- [<span data-ttu-id="c8b41-167">\<Элемент типа></span><span class="sxs-lookup"><span data-stu-id="c8b41-167">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="c8b41-168">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="c8b41-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c8b41-169">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c8b41-169">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="c8b41-170">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c8b41-170">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
