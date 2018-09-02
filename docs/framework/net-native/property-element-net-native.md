---
title: Элемент &lt;Property&gt; (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ed75d377814a740edece2b6a69e44acbd8ef0c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424376"
---
# <a name="ltpropertygt-element-net-native"></a><span data-ttu-id="7268b-102">Элемент &lt;Property&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="7268b-102">&lt;Property&gt; Element (.NET Native)</span></span>
<span data-ttu-id="7268b-103">Применяет политику отражения среды выполнения к свойству.</span><span class="sxs-lookup"><span data-stu-id="7268b-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7268b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7268b-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7268b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7268b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7268b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7268b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7268b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7268b-107">Attributes</span></span>  
  
|<span data-ttu-id="7268b-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7268b-108">Attribute</span></span>|<span data-ttu-id="7268b-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="7268b-109">Attribute type</span></span>|<span data-ttu-id="7268b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="7268b-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="7268b-111">Общие правила</span><span class="sxs-lookup"><span data-stu-id="7268b-111">General</span></span>|<span data-ttu-id="7268b-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="7268b-112">Required attribute.</span></span> <span data-ttu-id="7268b-113">Задает имя свойства.</span><span class="sxs-lookup"><span data-stu-id="7268b-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="7268b-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="7268b-114">Reflection</span></span>|<span data-ttu-id="7268b-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="7268b-115">Optional attribute.</span></span> <span data-ttu-id="7268b-116">Определяет запрос для получения сведений о свойстве или перечисляет свойство, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7268b-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="7268b-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="7268b-117">Reflection</span></span>|<span data-ttu-id="7268b-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="7268b-118">Optional attribute.</span></span> <span data-ttu-id="7268b-119">Управляет доступом среды выполнения к свойству для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="7268b-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="7268b-120">Эта политика гарантирует, что свойство можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7268b-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="7268b-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="7268b-121">Serialization</span></span>|<span data-ttu-id="7268b-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="7268b-122">Optional attribute.</span></span> <span data-ttu-id="7268b-123">Управляет доступом среды выполнения к свойству, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="7268b-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="7268b-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="7268b-124">Name attribute</span></span>  
  
|<span data-ttu-id="7268b-125">Значение</span><span class="sxs-lookup"><span data-stu-id="7268b-125">Value</span></span>|<span data-ttu-id="7268b-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="7268b-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7268b-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="7268b-127">*method_name*</span></span>|<span data-ttu-id="7268b-128">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="7268b-128">The property name.</span></span> <span data-ttu-id="7268b-129">Тип свойства определяется родительским элементом [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) или [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7268b-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="7268b-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="7268b-130">All other attributes</span></span>  
  
|<span data-ttu-id="7268b-131">Значение</span><span class="sxs-lookup"><span data-stu-id="7268b-131">Value</span></span>|<span data-ttu-id="7268b-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="7268b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7268b-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="7268b-133">*policy_setting*</span></span>|<span data-ttu-id="7268b-134">Параметр, применяемый к этому типу политики для свойства.</span><span class="sxs-lookup"><span data-stu-id="7268b-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="7268b-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="7268b-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="7268b-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7268b-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7268b-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7268b-137">Child Elements</span></span>  
 <span data-ttu-id="7268b-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7268b-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7268b-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7268b-139">Parent Elements</span></span>  
  
|<span data-ttu-id="7268b-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="7268b-140">Element</span></span>|<span data-ttu-id="7268b-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="7268b-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7268b-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="7268b-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="7268b-143">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="7268b-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="7268b-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="7268b-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="7268b-145">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="7268b-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7268b-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="7268b-146">Remarks</span></span>  
 <span data-ttu-id="7268b-147">Если политика свойства не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="7268b-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7268b-148">Пример</span><span class="sxs-lookup"><span data-stu-id="7268b-148">Example</span></span>  
 <span data-ttu-id="7268b-149">В следующем примере используется отражение для создания экземпляров объекта `Book` и отображения значений его свойств.</span><span class="sxs-lookup"><span data-stu-id="7268b-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="7268b-150">Исходный файл default.rd.xml для проекта выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7268b-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="7268b-151">Файл применяет значение `All` к политике `Activate` для класса `Book`, который предоставляет доступ к конструкторам класса через отражение.</span><span class="sxs-lookup"><span data-stu-id="7268b-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="7268b-152">Политика `Browse` для класса `Book` наследуется от его родительского пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7268b-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="7268b-153">Это свойство имеет значение `Required Public`, что делает метаданные доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7268b-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="7268b-154">Ниже приведен исходный код для этого примера.</span><span class="sxs-lookup"><span data-stu-id="7268b-154">The following is the source code for the example.</span></span> <span data-ttu-id="7268b-155">Переменная `outputBlock` представляет элемент управления [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx).</span><span class="sxs-lookup"><span data-stu-id="7268b-155">The `outputBlock` variable represents a [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="7268b-156">Тем не менее компиляция и выполнение этого примера создает исключение [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7268b-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="7268b-157">Несмотря на то, что мы уже сделали метаданные для типа `Book` доступными, нам не удалось обеспечить динамический доступ к реализациям свойств считывания.</span><span class="sxs-lookup"><span data-stu-id="7268b-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="7268b-158">Эту ошибку можно исправить одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="7268b-158">We can correct this error by either in one of two ways:</span></span>  
  
-   <span data-ttu-id="7268b-159">определив политику `Dynamic` для типа `Book` в его элементе [\<Type>](../../../docs/framework/net-native/type-element-net-native.md);</span><span class="sxs-lookup"><span data-stu-id="7268b-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
-   <span data-ttu-id="7268b-160">добавив вложенный элемент [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) для каждого свойства, считывание которого необходимо вызвать, как это делает следующий файл default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="7268b-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7268b-161">См. также</span><span class="sxs-lookup"><span data-stu-id="7268b-161">See Also</span></span>  
 [<span data-ttu-id="7268b-162">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="7268b-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="7268b-163">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="7268b-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="7268b-164">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="7268b-164">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
