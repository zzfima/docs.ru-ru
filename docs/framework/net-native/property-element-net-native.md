---
title: Элемент &lt;Property&gt; (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74fd4fa1387836e12d186a604f6996254eabf956
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549422"
---
# <a name="ltpropertygt-element-net-native"></a><span data-ttu-id="972e2-102">Элемент &lt;Property&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="972e2-102">&lt;Property&gt; Element (.NET Native)</span></span>
<span data-ttu-id="972e2-103">Применяет политику отражения среды выполнения к свойству.</span><span class="sxs-lookup"><span data-stu-id="972e2-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="972e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="972e2-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="972e2-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="972e2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="972e2-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="972e2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="972e2-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="972e2-107">Attributes</span></span>  
  
|<span data-ttu-id="972e2-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="972e2-108">Attribute</span></span>|<span data-ttu-id="972e2-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="972e2-109">Attribute type</span></span>|<span data-ttu-id="972e2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="972e2-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="972e2-111">Общие правила</span><span class="sxs-lookup"><span data-stu-id="972e2-111">General</span></span>|<span data-ttu-id="972e2-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="972e2-112">Required attribute.</span></span> <span data-ttu-id="972e2-113">Задает имя свойства.</span><span class="sxs-lookup"><span data-stu-id="972e2-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="972e2-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="972e2-114">Reflection</span></span>|<span data-ttu-id="972e2-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="972e2-115">Optional attribute.</span></span> <span data-ttu-id="972e2-116">Определяет запрос для получения сведений о свойстве или перечисляет свойство, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="972e2-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="972e2-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="972e2-117">Reflection</span></span>|<span data-ttu-id="972e2-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="972e2-118">Optional attribute.</span></span> <span data-ttu-id="972e2-119">Управляет доступом среды выполнения к свойству для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="972e2-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="972e2-120">Эта политика гарантирует, что свойство можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="972e2-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="972e2-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="972e2-121">Serialization</span></span>|<span data-ttu-id="972e2-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="972e2-122">Optional attribute.</span></span> <span data-ttu-id="972e2-123">Управляет доступом среды выполнения к свойству, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="972e2-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="972e2-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="972e2-124">Name attribute</span></span>  
  
|<span data-ttu-id="972e2-125">Значение</span><span class="sxs-lookup"><span data-stu-id="972e2-125">Value</span></span>|<span data-ttu-id="972e2-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="972e2-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="972e2-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="972e2-127">*method_name*</span></span>|<span data-ttu-id="972e2-128">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="972e2-128">The property name.</span></span> <span data-ttu-id="972e2-129">Тип свойства определяется родительским элементом [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) или [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="972e2-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="972e2-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="972e2-130">All other attributes</span></span>  
  
|<span data-ttu-id="972e2-131">Значение</span><span class="sxs-lookup"><span data-stu-id="972e2-131">Value</span></span>|<span data-ttu-id="972e2-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="972e2-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="972e2-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="972e2-133">*policy_setting*</span></span>|<span data-ttu-id="972e2-134">Параметр, применяемый к этому типу политики для свойства.</span><span class="sxs-lookup"><span data-stu-id="972e2-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="972e2-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="972e2-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="972e2-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="972e2-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="972e2-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="972e2-137">Child Elements</span></span>  
 <span data-ttu-id="972e2-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="972e2-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="972e2-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="972e2-139">Parent Elements</span></span>  
  
|<span data-ttu-id="972e2-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="972e2-140">Element</span></span>|<span data-ttu-id="972e2-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="972e2-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="972e2-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="972e2-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="972e2-143">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="972e2-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="972e2-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="972e2-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="972e2-145">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="972e2-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="972e2-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="972e2-146">Remarks</span></span>  
 <span data-ttu-id="972e2-147">Если политика свойства не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="972e2-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="972e2-148">Пример</span><span class="sxs-lookup"><span data-stu-id="972e2-148">Example</span></span>  
 <span data-ttu-id="972e2-149">В следующем примере используется отражение для создания экземпляров объекта `Book` и отображения значений его свойств.</span><span class="sxs-lookup"><span data-stu-id="972e2-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="972e2-150">Исходный файл default.rd.xml для проекта выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="972e2-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="972e2-151">Файл применяет значение `All` к политике `Activate` для класса `Book`, который предоставляет доступ к конструкторам класса через отражение.</span><span class="sxs-lookup"><span data-stu-id="972e2-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="972e2-152">Политика `Browse` для класса `Book` наследуется от его родительского пространства имен.</span><span class="sxs-lookup"><span data-stu-id="972e2-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="972e2-153">Это свойство имеет значение `Required Public`, что делает метаданные доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="972e2-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="972e2-154">Ниже приведен исходный код для этого примера.</span><span class="sxs-lookup"><span data-stu-id="972e2-154">The following is the source code for the example.</span></span> <span data-ttu-id="972e2-155">`outputBlock` Переменная представляет <xref:Windows.UI.Xaml.Controls.TextBlock> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="972e2-155">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="972e2-156">Тем не менее компиляция и выполнение этого примера создает исключение [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="972e2-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="972e2-157">Несмотря на то, что мы уже сделали метаданные для типа `Book` доступными, нам не удалось обеспечить динамический доступ к реализациям свойств считывания.</span><span class="sxs-lookup"><span data-stu-id="972e2-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="972e2-158">Эту ошибку можно исправить одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="972e2-158">We can correct this error by either in one of two ways:</span></span>  
  
-   <span data-ttu-id="972e2-159">определив политику `Dynamic` для типа `Book` в его элементе [\<Type>](../../../docs/framework/net-native/type-element-net-native.md);</span><span class="sxs-lookup"><span data-stu-id="972e2-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
-   <span data-ttu-id="972e2-160">добавив вложенный элемент [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) для каждого свойства, считывание которого необходимо вызвать, как это делает следующий файл default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="972e2-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="972e2-161">См. также</span><span class="sxs-lookup"><span data-stu-id="972e2-161">See also</span></span>
- [<span data-ttu-id="972e2-162">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="972e2-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="972e2-163">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="972e2-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="972e2-164">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="972e2-164">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
